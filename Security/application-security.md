# Application Security

## Authentication System Design

The following principles should be applied to the authentication system:

### Adopt Zero-Trust Principles

The X-Files (tv show) hit on the very principle that should be applied to all aspects of technology; "trust no-one".  The following should be adopted:

* **Segregation of frontend and backend:**  You should not trust any information that is stored or received from client-side/frontend components.  As such, frontend should strictly handle user interface and never store or manipulate secrets.  All sensitive logic and checks should be implemented within backend components.
* **Short-Lived Access Tokens:** Any tokens that are issues should be short-lived, this would limit the window of opportunity for attackers if the token is disclosed or compromised.


### Leverage Multi-Factor Authentication (MFA)

MFA should be implemented as a minimum standard, password based authentication is obsolete and vulnerable to a plethora of both frontend (disclosure/extraction) and backend (brute-force, insecure storage/handling).

As such the following should be implemented:

* **Time-based One-Time Password (TOTP):** This effectively provides a seed which is used to compute a deterministic number over a period of 60 seconds; applications such as google authenticator provide this functionality.  With a new secret been generated frequently, adheres to the `Short-Lived Access Tokens` item discussed above.
* **Adaptive/Context Aware MFA:**  Should changes in login behavior, source IP/Device or a privileged action be performed.  The application should require the user to re-authenticate via a method such as MFA re-challenge in order to verify themselves.  This would help mitigate session hijacking based attacks.


### Authentication Source

How a user would authenticate to the system is critical.  only trusted, secure sources should be used.  The following principles should be considered:

* **Identity Provider Integration (IdP):**  Where possible, consideration should be given to implementing idP capabilities; these providers consolidate user authentication processes, reducing administrative overhead and streamlining the user experience. leveraging SAML or OAuth2/OpenID Connect, the system inherits mature security controls while maintaining compatibility with enterprise and social login services.
  * *__Enterprise SSO Compatibility:__* Use common IdP solutions such as Okta and Auth0.
  * *__Social Login:__* Use trusted social platforms (e.g., Google, Microsoft).  However, permissions need to be carefully limited to ensure data retrieval is limited to only what is needed.
* **Local Credential Storage:** Should the system store user credentials locally, strong hashing algorithms like Argon2 or bcrypt with random salts will protect against brute force attacks. Pairing this with adaptive authentication checks, such as device or geolocation verification will assist in detecting suspicious login attempts early.
* **Credential Governance:** The syste should enforce robust password policies, including complexity and rotation requirements; minimising the risk of compromised credentials. Where possible, automated provisioning and deprovisioning workflows should be implemented to further ensure only authorised users retain access; improving overall security posture.


### Communication

* **Use HTTPS Everywhere:** Any communication with external clients or internal critical components should be over HTTPS where TLS 1.2 or higher is used to ensure confidentiality and integrity of data in transit.
* **Network Footprint:**  Externally facing infrastructure should only present the ports absolutely nessesary for the application to be accessed by its end users.  Where possible (mostly internally), firewall rules should be implemented specifically defining IP & Port information between critical components; ensuring only a minimal attack footprint is presented to an attacker.


### Session Management

* **Token Lifetimes & Rotation:**  Session tokens should have a maximum lifetime of 15-30 minutes, these tokens should be accompanied with an additional 7-14 day refresh token.  Seamless renewals should be permitted up to a hard cap of approximately 24-48hrs.  At this limit, users would be forced to re-authenticate themselves.  Upon session refresh, both tokens should be refreshed/changed; this will reduce the time window in which successful replay and disclosure attacks could occur.
* **Session Storage & Lifetime Management:** Cookies should leverage secure attributes such as `SameSite`, `Secure` and `HttpOnly` where possible to prevent unauthorised script access or disclosure across differing sites.  Session information should never be stored within the browsers Storage API (local/session storage) due to the overly permissive access restrictions; increasing the risk of disclosure and session hijacking attacks.
* **Session Revocation & Logout:**  Session information should be centrally managed within the back-end where upon events such as user logout, password change or anomaly detection the session should be terminated.
* **Concurrent Session Control:** Concurrent sessions should be restricted to a single active session where possible, should a new session be created.  The user should receive a prompt to terminate the older sessions.  Additional controls such as device fingerprinting, IP address or geolocation should be used in order to identify anomalies where any suspicious behavior would result in the session being terminated.  This will provide additional layers of security that help mitigate against token theft/disclosure and session hijacking.


## JWT Token Security

### Architecture 

Care should be taken to not implement all of the JWT token functionality within a single monolith/endpoint, this presents a single point of failure/are in which to attack.  Consider splitting up the various processes to seperate backend components, such as:

* **Dedicated Authentication Service:** Token minting should be performed in a centralised, hardened service that is isolated from general business logic API's.  Internal access to this service should be via HTTPS or mTLS where possible.
* **Token Verification:** Verification can be performed within the API gateways where respective fields such as `exp` and `iss` can be verified.
* **Session Service:** This service stores relevant session information relating to the logged-in user.  This information is transitory where applications such as Redis are used.


### Token List

At a minimum the following tokens should be used:

* **Session Token**
  * **Purpose:** General user session token, permitting access to authenticated areas of the application.  This token would be tied to backend "session context" such as the device fingerprint and IP address.
  * **Lifetime:** Maximum 8 hours of inactivity with a sliding window.
* **Refresh Token**
  * **Purpose:** Allows seamless/silent renewal of the session token without the user requiring to authenticate themselves.
  * **Lifetime:** Maximum 24-48 hours, however the token should be single use and rotated.


### Signing & Encryption

* **Use Strong Algorithms:** Utilise 256bit encryption at a minimum, where possible `ES256` or `RS256` should be used.  Consideration should be given to leveraging `ES256` due to eliptic curve cryptography providing a significantly reduced signature payload; reducing the overall size of the JWT.
* **Encrypt Both Inner & Outer JWT Parts:**  The body of the JWT token should be signed by an appropriate algorithm (outlined above).  However, should claims or other secret/sensitive information be stored within the token.  Consideration should be given to encrypting these areas (e.g. JSON Web Encryption) using algorithms such as `A256GCM`.  This would keep public claims readable within the backend gateway for routing while also encrypting more sensitive claims.
* **Key Rotation:**  Secrets/Keys should be rotated on a regular basis (e.g. every 90 days), this would limit any impact of key disclosure.
* **Key Generation & Storage:**  Where possible a FIPS 140-2 compliant KMS should be leveraged for key generation and storage.  A root/primary key would be generated within the KMS where "leaf" keys should then be derived for each environment (e.g. prod/dev) requiring JWT functionality.


### Token Lifecycle

The following is a rough outline of the token lifecycle process one a user has successfully authenticated to the SPA:


1. **Issue Tokens:**  Auth service issues a JWT session token (with a correct `jti` token identifier) and a refresh token (can be a cookie, leveraging httpOnly, secure and SameSite).
2. **Session Token Verification:** 

   
   1. The API gateway would validate the signature and expiry locally to provide quick validation.  
   2. Upon sucessful validation, the `jti` claim should then be added to a sliding list with an expiry set to the token expiry (e.g. 8hrs); this will assist in preventing replay attacks.
   3. Session information should be cross-checked with the session service to ensure validity. 
   4. The scope/claims should then be checked to ensure sufficient permissions to perform the intended action.
3. **Session Token Refresh**

   
   1. The SPA would send a request to an authentication service endpoint such as `/refresh` with the refresh token.
   2. The refresh token information should then be validated with the session service, where claims and expiry information is checked.
   3. Upon success, a new refresh and session token are generated and sent to the SPA.  The old tokens would then be disabled/removed from the session service.


### Logging/Monitoring/Auditing

Information should be logged to a centralized repository, this repository should reside within a locked down, segregated account where access is strictly controlled and monitored.

* **Capture & Logging of Information:** 
  * *__Session Identifiers:__* Relevant session information such as the `jti` claim within the token.
  * User Account Information: Relevant information permitting the user account to be easily identified (e.g. account ID).
  * *__Source IP:__*  The source IP address of the actor performing any action.
  * *__Action Performed:__* An outline of what action was performed and whether said action is successful. 
* **Monitor Activity For Anomalies:**
  * **Failed Signatures:** 3 or more failed attempts by the same IP should be logged and blocked.
  * **Different Geolocation/Continent:** Notify end user and execute investigatory workflow to determine whether the session has been hijacked.


### Financial Security Concerns

* **User PII:** Any Personally Identifiable Information (PII) would need to meet GDPR standards.  In general, this would mean isolating and storing PII information in a European location where data should be encrypted at rest.  Access should be kept to a minimum and should PII information bleed into other systems then tokenisation may be required to provide anonymity.
* **Audit Logs:**  Logs should be detailed enough to enforce non-repudiation while being stored in a tamper resistant manner.  Additional controls such as checkpoints (hash of logs to date can be created and stored in a external local to provide independent verification).
* Log Retention:  Financial compliance regulations generally stipulate the retention period for logs should be between 5-7 years.
* **Key Management:** Compliance standards such as MiCA require keys to be rotated after a defined period of time to minimise risk of disclosure.  Access to keys should be strictly monitored where any user who has access to key material cannot access the production resources where key material is used. A process should also be clearly defined for swapping of compromised key material.
* **Key Generation:**  Seed/Key material should use a 256 bit mnemonic with a 256bit salt/passphrase (512bit total) for generating any private keys.  The entropy required to generate randomness should be FIPS 140-2 compliant and steps should be taken to ensure all artifacts used in seed generation are destroyed upon completion.  The private key should leverage technology such as Shamir Secrets Sharing where a minimum of 3 shares are created and stored in 3 unique but separate locations.  Access to keys should be strictly monitored where any user who has access to key material cannot access the production resources where key material is used.

  \

## TurnKey Key-Pair Delegated Signing Security

### Architecture

#### Architecture Considerations

* **Strong Identity and Access Management (IAM):** Integrate key management with IAM solutions to enforce strict access controls using role-based access (RBAC).  This should be combined with Multi-factor authentication (MFA) being enforced for all keypair operations or environment access.
* **KMS Usage Cost:** Where possible, KMS should handle all key operations ranging from generation to storage and signing.  However, this may be cost prohibitive with large number of users (e.g. $1 per key).
* **Pooled Customer Managed Keys (CMK):** A small batch of parent CMK keys should be created within the KMS, the `KeyId` could then be used like a "tenant bucket"" where 5-10k+ users could have their key-pairs encrypted by the root/parent CMK.  This would dramatically reduce costs.
* **Segregation of Duties:**  The process should be split between 3 distinct, segregated zones:
  * *__Data Plane:__*  This would be public facing where its primary purpose is to facilitate signing of delegation requests.
  * *__Control Plane:__*  This is an internal area where the KMS is located, strict IAM policies and additional controls such as `GuardDuty` would be operating.
  * *__Observability:__* This is a high-controlled area that agrigates all logs into CloudTrail and would implement CloudWatch or SIEM capabilities.


#### Data Plane

* **Purpose:** Handles live cryptographic operations (key generation, decrypt, sign) for every request in the trading path.
* **Key Components:** Private ALB, ECS Fargate signing service, Nitro Enclave signer process \[Generates key-pair or retrieves encrypted key-pair from DynamoDB and decrypts via KMS\], DynamoDB key‑vault table \[individual user key pairs, stored as encrypted blob with pooled CMK key\].
* **Isolation Model:** No public IPs; ALB and tasks in private subnets with VPC interface endpoints for KMS/DynamoDB.
* **Resilience:** Deployed across three AZs (eu‑west‑1a/b/c); DynamoDB global table replicates to DR region.

#### Control Plane

* **Purpose:** Governs identity, policy and cryptographic root‑of‑trust for pooled CMKs.
* **Key Components:** AWS KMS asymmetric CMK shards, strict IAM + SCP guard‑rails and GuardDuty/Security Hub.
* **Shard Mapping:** Leverage a deterministic process for enforcing tenancy based on user identifier and KMS/CMK KeyId.
* **Policy Hardening:** CMK policies allow only `kms:Sign/kms:Decrypt` to the signing‑service role; `kms:Export*` denied by SCP.
* **Resilience**: Multi‑Region CMKs (eu‑west‑1 <‑> eu‑central‑1) keep DR copies in sync with zero user impact.

#### Observability

* **Purpose:** Provide tamper‑evident, real‑time visibility and automated containment for key‑related events.
* **Key Components:** CloudTrail (all KMS calls), CloudWatch Logs Insights, SIEM \[such as Wazzuh\].
* **Evidence Storage:** Long-term log/information storage within an encrypted S3 bucket in `COMPLIANCE` mode \[Data cannot be overwritten or deleted\].

  \

### Observability & Auditing

* **Segregated Logging Account/Environment:**  Logs should be sent to a centrally managed environment, with the following characteristics:
  * *__Permissions:__* this environment should be heavily locked down via IAM + SCP guard rails where read-only access is the default level of permissions.
  * *__Isolation:__* This environment does not have internet access where possible or restricted to specific services (e.g. Grafana Cloud).  Access to this environment should be through a bastion host which is hardened to security baselines such as CIS.
  * *__Activity Logging:__* Any environment activity should generate audit logs, this can range from users accessing resources to changing settings.
* **KMS & Signer Process Logging:**  All logs should be streamed to this environment, an example of such logs would be `kms:Sign/kms:Decrypt` or `kms:*`.
* **Contextual Enrichment:**  Where possible logs streamed to this environment should be contextually enriched so they provide as much context as possible.  Such enrichment items could include, user-id, IP/device fingerprint and application request.
* **Clock Discipline:** Where possible all critical services that involve logs (both sending/recieving) should leverage clock syncronisation processes (e.g. NTP) to ensure the time being recorded across the environment is consistent.  Efforts should also be taken to ensure a single format/standard is used (e.g. UTC).
* **Non-Repudiation:** Information could be stored within a S3 bucket in `COMPLIANCE` mode which prevents information being overwritten or deleted, even by the root user.  However, consideration should be given to  aggregating logs every `X` hours into a compressed data structure such as a Merkle tree.  This can then be posted to the bitcoin/solana testnet/mainnet;  providing a temper-proof external means of verifying the integrity of logs within an environment.


### Detecting & Alerting on Abnormal Usage

There are multiple methods for detecting abnormal usage, however the majority tend to focus on building up behavioral patterns.  This means a baseline of normal activity would need to be established, from this baseline outliers can be more easily identified and acted upon.

The following areas should be investigated to identify abnormal usage:

#### Anomaly Detection

* **Centralise Log Collection:**  All log information should be published to a single source, this would make analysis/identification orders of magnitude easier to perform.
* **Rolling Baseline:**  User trends can change over time, as such a rolling 30-day baseline should be established, this will enhance any statistical profiling methods.
* **Statistical Profiling:**  Post baseline, it could be possible to implement outlier profiling, some areas that should be investigated are:
  * **Impossible‑travel:** A user session/action is used from two ASN / countries within <5 min.
  * **Work‑hours drift:** User login/action is performed outside declared trading window triggers "suspect" flag.
  * **Rate anomaly:** >3× 90th percentile action volume over 15 min → *critical* alert.
* **Device Fingerprinting Deviations:** Should the fingerprint of devices change then it should set a "suspect" flag where additional user verification measures should be performed.
* **Expired API/Keys:**  Any use of expired API or crypto keys (e.g. signing) should also trigger a "suspect" flag.

#### Alerting and Incident Response Automation

* **Alerting Channels:**  Create a dedicated channel/medium (e.g. Slack/Email) where any alert is posted, this alert should contain relevant context such as perceived severity, action, resource and timestamp.
* **Leverage Automation:** Automation should be used where security alerts are integrated with relevant ticketing and incident response platforms (e.g. Jira, PagerDuty).

#### Continuous Monitoring

* **Real-time Monitoring:**  Audit logs should be analysed from a security perspective, as close to real-time as possible; this will enable rapid detection and response to anomalies.
* **Report Generation:**  Periodic reports should be generated based on deviations, these reports should contain delta's of previous reports in order to provide trend information.
* **Periodic Review:**  The process and the information/logs should be reviewed on a bi-annual basis from a risk assessment perspective, any deficiencies should be documented and remediated.  This will provide a feedback loop for continuous improvement.


### Key Exfiltration Prevention

The organisation must adopt an "assume-breach" stance; attackers are persistent and while organisations have to secure a wide attack surface, it only takes one crack which could lead to compromise.

The security adage of "defense in depth" needs to be applied where controls are layered at different levels within the technology stack.  Some of these controls/layers are outlined below:

#### HSM Key Controls

* Non-Export Policies: Key material should be stored within a HSM where possible and marked as non-exportable.  This will prevent leakage/exfiltration.

#### Endpoint Security

* **Hardened Corporate Devices:**  Devices used by the organisation should be hardened to appropriate benchmarks (such as CIS), it should be noted a pragmatic approch would need to be taken as developers often require installing tools or administrator access.
* **Hardware Key Authentication:**  Devices such as YubiKeys should be used for authentication and signing, password extraction is one of the primary means of lateral movement.  Requiring users to sign into their devices with YubiKey will aid in eliminating their use.
* **DLP Solutions:**  Leverage DLP solutions (e.g. Google Workspace Enterprise) that restrict where data can be viewed or copied to (e.g. Google Drive can prevent files from being copied/printed from the drive).  This reduces the attack surface, allowing controls to have more impact.
* **Restrict Internet Access:**  All devices should route their traffic through an appropriate proxy that prevents access to potentially malicious sites or downloading of unauthorised software.  User activity should be appropriately logged and regularly reviewed.

#### Environment

* **Network Segregation:**  The environment should be segregated based on perceived risk to each running service and its function.  Critical systems should reside within their own network segment.  
* **Principle of Least Privilege:** Access or service to service communication should be restricted to specific ports or permissions where possible.  This would involve defining appropriate IAM roles and security groups.
* **Process Isolation:** Critical services (e.g. such as signing) should be completely isolated at the process level.  Technologies such as AWS Nitro could be used to isolate an cryptographically attest the image/process is legitimate.
* **Monitoring:**  Critical network segments should have appropriate network, environment and runtime monitoring solutions setup (such as a GuardDuty/Falco) where this information is centrally collected and analysed by a SIEM (such as Wazzuh).

#### Just-In-Time (JIT) Privilege Access

* **Principle of Least Privilege:** Whether its a corporate device or AWS environment, the organisation should create 2 accounts (standard/administrator) where the standard account is used by default.  Elevation to an administrator should be temporary and its activity be logged.
* **Privilege Granting/Revoking process:**  Should additional priviledges be required, these would need to be logged/tracked in an appropriate medium (e.g. Jira ticket).  Permissions should be kept to a minimum, granted when absolutely necessary with access being revoked when the tack is complete.
* **Periodic Review of Privileged Roles:** All privileged roles within the organisation (AWS/Third-Part Apps/Devices) should be reviewed on a quarterly basis to ensure access is granted to only legitimate users.

#### Regular Security Assessments/Penetration Testing

* **External Audits:**  Critical infrastructure/services should receive an annual penetration test by an reputable external vendor.
* **Internal Audits:** Periodic audits/testing should be performed against the environment, data and devices to proactively identify and remediate vulnerabilties.
* **War Gaming:** Periodic "war gaming" sessions should be held with internal teams; beach/compromise scenarios would be detailed and the organisations controls/detection/response capabilities be measured.  Identified gaps should then be remediated.

## Frontend Security Strategy

Within the Web3 industry, smart contracts are perceived to be the biggest risk to Web3 apps.  This is just "one side of the coin", with the "middle-man"" removal, the onus for security is now on the project and its users.  This makes frontend security paramount, exploits such as cross-site scripting (xss) can interact with a users wallet; presenting opportunities such as blind-signing transactions.

To provide a seamless user experience, the organisation can implement the following controls that would be invisible to users:

### Cross-Site Request Forgery (CSRF) Protection

* **Implement Stateless Authentication:** Tokens stored securely in browser memory (HttpOnly cookies or secure local storage) to avoid direct exposure. Where possible use custom headers or bearer tokens in API requests to prevent traditional CSRF attacks (which rely on automatic cookie submissions).
  * **JWT Authentication:** Include tokens in the `Authorization` header explicitly and ensure API endpoints validate JWT properly.
  * **API Request Validation:** Require custom headers to be set (e.g. `X-Requested-With`) on sensitive endpoints, further reducing the CSRF attack surface.
  * **Cookies:** 
    * *__SameSite:__* Configure cookies as `SameSite=Strict` or `SameSite=Lax` based on usability requirements, preventing cross-origin submission of authenticated requests.
    * *__Secure Flag:__* Configure cookies with the `secure` attribute; preventing transmission over unencrypted mediums.  While its easy to obtain certificates (e.g. LetsEncrypt), this provides an additional barrier/hurdle that can negate CSRF attacks.
* **Verify Origin:** Should the `Origin` header be present, this should be verified that the value matches the target origin.  Should this not be present then methods to identify the orgin could  be used, such as checking additional headers such as `Host`, `Referer` and `X-Forwarded-Host`.  

### Cross-Site Scripting (XSS) Prevention

This is one of the most dangerous attacks to a Web3 application, XSS payloads can be delivered not only via the organisations applications but any application on the internet.  For a Web3 app, XSS would be considered a critical finding.

The objective is to prevent unauthorised code execution within the users browser, this can be achieved by leveraging the following:

#### Content Security Policy (CSP)

A strict CSP should be implemented, explicitly allowing only trusted sources for scripts, styles, images, and API interactions.  It should be noted, CSP can break application functionality. As such it should be done in various stages, starting from minimal, progressing to more strict.

The CSP policy is generally set via a HTTP header, an example CSP policy is below:

```none
Content-Security-Policy: default-src 'self'; script-src 'self' https://trusted.cdn.com; style-src 'self' 'unsafe-inline'; connect-src 'self' api.website.com; object-src 'none';
```

Consideration should be given to using the `report-uri` / `report-to` CSP capabilities so blocking policies are fine-tuned before enforcement; will help avoid broken pages.

#### Input Sanitisation and Output Encoding

Any information sent from client-side should not be trusted, as such efforts should be made to verify the information is correct/benign.  These checks should be performed server-side and include the following approaches:

* **Whitelist:** Each input/parameter received should be compared against a list of permitted characters (e.g. a-z, numbers).  Any data that does not match the permitted list should be blocked and logged, an easy implementation would be to leverage RegEx's.
* **Parameterised Queries:** While this is more prevelant with SQL Injection, ensuring sufficient data escaping mechanisms are in place to provide an additional line of defense.
* **Encode All Output:**  Any data being sent to a client should be sufficiently encoded (e.g. HTML), raw data should not be permitted to be sent.  This provides additional controls and prevents attacks such as persistent XSS.
* **Leverage Modern JavaScript Frameworks:**  Frameworks such as React/Angular inherently mitigate most XSS risks through virtual DOM rendering or built-in sanitisation. 
* **Regular Patching:**  All frameworks and dependencies should be monitored for newly identified vulnerabilities and updated on a regular basis.

#### Sub-Resource Integrity (SRI)

This browser featured provides guarantees that every **external** script / stylesheet arrives unmodified, should the source system (e.g. CDN / Web Server) be compromised and malicious code injected.  The changes would be rejected, this is achieved through the use of hashing the code contents.

The following should be considered:

* **Secure Hashing:**  SHA-384+ should be used.
* Version Pinning:  SRI should be combined with a versioned URL (e.g. blah.com/v2/moo.js) to avoid silent CDN updates.
* **Logging/Alerting:**  The `securitypolicyviolation` event should be monitored, these events may signify supply-chain issues.
* **Review/Update Hashes:**  Parodically review the SRI hashes to ensure they are correct and match any newly updated code.
* **Cross-Origin Flag:** Setting `crossorigin="anonymous"` will ensure requests inherit the site's CSP scope where no credentials are leaked.

Below is an example of how SRI is implemented:

```none
<script src="https://cdn.example.com/vue@3.4.7.prod.min.js"
        integrity="sha512-2bQlft…VHUyg=="
        crossorigin="anonymous"></script>
```


### Clickjacking Protection

ClickJacking provides attackers with multiple attack vectors, ranging from general DOM issues through to XSS and the use of external IFRAMES.  Controls can be implement at multiple layers of the application, however it is recommended the first focus should be within the HTTP headers where additional script controls should be considered secondary.

The recommended methods for prevention is listed below:

* **X-Frame-Options Header:** This header controls whether a page can be placed within an IFRAME, setting the value to `X-Frame-Options: DENY` would prevent this.
* **Content Security Policy:**  It is possible to provide protections through the CSP header with the `frame-ancestors` attribute. Setting this to `none` will have a similar affect to the `DENY` option above.
* **Permission Removal:**  It is possible to control what browser functionality a web page can access.  These permissions can be controlled either at the HTTP header or within an IFRAME (`sandbox` attribute) tag.  Access to powerful API's (e.g., camera, geolocation, payment) should be restricted.
  * *__Example Header:__* The `()` indicates the feature should be disabled.

    ```none
    Permissions-Policy: camera=(), microphone=(), geolocation=(), payment=("https://widget.website.com")
    ```


An additonal approach would be to implement a JavaScript check, this check should be placed within the `<HEAD>` section of the page as it would be executed before the DOM is loaded.  This script can provide a fallback feature where older browsers may not honor modern framing directives like those explained above.

An example implementation of such a fallback script with whitelisting capabilties is shown below:

```none
(function frameGuard() {
  'use strict';

  const sameWindow = window.top === window.self;

  // Whitelist: allow embedding for explicitly trusted paths
  const allowList = [
    '/widgets/account-balance',
    '/public/charts/embed/'
  ];
  const pathAllowed = allowList.some(p => location.pathname.startsWith(p));

  if (!sameWindow && !pathAllowed) {
    try {
      // Attempt clean breakout
      window.top.location = window.self.location.href;
    } catch (e) {
      // Cross-origin restriction – fallback to safe landing
      window.location.replace('/error/frame-bust');
    }
  }
})();
```


\
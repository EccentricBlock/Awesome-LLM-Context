# Internal Threat Mitigation

# Privileged Access Management

## Core Principles

* **Principle of Least Privilege:** Ensure developers hold only the minimum rights needed for their role, elevating privileges *just in time* when required.
* **Just-In-Time Access:**
  * **Temporal Elevation:** Grant temporary, task-specific privileges via an automated ticketing workflow (e.g Okta Workflows).
  * **Task Scope:** Restrict elevations to exactly the resources and operations needed.
* **Separation of Duties:** Prevent any individual from both requesting and approving their own elevated access.
* **Okta Identity Provider Integration:**
  * **Okta Workflows:** Use Okta's approval flows to orchestrate entitlement requests and multi-factor authentication challenges.
  * **Okta Groups & Roles:** Map developer roles in Okta to fine-grained permissions in downstream systems.
* **Automatic Expiry:** Attach a default 1-hour expiry to routine elevations; extend only with explicit justification.
* **No Administrative Access By Default:**  Users are only granted developer/local user access which does not contain any special privileges.


## Permission Elevation Approach

Consideration should be given to implementing a tiered approach based on developer roles and the sensitivity of the resources they need to access. This avoids a "one size fits all" overly restrictive model that hinders productivity.

The various permission tiers are outlined below:

### **Tier 0 – Standard Developer Access**

This is the baseline, granted through standard Okta groups tied to their role (e.g., Frontend Developer, Backend Engineer). 

This includes:

* Access to code repositories (Git), build systems, testing environments.
* Limited access to non-production infrastructure via Infrastructure as Code (IaC) (read-only where possible). Changes are through Pull Requests and automated pipelines.
* Okta MFA enforced for all logins.
* \

### **Tier 1 – Elevated Dev Access (Short-Lived)**

For tasks requiring temporary access to more sensitive resources, it would be possible to leverage Okta workflows for permission granting where the developer details why they need access, list of specific resources and duration.

This tier grants:

* Just-In-Time (JIT) Access to Production Infrastructure for debugging/investigatory work, this does not include access to critical areas such as wallet operations or GDPR/PII based data.
* Database Access (Read-Only with Auditing) for debugging production issues, JIT access to read-only database replicas is permitted. All queries are logged meticulously.
* Logging Account Access (Read-Only with Auditing) for investigatory and compliance worklods.

### **Tier 2 – Critical Operations Access (Highly Restricted)**

Reserved for a very small subset of senior developers/SREs responsible for critical infrastructure changes, incident response or wallet/custody operations. 

This tier requires:

* **Multi-Person Approval:** Two or more approvers with different responsibilities required for *any* access request.
* **Stronger Authentication Factors:** Beyond MFA, consider hardware security keys (YubiKeys) and biometric verification.
* **Detailed Justification & Session Recording:** Every action taken is recorded end-to-end – screen recordings, keystrokes, commands executed.

## Monitoring Elevated Permissions

Monitoring isn't just about logging, it's about actively detecting anomalous behavior. 

The following approac could be applied:

* **Okta Audit Logs:** Centralize Okta logs in a SIEM (Splunk, Sumo Logic, Elastic Stack). Monitor for unusual login patterns, failed authentication attempts, and group membership changes.
* **PAM Solution Logging & Alerting:** Whatever PAM tool is used, it will provide its own detailed audit trail; who requested access to what resource, when, for how long, and from where. Alerts should be configured for:
  * Access requests outside of normal working hours.
  * Requests for resources they haven't previously accessed.
  * Attempts to escalate privileges repeatedly without approval.
  * Long-duration access sessions (exceeding pre-defined thresholds).
* **Infrastructure Monitoring:** Monitor cloud infrastructure logs (e.g. AWS CloudTrail) for any changes made by developers with elevated permissions. Integrate these logs into the SIEM as well.
* **Behavioral Analytics:** Leverage UEBA (User and Entity Behavior Analytics) tools to establish baselines of developer activity and detect deviations from normal behavior; potentially indicating a compromised account or malicious insider.

## Revoking Elevated Permissions

Permission revocation needs to be automated as much as possible to reduce the window for exploitation.  The following principles should be applied:

* **Time-Based Access:** PAM requests are automatically revoked after the specified duration (e.g., 4 hours, 8 hours).
* **Workflow Integration:** When a developer leaves the company or changes roles, their access is automatically updated in Okta and all PAM permissions are deprovisioned through automated scripts/playbooks.
* **Emergency Revocation:** A clearly defined process for immediately revoking access if suspicious activity is detected. This should trigger alerts to security teams and incident responders. (Ideally a "kill switch" integrated into the PAM solution.)
* **Regular Access Reviews**: Bi-annual reviews of developer permissions, particularly Tier 1 & 2, to ensure continued necessity based on current roles and responsibilities.

## Auditability

Complete auditability is paramount from a security and compliance perspective, this should include:

* **Centralized Logging:** All events (Okta logins, PAM requests, infrastructure changes) are aggregated into a single SIEM for analysis and reporting.
* **Immutable Logs:** Ensure logs are stored securely and cannot be tampered with (e.g. S3 with Object Lock or equivalent)
* **Detailed Audit Trails:** Capture as much context as possible – who requested access, why, when, what they did, and from where.
* **Regular Audits**: Conduct regular audits of the PAM system and developer permissions to ensure compliance with security policies and regulations.

## Minimizing Operational Friction

Creating overly burdensome controls can lead to developers/engineering attemting circumventing them.

* **Self-Service Portal:** Okta provide a self-service workflow portal/process that could be leveraged, this would tie into the existing technology stack.
* **Automation:** Automate as much of the workflow as possible (e.g. request approval, permission granting, and revocation).
* **Clear Documentation & Training:** Provide developers with clear instructions on how to request access and what security policies they need to follow.
* **DevOps Integration**: Integrate PAM into existing CI/CD pipelines to streamline secret management and automated provisioning of temporary credentials.

# Insider Threat Monitoring

## Core Principles

* **Data-Driven:** Leveraging Okta logs alongside other data sources for a comprehensive view of user behavior.
* **Behavioral Baseline:** Establishing normal activity patterns for each engineer to identify deviations. This is far more effective than static rule sets.
* **Automation & Orchestration:** Automating detection rules and response procedures where possible to reduce mean time to detection (MTTD) and mean time to resolution (MTTR).
* **Privacy by Design:** Implementing privacy-enhancing technologies and adhering to data minimization principles

## Key Privacy Considerations

* **Data Minimization:** Collect only the data necessary for effective monitoring. Avoid collecting PII that isn't directly relevant to security.
* **Anonymization/Pseudonymization:** After a defined retention period (e.g., 30 days), anonymize IP addresses, mask application names, and aggregate trading data as much as possible.
* **Access Controls:** Restrict access to logs and monitoring tools to authorized security personnel only. Applying role-based access control is critical.
* **Transparency:** Inform engineers about the monitoring program and the types of data collected (within legal constraints).
* **Regular Audits:** Regularly audit the monitoring system to ensure compliance with privacy policies and regulations.
* **Data Encryption:** All logs should be encrypted both in transit and at rest.
* **Legal Review**: Engage legal counsel to review the monitoring program and ensure it complies with relevant laws (e.g., GDPR).

## Key Data Sources 

### **Okta (SSO Logs)**

* *__Log Information:__* Login times, locations, IP addresses, applications accessed, MFA status, User roles/groups, successful/failed login attempts. Browser fingerprinting (limited).
* *__Purpose:__* Core behavioral analysis, identify anomalies in access patterns, detect brute-force attacks, geolocation discrepancies.
* *__Retention:__* 90 days (with anonymization after 30)
* *__Specific Privacy Considerations:__* Sensitive; PII. Strict access controls required. Anonymize IP addresses after a defined period and potentially mask application names.

### **System Logs (Servers/Databases)**

* *__Log Information:__* Access to critical systems, database queries (audited & logged – *not* content of queries, but source, destination, time), file access, changes to configurations.
* *__Purpose:__* Track actions taken within the infrastructure following authentication via Okta. Correlate with Okta events.
* *__Retention:__* 90 days (with anonymization after 30)
* *__Specific Privacy Considerations:__* Sensitive; PII. Access controls and auditing are essential.

### **Trading Platform Logs**

* *__Log Information:__* Transaction data *aggregated*, API usage, changes to trading parameters. (*Do not* log individual user transactions).
* *__Purpose:__* Detect unusual trading patterns or attempts to manipulate the platform.
* *__Retention:__* 90 days (with anonymization after 30)
* *__Specific Privacy Considerations:__* Sensitive; potentially PII depending on aggregation level. Focus on detecting systemic anomalies rather than individual user behavior.

### **Code Repositories (Git Logs)**

* *__Log Information:__* Commit history, code changes, access logs, force-push, PAT creation.
* *__Purpose:__* Monitor for suspicious code commits (e.g., attempts to disable security controls), unauthorized access to sensitive repositories.
* *R__etention:__* 365 days
* *__Specific Privacy Considerations:__* Less sensitive; focus is on identifying malicious code activity.

### **Endpoint Detection & Response (EDR)**

* *__Log Information:__* Process execution, file modifications, network connections, registry changes.
* *__Purpose:__* Detect malware or other malicious software running on engineer workstations.
* *__Retention:__* 30 days (with anonymisation after 7)
* *__Specific Privacy Considerations:__* Sensitive; PII. Requires careful configuration to minimize false positives and respect privacy.

### **Network Intrusion Detection System (NIDS)/IPS:**

* *__Log Information:__* Network traffic patterns, suspicious connections.
* *__Purpose:__* Identify unusual network activity originating from internal systems.
* *__Retention:__* 30 days (with anonymization after 7)
* *__Specific Privacy Considerations:__* Less sensitive; focus on identifying malicious network behavior.

## Specific Detection Scenarios & Response Procedures

### **Unusual Login Location/Time**

* *__Detection Logic:__* Okta logs show login from a country the engineer has *never* accessed before, or outside of normal working hours (requires establishing baseline).
* *__Response Procedure:__* 
  * Tier 1: Automated alert to security team for review. 
  * Tier 2: MFA challenge if feasible. 
  * Tier 3: Account lockout & investigation.
* *__Severity:__* High

**Accessing Sensitive Applications Outside of Role**

* *__Detection Logic:__* Engineer attempts to access an application they are not authorized for (Okta groups/roles).
* *__Response Procedure:__* 
  * Tier 1: Automated alert and logging. 
  * Tier 2: Immediate investigation by security team. Potential disabling of access based on risk assessment.
* *__Severity:__* Critical

**Rapid-Fire Failed Login Attempts (Brute Force)**

* *__Detection Logic:__* Multiple failed login attempts from the same IP address within a short timeframe (Okta logs).
* *__Response Procedure:__* 
  * Tier 1: Automated account lockout & IP block. 
  * Tier 2: Investigation to determine source and potential compromise.
* *__Severity:__* High

**Sudden Download/Exfiltration of Large Datasets**

* *__Detection Logic:__* EDR detects large amounts of data being copied to external devices or cloud storage. System logs show unusual database queries (e.g., exporting entire tables).
* *__Response Procedure:__* 
  * Tier 1: Automated alert & immediate investigation. 
  * Tier 2: Network isolation of impacted endpoint, forensic analysis.
* *__Severity:__* Critical

**Changes to Security Controls (Code Repositories)**

* *__Detection Logic:__* Code commits attempt to disable security features or modify critical configurations (Git logs).
* *__Response Procedure:__* 
  * Tier 1: Automated rollback of changes and alert to development leads/security team. 
  * Tier 2: Investigation & review by code owners.
* *__Severity:__* High

**Unusual API Usage**

* *__Detection Logic:__* Trading platform logs show a significant increase in API calls from an engineer's workstation compared to their historical baseline (aggregated data).
* *__Response Procedure:__* 
  * Tier 1: Automated alert for investigation. 
  * Tier 2: Review of API activity and potential escalation if suspicious patterns are identified.
* *__Severity:__* Medium-High

**Compromised Account Indicators**

* *__Detection Logic:__* Okta logs show login attempts following a known breach notification or phishing campaign targeting engineers. EDR detects unusual processes running on the workstation.
* *__Response Procedure:__* 
  * Tier 1: Automated MFA challenge & password reset request. 
  * Tier 2: Endpoint isolation and forensic analysis.
* *__Severity:__* High


\

\

\
# Cloud Architecture & Networking Security

# AWS Architecture Design

The overall premise for this architecture design are zero-trust principles, given that nation states have been heavily involved with cryptocurrency incidents over the last several years.  An organisation must always assume breach, as such.  Apply the "trust no-one" philosophy discussed within the application section. 

The system being hosted should be split up into defined sections, each section serves a specific purpose where assets (items of value) and their associated risks are clearly known.

## Principles

The following principles should be applied to the architecture:

* **Edge Protection:** Route 53 → CloudFront → Application Load Balancer front-stopped by *a WAF* and DDOS controls. This ensures malicious traffic is scrubbed at the edge, reducing latency for genuine traders and shielding the core VPC from volumetric DDoS or injection attempts.
* **Zero-Trust Admin Access:** There should be no VPN; engineers reach consoles and bastions through zero-trust methods where MFA based SSO with PassKey/YubiKey and device posture checks are performed.  Tools such as Okta advanced server access, Google BeyondCorp and AWS Verified Access can help facilitate.
* **Humans Do Not Touch Production:**  Production deployments/configuration should be performed as Infrastructure as Code, no-human hands should ever touch production during normal operations.

  \

## VPC Segregation Strategy

The internal environment should be segregated based on intended business function and the perceived risks, the list below outlines key subnets/VPN's that should be considered:

### Public

* **Purpose:** Expose load balancers publicly to accept HTTPS requests and route to internal resources securely.
* **Example Services:** Network Load Balancer (NLB),Application Load Balancers (ALB) and Route 53 DNS records.
* **Security Controls Overview:**
  * *__Ingress:__* Allow inbound HTTPS (port 443) only.
  * *__Web Application Firewall:__* Web application firewall protection against web attacks.
  * *__DDOS Protection:__* Protect against volumetric DDoS attacks using services like AWS Shield Advanced or Cloudlfare.
  * *__Egress:__* Restricted to internal frontend services only.

### Frontend/DMZ

* **Purpose:** Hosts frontend applications that are publicly accessible via the public subnet's load balancers but isolated from direct internet exposure.
* **Example Services:** ECS Fargate tasks running React/Next.js UI, public REST & GraphQL gateways, CDN origin endpoints.
* **Security Controls Overview:**
  * *__Ingress:__* Only from Public subnet ALB.
  * *__Stateless Containers:__* No data persistence; images pulled from signed ECR only.
  * *__No Direct Public IPs__*
  * *__Security Groups & NACLs:__* Strictly restrict outbound access.
  * *__Network Firewall Egress:__* Deep Packet Inspection (DPI) on outbound traffic; Suricata rules block C2 and crypto-jacking signatures.
  * *__IAM Roles:__* Service-linked roles with least-privilege for each service.
  * *__Logging:__* Enable detailed access logging for audit.

### Core Trading/Application

* **Purpose:** Runs core business logic including trading engines, order matching, and internal API services. Critical to platform functionality.
* **Example Services:**  ECS compute clusters for services such as order matching engine, risk management and trade validation services.
* **Security Controls Overview:**
  * *__Ingress:__* Restricted to internal load balancers only.
  * *__Network Isolation:__* No direct internet access.
  * *__IAM Roles:__* Service-linked roles with least-privilege for each service.
  * *__Encryption:__* Data in transit protected via TLS internally.
  * *__Intrusion Detection:__* AWS GuardDuty & host-based IDS/IPS integration.

### Data Feed Ingestion

* **Purpose:** Dedicated for services ingesting third-party data feeds, isolating external connections from core components.
* **Example Services:** Lambdas or ECS services ingesting any external data (e.g. price/oracles)
* **Security Controls Overview:**
  * *__Egress:__* Controlled outbound access (HTTPS/API endpoints only).
  * *__Ingress:__* Only allow responses to initiated outbound requests.
  * *__Security Groups:__* Stateful firewalling restricting communication to approved endpoints/ports.
  * *__VPC Endpoints:__* AWS PrivateLink to S3 and other necessary services (no internet traversal).
  * *__VPC Flow Logs:__* Stream logs to a central Logging account for traffic analysis.
  * *__Encryption at Rest:__* KMS managed keys/secrets; cross-account key deletion blocked by approval workflow.

### Data

* **Purpose:**  Store non-PII operational data (order history, trade analytics, configs).
* **Example Services:** Aurora MySQL/Postgres, DynamoDB tables & S3 buckets
* **Security Controls Overview:**
  * *__Automated Snapshots:__* Cross-Region replication; snapshots encrypted and shared only with DR account.
  * *__VPC Endpoints:__* Private-only, no IGW, use methods such as AWS PrivateLink to S3 and other necessary services (no internet traversal).
  * *__Activity Monitoring:__* *Database Activity Streams* sent to Security Lake or CloudTrail for behavioural analytics.

### AML/Compliance

* **Purpose:** Persist personally-identifiable information, KYC files and SAR (suspicious-activity-report) data.
* **Example Services:** Aurora MySQL/Postgres , S3 Object-Lock buckets for document evidence.
* **Security Controls Overview:**
  * *__Automated Snapshots:__* Cross-Region replication; snapshots encrypted and shared only with DR account.
  * *__Data-Classification Tags:__* Automated Macie scans label objects; use System Control Policies to prevent `s3:GetObject` without "GDPR-Justified" tag.
  * *__Audit Immutability:__* S3 Object-Lock (compliance mode) + CloudTrail Lake retention 7 years.
  * *__Encryption at Rest:__* KMS based keys for encrypting sensitive information.
  * *__Explicit Access Controls:__* RBAC enforced through AWS IAM.
  * *__Audit Logging:__* Detailed logs captured and analysed regularly.

### Custody

* **Purpose:** Hosts infrastructure critical to custody and key management, ensuring secure custody of cryptocurrency assets and keys.
* **Example Services:**  AWS Key Management Service (KMS) with Custom Key Stores and Cryptocurrency wallet infrastructure.
* **Security Controls Overview:**
  * *__Automated Snapshots:__* Cross-Region replication; snapshots encrypted and shared only with DR account.
  * *__Air-Gapped Admin:__* Boundary/TGS bastion requires quorum-approved break-glass; no direct SSH.
  * *__Access Control:__* Multi-factor and multi-tier IAM access approvals required.
  * *__Auditing:__* Comprehensive logging of all access and operations (CloudTrail).
  * *__Real-Time Alerts:__* SNS push to PagerDuty on any failed or unusual HSM decrypt attempt.
  * *__Transaction Policy Engine:__* All sign requests flow through policy: withdrawal velocity limits, multi-sig quorum.
  * *__Private Connectivity:__* No IGW; private link from Core Trading VPC only.

### Security 

* **Purpose:** Central hub for detection, logging, forensics and response tooling.
* **Example Services:** GuardDuty, Security Hub aggregators, AWS Config, SIEM and other tooling relating to security and incident response.
* **Security Controls Overview:**
  * *__Least-Privilege SCPs:__* Security account can *pull* logs but cannot assume roles back into prod, preventing counter-pivot.
  * *__Comprehensive Logging:__* Full audit trail for forensic investigation.
  * *__Access Control:__* Limited to authorised security personnel, using RBAC/IAM.
  * *__Network Isolation:__* Highly restricted subnet, limited to necessary outbound monitoring/management communications.

## Logging/Auditing

Establish a dedicated AWS account exclusively for log aggregation, ensuring separation from production and development environments to enhance security and simplify management.

### **AWS CloudTrail for Audit Logging**

Configure AWS CloudTrail to record API calls, actions taken by users, and resource access within the cryptocurrency trading platform.

* **Multi-Region Trails:** One org-wide trail per region, writing to an S3 bucket in the logging account with Object-Lock (compliance mode, 7 years).
* **Integrity validation:** Activate log file integrity validation to detect log tampering attempts.

### CloudWatch Logs and Metrics

Utilise Amazon CloudWatch Logs to capture application, infrastructure, and security logs from all frontend and backend components.

* **Subscription filters:** Stream logs securely from source accounts to the central logging account using CloudWatch Logs subscription filters.

### IAM Policies & Cross-Account Access

Implement strict IAM policies and cross-account roles to tightly control log access.

* **Least privilege principle:** Restrict log access to designated security and auditing teams only.
* **Read-only permissions:** Ensure logging resources are immutable by configuring read-only access for most users.
* **Multi-Factor Authentication:** Enable MFA-protected, time-limited sessions and record all console/API actions with AWS CloudTrail.

### Immutable Storage & Retention

* **Object-Lock:** Prevents tampering; Legal-Hold tags applied automatically for ongoing investigations.
* **Versioning & MFA-Delete:** Enabled on every log bucket; deletion requires break-glass role with hardware MFA.
* **Lifecycle Tiers:** 30 days in Standard, 90 days in Intelligent-Tiering, then Glacier Deep Archive; automatic expiration after retention period.

### Real-Time Monitoring and Alerts

Establish real-time monitoring capabilities using CloudWatch Alarms, Amazon SNS, and AWS Security Hub.

* **Automated alerts:** Configure immediate alerts for critical security events (e.g., failed login attempts, unauthorised access attempts).
* **Integration with SIEM/SOAR:** Facilitate log integration with third-party Security Information and Event Management (SIEM) tools such as Splunk or ELK for advanced analysis.
* **Anomaly Detection:** Implement anomaly detection rules using machine learning algorithms to identify potentially malicious behavior that might not be caught by traditional signature-based detection methods. Amazon GuardDuty can assist with this, but custom ML models may also be appropriate.

## Top 5 Security Controls

The following outline the most pertinent security controls.

### Identity and Access Management (IAM)

Restricting permissions ensures users and services only access resources necessary for their roles, reducing the risk of lateral movement and internal compromise.

#### Control Implementation:

* Enforce Principle of Least Privilege.
* Utilise role-based access controls (RBAC) integrated with AWS IAM.
* Utilize AWS Organizations to centrally manage policies across multiple AWS accounts if needed (separation of environments: Dev/Test/Prod).
* Enforce Multi-Factor Authentication (MFA) for *all* user access – including administrative accounts.

#### Threats Addressed:

* Privilege escalation.
* Unauthorised access to sensitive resources.

### Data Encryption at Rest & In Transit

Encrypting sensitive data reduces exposure from compromised resources or network sniffing, ensuring confidential information remains protected even during a breach event.

#### Control Implementation:

* Implement AWS KMS to manage encryption keys securely.
* All data at rest encrypted using AWS KMS CMKs (EBS, RDS, S3, DynamoDB)
* Enforce HTTPS (TLS 1.2+) communication between client-browser, frontend APIs, and backend microservices.

#### Threats Addressed:

* Data leakage from storage breaches.
* Man-in-the-middle (MITM) attacks during data transmission.

### Comprehensive Logging, Monitoring, and Incident Response

Comprehensive logging and real-time monitoring enable swift identification and reaction to security incidents, reducing Mean Time to Detect (MTTD) and Mean Time to Respond (MTTR). Effective incident response reduces the damage and impact of potential breaches or insider threats.

#### Control Implementation:

* Enable detailed logging via CloudTrail (auditing actions).
* GuardDuty for threat detection (anomaly and compromise indicators).
* Centralised log aggregation and monitoring into a dedicated logging account, using tools such as AWS Security Hub integrated with external SIEM and SOAR tools (e.g., Splunk, Elastic Security).
* Real-time alerts via Amazon SNS & CloudWatch Alarms

#### Threats Addressed:

* Undetected breaches and anomalies.
* Slow response and mitigation to security incidents.

### Network Security & Segmentation

Strong network segmentation minimises the blast radius of a breach. Properly enforced security groups and NACLs prevent attackers from easily traversing the internal network or accessing databases directly.

#### Control Implementation:

* VPC isolation into private/public/restricted subnets, with Block Public Access globally denies unintended IGW routes and public IPs.
* Security Groups and Network ACLs (NACLs) restricting inbound/outbound access based on roles and subnet purposes.
* Private connectivity (AWS PrivateLink) for internal services and APIs.

#### Threats Addressed:

* Unauthorised lateral movement.
* External access to sensitive internal infrastructure.

### Web Application Firewall (AWS WAF) and DDoS Protection

Implementing a WAF provides a layered defence against known web-based attacks. Where DDoS protection with services such as AWS Shield or Cloudflare, mitigates volumetric and sophisticated DDoS attacks, preserving service availability crucial for trading operations.

#### Control Implementation:

* AWS/Cloudflare WAF integrated with Application Load Balancers.
* Implement rate limiting and known attack pattern filtering (e.g., OWASP Top 10 mitigations).
* AWS Shield for DDoS resilience.

#### Threats Addressed:

* OWASP top 10 attacks where the most prominent would be Injection based attacks (SQL injection, XSS).
* Distributed Denial of Service (DDoS) attacks disrupting availability.

# Network Security Analysis

## Traffic Patterns Indicating Potential Security Incidents

### Unusual Traffic Volume or Spike

* Sudden surges in incoming traffic (potential DDoS attacks).
* Abrupt increase in outbound traffic (possible data exfiltration).
* Activity resembling mapping or fingerprinting of network infrastructure.

### Data Exfiltration Patterns

* Regularly timed or sustained data transfers to unknown external endpoints.
* Unexpected large outbound traffic flows, possibly indicating wallet key or sensitive data exfiltration, alert when data egress exceeds 1 GB/hour from non-whitelisted subnets.
* Sudden or persistent use of encrypted tunnels or VPN traffic, which may indicate unauthorised attempts to evade detection.
* Client-initiated WebSockets/Connections open for > 24 h with trickle outbound bytes.

### Irregular Access Patterns

* Multiple rapid login attempts (brute force credential attacks).
* High frequency of failed API authentication requests (indicative of compromised API keys).
* Traffic between between micro-services that normally never communicate or unexpected traffic ports (e.g. SMB, RDP, SSH) or from unexpected sources.
* \


## Monitoring Strategies

The following strategies could be used to identify anomalous or malicious behaviour.

### Real-Time Traffic Analysis

* Enable VPC flow logs that are sent to a SIEM and/or logging backend.
* Employ Intrusion Detection Systems (IDS), such as Suricata or Snort, integrated with rules tuned specifically for cryptocurrency-specific threats.
* Continuous network flow monitoring (NetFlow, sFlow) with anomaly detection mechanisms (ML-based network analysis tools).
* Utilise a WAF to inspect incoming requests/responses for common attacks (e.g. OWASP top 10).

### Behavioural Analysis and Anomaly Detection

* Establish baseline network behavior and detect deviations from the norm using machine learning algorithms. This can help identify compromised systems or insider threats.
* Use GuardDuty and Security Hub findings to prioritise alerts.
* Plant honey services/API-keys canary wallets; any network touch executes a SOAR "critical-breach" playbook.
* Track metrics such as failed-login rate, withdraw ratio, and per-IP dispersion to establish baselines and altert on deviation.

### Geolocation and IP/Wallet-Address Reputation Monitoring

* Enrich every auth attempt with GeoIP and ASN and log appropriately.
* Utilise threat intelligence feeds (e.g. AlienVault OTX, Recorded Future) integrated with security tooling for real-time IP address risk scoring and geographic anomaly alerts.
* Monitor sanctioned/suspicious wallet feeds such as OFAC, alert and tag account as "suspect" on identification.

### Threat Intelligence & SIEM Integration

* Automatically ingest threat feeds into WAF and Network Firewall to create dynamic blocking lists.
* Match internal logs against known bad IPs/domains in real time to identify Indicators of Compromis (IoC).
* Centralised SIEM solution (e.g. Splunk, Elastic SIEM) to correlate logs from firewalls, load balancers, WAF, API gateways, and cloud environments.


## Recommended Security Controls

The following controls are recommended to prevent the threats mentioned above:

* **Enforce Zero-Trust Principles:** Implement zero-trust access policies enforcing least privilege with a default being "deny all", combined with continuous verification.
* **Network Segmentation:** Isolate critical systems (wallets, trading engine) from less sensitive systems using VPC subnets, network access control lists (ACLs), and security groups.
* **Strict Egress Allow-List:** Outbound internet only via NAT/egress gateways with domain/IP allow-list; block mixers, Tor, new-reg domains.
* **Web Application Firewall (WAF):** Implement Cloudflare or AWS WAF to protect against web application attacks and monitor for suspicious requests.
* **Endpoint Detection and Response (EDR):** Deploy comprehensive EDR solutions (CrowdStrike, SentinelOne) to monitor endpoint behaviours, as attackers frequently pivot from endpoints into network environments.
* **Regular Security Audits & Penetration Testing:** Regularly assess the platform's network security posture through audits and penetration testing to identify vulnerabilities and weaknesses.
* **Hardware-Backed Admin Access:** Mandate FIDO2/WebAuthn for staff VPN & consoles; use Just-In-Time privilege elevation.
* **Continuous Secrets Hygiene:** Rotate secrets every 60-90 days where possible, consider binding to CIDRs/device fingerprints.  Ensure strict ACL's and encryption is enforced.
* **Dynamic Withdrawal Guardrails:** Per-user daily/velocity caps, leverage adaptive MFA for anomalies, and auto-delay high-risk transfers.
* **Isolated Wallet Infrastructure:** Place signers/HSMs in private subnets with *no* outbound internet; quorum signing + time-locked withdrawals.
* **SOAR Playbooks & Drills:** On *"suspicious-withdrawal"* or *"canary key used"* pause withdrawals, snapshot hosts, revoke tokens, and page on-call; rehearse quarterly purple-team exercises to validate security improvements.

# Multi-Account AWS Security Strategy

The following strategy centers around a highly segregated multi-account AWS environment leveraging AWS Control Tower as the core management platform and AWS Organizations to enforce consistent policies across all accounts. This approach provides isolation, limits blast radius, automates security best practices, and simplifies auditing and incident response.

## Account Governance

AWS Control Tower will be the backbone for provisioning and managing accounts while enforcing consistent policies. The following key elements would be used:

* **Landing Zone:** Establish a well-architected landing zone configured with baseline security controls (VPC setup, IAM roles, logging). Control Tower automates this process significantly reducing manual configuration errors.
* **Blueprints:** Create blueprints for each account type (e.g. trading platform, wallet/custody, data persistance). These blueprints provide pre-configured common infrastructure components with secure defaults. This ensures consistency and rapid deployment. These blueprints could incorporate:
  * *__Network Configuration:__* Predefined VPC CIDR blocks, subnet configurations adhering to security best practices.
  * *__IAM Policies:__* Least privilege access control enforced through roles based on the principle of least privilege. Regularly reviewed using IAM Access Analyzer.
  * *__Logging & Monitoring:__* CloudTrail enabled by default, config rules configured for compliance checks (e.g., encryption at rest), GuardDuty activated.
  * *__Encryption:__* Encryption at rest and in transit enforced across all accounts (KMS keys managed securely).
* **Guardrails:** Implement guardrails to prevent non-compliant actions, such as:
  * *__Prevent Public S3 Buckets:__* Blocks creation of publicly accessible S3 buckets within any account.
  * *__Restrict Resource Types:__* Prevents deployment of potentially insecure resource types (e.g., EC2 instances without proper security group configurations).
  * *__Disable or Enforce MFA on Root Accounts:__* Disable or enforce mandatory multi-factor authentication for all root accounts.
  * *__RegionGuard:__* Allow only approved GDPR-aligned regions (eu-west-2, eu-central-1).

## Account Organisation

Consideration should be given to implementing an organisational structure that is similar to the following:

* **Root OU:**
  * *__Management Account:__* Governance, billing, SCP management.


* **Security OU:**
  * *__Log Archive Account: __*Central log aggregation and long-term storage.
  * *__Security Tooling Account: __*Security monitoring, threat detection (GuardDuty, Security Hub), incident response automation.
  * *__Compliance & Audit Account:__* Independent auditing and compliance verification activities.
* **Shared Services OU:**
  * *__CI/CD Account:__* Hosted pipelines isolated from Production OU.
  * *__Networking Hub Account:__* Host Transit Gateway, NAT Gateways, central DNS and VPN endpoints.
* **Production OU:**
  * *__Trading/Platform Account:__* Hosting core services required for the business to perform (e.g. trading/data ingestion).
  * *__Wallet/Custody Account:__* Secure management of crypto wallets and private keys or any sensitive cryptographic operations.
* **Development OU:**
  * *__Staging Account:__* Pre-production testing environments.
  * *__Development Account:__* Application and infrastructure development workloads.
* Sandbox/Research OU:
  * *__Transient/Throw-Away Accounts:__* Experimentation and research projects.


## Protection Measures

The following protection measures should be implemented within the AWS environment:

### Network Segmentation 

Network segmentation is critical to limit the blast radius of potential breaches and limit lateral movement, the following measures should be applied:

#### Hub-and-Spoke Topology

* Leverage a Transit Gateway to simplify network routing between multiple VPCs across different accounts. Provides centralized management of network connectivity and allows for policy enforcement at the gateway level.


* Use VPC peering only between authorized accounts (e.g., Trading Platform <-> Custody/Wallet). Use specirfically defined access control lists (ACLs) and security groups to govern traffic flow. Avoid transitive peering where possible.
* Use security groups to enforce strict application-level micro-segmentation.

#### Subnet Configuration

* Public subnets are restricted to external-facing resources (load balancers, CloudFront).
* Private subnets are used to host All core applications and internal services without direct internet access.
* Isolated subnets will host highly sensitive workloads (cryptographic key management, PII data).

#### Traffic Inspection

* Utillise an IDS/IPS between the transit gateway and VPCs to monitor for Indicators of Compromise (IoC).
* Implement WAF and DDOS solutions for publicly facing services to identify and mitigate malicious traffic.


### Access Controls

#### **IAM Roles & Policies (Least Privilege)**

* Enforce granular IAM policies based on the principle of least privilege. No direct access from one account to another.
* Restrict accounts from performing risky actions (disabling logging, changing security settings, unauthorised region/resource deployment).
* Enforce conditions such as IP whitelisting, device security posture, and working hours for privileged access.  
* All communication should be mediated through roles that grant specific permissions only for necessary operations. AWS Organizations Service Control Policies (SCPs) will reinforce this across the entire organization.
* Continuous scanning for overly permissive policies and cross-account access with tools such as IAM Access Analyser.

#### Credential Management

* Leverage a centralised identity source such as integrating with Okta to simplify user management.
* Enforce multi-factor authentication, where possible mandate FIDO2/YubiKey.
* Temporary privilege elevation workflows for sensitive roles.
* Implement a centralised secrets management and rotation leveraging tools such as AWS Secrets Manager or HashiCorp Vault.


### Data Protection & Encryption

#### Encryption

* **Key Management:**
  * Centralized key management using KMS with strict access control policies.
  * Keys segregated per AWS account and per critical workload.
  * Strict IAM access controls on KMS keys and regular rotation policies enforced.
* **Encryption at Rest:** Implement mandatory encryption using KMS for services such as S3, RDS, DynamoDB, EBS.
* **Encryption in Transit:** Enforce TLS 1.3 where possible across all internal and external communications pathways.

#### Data Protection

* **Data Loss Prevention (DLP):** Implement DLP tools to identify and protect sensitive data within S3 buckets, databases, and other storage locations.


* **Data Residency & Compliance:** Implement data residency controls to ensure compliance with relevant regulations (e.g., GDPR, CCPA).
* **Secrets Management:**
  * Implement a centralised secrets management and rotation leveraging tools such as AWS Secrets Manager or HashiCorp Vault.
  * Enforce strict/fine-grained resource level access.
* **Backup and Disaster Recovery:** Regular, encrypted backups with automated cross-account replication to a associated DR accounts.


## Protecting Against Common Attack Vectors

This architecture addresses several common attack vectors, such as:

* **Compromised Credentials:** IAM roles and policies, MFA enforcement, PAM solution, and regular credential rotation reduce the risk of unauthorized access due to stolen or compromised credentials.
* **Lateral Movement:** Network segmentation (VPCs, peering restrictions, Transit Gateway policies) limits an attacker's ability to move laterally within the environment even if one account is compromised.
* **Data Breaches:** Encryption at rest and in transit, DLP tools, and database security measures protect sensitive data from unauthorized access or exfiltration.
* **Insider Threats:** Least privilege access control and monitoring of user activity (CloudTrail logs, GuardDuty findings) detect and prevent malicious activities by insiders.
* **Supply Chain Attacks:** Isolating the CI/CD pipeline in a separate account reduces the risk of source code compromise affecting production systems. Regularly scan dependencies for vulnerabilities.
* **DDoS Attacks:** Utilize AWS Shield and Web Application Firewall (WAF) to mitigate DDoS attacks against the trading platform frontends.


# Security Group Best Practices

## Design Approach

Designing security groups in a microservices architecture requires careful consideration to balance security, functionality, and manageability. My approach involves:

* **Immutable and Reusable Templates (IaC):** Use Infrastructure as Code (Terraform, CloudFormation) to ensure consistent, auditable, and reproducible security configurations across environments.
* **Zero-Trust / Default-Deny:** Begin every security group with *no* inbound or outbound rules; assume breach and require explicit allow-lists for every flow.
* **Deterministic Naming & Tagging:** Use a consistent pattern (<env>-<svc>-<tier>-sg) and mandatory JSON tags such as owner_email, expiry, and data_classification to ensure searchability, accountability, and lifecycle governance.
* **Role-Based Access Controls:** Use IAM roles and service-linked roles in conjunction with SGs to ensure that only authorised compute instances can attach to sensitive SGs.
* **Layered, Context-Aware Segmentation:** Group microservices logically by function or domain (e.g., authentication services, trading services, data analytics). Each group communicates only via defined, secure channels.

## Examples

The following provides some examples on how to the above principles can be applied:

### Microservice: Trading API

**Function:** Handles user trading requests; publicly accessible via ALB/NLB.

**Outbound Rules Example:** 

* Rule 1: Only allows communication to the Order Management service for order placement.
  * Destination: Order Management SG
  * Port: 8080 (HTTPS),
  * Protocol: TCP
* Rule 2: Allows sending logs to centralized logging.
  * Destination: Logging Service SG, 
  * Port: 53 (DNS), 
  * Protocol: UDP 
* Rule 3: Allows sending metrics to monitoring system.
  * Destination: Monitoring Service SG, 
  * Port: 433 (HTTPS) 
  * Protocol: TCP 

**Reasoning:**  Trading API needs only communicate with Order Management to fulfill requests and send logs/metrics. Direct access to the Wallet service is *not* required.

**Risks Mitigated:**  Prevent unauthorized access to other services; Limit impact of a Trading API compromise.


### Microservice: Order Management

**Function:** Processes orders, interacts with database.

**Outbound Rules Example:** 

* Rule 1: Only allows communication for debit/credit operations.
  * Destination: Wallet Service SG
  * Port: 8080 (HTTPS)
  * Protocol: TCP 
* Rule 2: Allows connection to the Order Management database.
  * Destination: Database SG
  * Port: 5432 (PostgreSQL)
  * Protocol: TCP 
* Rule 3: Allows sending logs to centralized logging.
  * Destination: Logging Service SG
  * Port: 514 (syslog)
  * Protocol: UDP 

**Reasoning:** Order management needs access to Wallet service for financial transactions and the database for storing order details. Direct public internet access is unnecessary.

**Risks Mitigated:** Prevent unauthorized database manipulation; Limit lateral movement if Order Management is compromised. Avoid exposing sensitive data directly to the internet.


### Microservice: Wallet Service

**Function:** Manages user wallets & crypto balances. Highly Sensitive.

**Outbound Rules Example:** 

* Rule 1: Allows sending logs.
  * Destination: Logging Service SG, 
  * Port: 514 (syslog)
  * Protocol: UDP
* Rule 2: Allows sending transactions to the chain.
  * Destination: Blockchain Nodes SG
  * Port: 8545 (JSON-RPC) 
  * Protocol: TCP 

**Reasoning:** Wallet service is primarily a data store and needs minimal outbound connections to broadcast a transaction.

**Risks Mitigated:** Prevent unauthorized external communication; Detect potential exfiltration attempts.

## Auditing and Maintaining Security Groups Over Time

Security groups are *not* "set it and forget it". Ongoing maintenance is critical. The methodology outlined below focuses on automation, continuous monitoring, and regular reviews:

* **IaC Version Control:** All security group definitions will be managed as code in a version control system (Git). This provides audit history, rollback capabilities, and facilitates collaborative changes.
* **Change Management:** Every change goes through peer-reviewed merge requests (version controlled) with Integration into CI/CD pipelines to automate compliance/security checks before deployment.
* Automated Scanning & Reporting: Use AWS Trusted Advisor, AWS Config rules or third-party tools (e.g. Prowler) weekly to detect overly permissive SGs.
* **Continuous Monitoring:** Enable VPN flow logs for all VPCs; ingest into SIEM for anomaly detection (e.g., unexpected outbound DNS queries).
* **Alerting:** Trigger on new SG creation, rule additions, or suddenly allowed ports.
* **Tagging and Metadata Hygiene:** Enforce manditory tags such as Service, Environment, Owner, ApprovalDate. 
* **Periodic Manual Audits:** Conduct regular internal audits to verify compliance with established least-privilege rules.  Automated reminders should be created to tag owners when SGs approach 90 days since creation or last review.
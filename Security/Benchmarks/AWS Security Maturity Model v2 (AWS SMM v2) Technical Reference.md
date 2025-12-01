
# AWS Security Maturity Model v2 (SMM v2) Technical Reference

## 1. Purpose and Scope

The AWS Security Maturity Model v2 (AWS SMM v2) is a comprehensive framework designed to guide organisations in structuring, prioritising, and accelerating their security journey on AWS. It serves as a risk-reduction mechanism by categorising security controls into prescriptive phases, moving beyond binary "secure/insecure" assessments toward a roadmap of continuous improvement.

The model aligns strictly with the AWS Cloud Adoption Framework (CAF) Security Perspective and the AWS Shared Responsibility Model. It structures security implementation into four distinct phases of maturity—Phase 1 (Quick Wins), Phase 2 (Foundational), Phase 3 (Efficient), and Phase 4 (Optimised)—and groups technical practices into ten security capability domains. This document serves as an authoritative technical reference for implementation.

---

## 2. Conceptual Model

### 2.1 Relationship to AWS CAF and Shared Responsibility

AWS SMM v2 operationalises the high-level directives of the AWS CAF Security Perspective. While CAF defines the "what" (organisational capabilities such as Governance, People, and Technology), SMM v2 defines the "how" and "when" (tactical sequencing of controls).

The model addresses the customer's side of the Shared Responsibility Model—**Security in the Cloud**. Implementation of SMM v2 mandates that the organisation takes ownership of configuration, data protection, and access management, while validating that AWS (Security **of** the Cloud) meets compliance requirements via assurance mechanisms. Maturity within this model implies a deepening of **preventive**, **detective**, **responsive**, and **governance** controls across all AWS accounts and workloads.


#### Phase 1 – Quick Wins
* **Objective:** Establish immediate risk reduction with minimal engineering effort.
* **Focus:** High-impact, low-Complexity controls that address the most critical security hygiene issues.
* **Typical Risk Profile:** Without Phase 1, the environment is susceptible to account compromise, root user abuse, and unintentional public data exposure.
* **Exit Criteria:** Root account secured, MFA enforced, public access blocked, and basic threat detection (GuardDuty) enabled.

#### Phase 2 – Foundational
* **Objective:** Establish baselines, standardisation, and centralisation.
* **Focus:** Transitioning from manual actions to managed guardrails (SCPs), centralised logging, and initial secret management.
* **Typical Risk Profile:** Lack of standardisation leads to configuration drift and "shadow IT" risks.
* **Exit Criteria:** Multi-Account strategy (AWS Organizations) in place, centralised logs, encryption at rest defaults, and defined incident response playbooks.

#### Phase 3 – Efficient
* **Objective:** Integration of security into engineering workflows (DevSecOps).
* **Focus:** Automation, Infrastructure as Code (IaC), "shifting left", and proactive threat modelling.
* **Typical Risk Profile:** Security becomes a bottleneck to velocity; manual reviews fail to scale with workload growth.
* **Exit Criteria:** Security controls deployed via IaC pipelines, automated vulnerability management, and regular tabletop exercises.

#### Phase 4 – Optimised
* **Objective:** Continuous improvement and data-Driven operations.
* **Focus:** Advanced automation, self-healing infrastructure, zero trust architectures, and proactive adversarial simulation (Red Teaming).
* **Typical Risk Profile:** Sophisticated threats may bypass static controls; lack of dynamic response capability.
* **Exit Criteria:** Automated remediation of configuration drift, zero trust network access, and chaotic engineering practices for resiliency.

### 2.3 Security Capability Domains

AWS SMM v2 groups activities into ten security capability domains that correspond closely to the AWS CAF Security perspective capabilities.  Expectations in each domain increase from Phase 1 to Phase 4:

* **Security Governance:** The strategy, roles, and structural controls (regions, accounts) governing the environment. Evolves from assigning contacts to automated account factories.
* **Security Assurance:** Mechanisms to validate compliance and posture. Evolves from static CSPM checks to continuous, automated evidence gathering.
* **Identity and Access Management (IAM):** Control of principals and permissions. Evolves from MFA and federation to fine-grained Attribute-Based Access Control (ABAC) and Data Perimeters.
* **Threat Detection:** Identification of potential security events. Evolves from basic GuardDuty alerts to custom correlation in Security Lake/SIEM.
* **Vulnerability Management:** Identification and remediation of software flaws. Evolves from ad-hoc patching to automated pipelines and bug bounties.
* **Infrastructure Protection:** Network and compute security. Evolves from security groups to Zero Trust architectures.
* **Data Protection:** Encryption and privacy controls. Evolves from S3 block public access to advanced DLP and GenAI protection.
* **Application Security:** Securing code and logic. Evolves from WAF to full DevSecOps integration and threat modelling.
* **Incident Response:** Reacting to security events. Evolves from manual triage to automated remediation and orchestration.
* **Resiliency:** ability to recover from failure. Evolves from backups to multi-region active-Active architectures.

---

## 3. Canonical AWS SMM v2 Taxonomy (Authoritative List)

The following tables list the official AWS SMM v2 activities by phase and security capability domain. These are the canonical titles for each control/activity, as provided by AWS, and they form the basis for the deep dives in subsequent sections.

### 3.1 Phase 1: Quick Wins

| **Security Capability Domain (Phase 1)** | **Activities (Phase 1 – Quick Wins)**                                                                                                                |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security governance (SG1)**            | **SG1.1** Assign Security contacts<br>**SG1.2** Select the region(s) to use and block the rest                                                       |
| **Security assurance (SA1)**             | **SA1.1** Evaluate Cloud Security Posture (CSPM)                                                                                                     |
| **Identity and access management (IA1)** | **IA1.1** Multi-Factor Authentication<br>**IA1.2** Root Account Protection<br>**IA1.3** Identity Federation<br>**IA1.4** Cleanup unintended accesses |
| **Threat detection (TD1)**               | **TD1.1** Detect Common Threats<br>**TD1.2** Audit API calls<br>**TD1.3** Billing alarms                                                             |
| **Vulnerability management (VM1)**       | N/A                                                                                                      |
| **Infrastructure protection (IP1)**      | **IP1.1** Cleanup risky open ports                                                                                                                   |
| **Data protection (DP1)**                | **DP1.1** Block Public Access<br>**DP1.2** Analyse data security posture                                                                             |
| **Application security (AS1)**           | **AS1.1** WAF with managed rules                                                                                                                     |
| **Incident response (IR1)**              | **IR1.1** Act on Critical Security Findings                                                                                                          |
| **Resiliency (RS1)**                     | **RS1.1** Evaluate Resilience                                                                                                                        |
### 3.2 Phase 2: Foundational

| **Security Capability Domain (Phase 2)** | **Activities (Phase 2 – Foundational)**                                                                                                                    |
| ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security governance (SG2)**            | **SG2.1** Identify security and regulatory requirements<br>**SG2.2** Cloud Security Training Plan                                                          |
| **Security assurance (SA2)**             | **SA2.1** Inventory & Configuration monitoring                                                                                                             |
| **Identity and access management (IA2)** | **IA2.1** GuardRails: Organisational Policies with SCPs/RCPs<br>**IA2.2** Use Temporary Credentials<br>**IA2.3** Instance Metadata Service (IMDS) v2       |
| **Threat detection (TD2)**               | **TD2.1** Advanced Threat Detection                                                                                                                        |
| **Vulnerability management (VM2)**       | **VM2.1** Manage infrastructure vulnerabilities<br>**VM2.2** Manage application vulnerabilities                                                            |
| **Infrastructure protection (IP2)**      | **IP2.1** Limit Network Access<br>**IP2.2** Secure EC2 Instances Management<br>**IP2.3** Network segmentation (VPCs)<br>**IP2.4** Multi-Account management |
| **Data protection (DP2)**                | **DP2.1** Data Encryption at rest<br>**DP2.2** Backups<br>**DP2.3** Discover sensitive data                                                                |
| **Application security (AS2)**           | **AS2.1** Involve security teams in development<br>**AS2.2** No secrets in code                                                                            |
| **Incident response (IR2)**              | **IR2.1** Define incident response playbooks                                                                                                               |
| **Resiliency (RS2)**                     | **RS2.1** Redundancy using multiple Availability Zones                                                                                                     |

### 3.3 Phase 3: Efficient

| **Security Capability Domain (Phase 3)** | **Activities (Phase 3 – Efficient)**                                                                                                               |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security governance (SG3)**            | **SG3.1** Design your secure architecture<br>**SG3.2** Use infrastructure as code<br>**SG3.3** Tagging strategy                                    |
| **Security assurance (SA3)**             | **SA3.1** Create your compliance reports                                                                                                           |
| **Identity and access management (IA3)** | **IA3.1** Least Privilege Review<br>**IA3.2** Customer IAM: security of your customers                                                             |
| **Threat detection (TD3)**               | **TD3.1** Custom Threat Detection capabilities (SecLake / SIEM)                                                                                    |
| **Vulnerability management (VM3)**       | **VM3.1** Security Champions Program<br>**VM3.2** DevSecOps: Security in the Pipeline                                                              |
| **Infrastructure protection (IP3)**      | **IP3.1** Image Generation Pipeline<br>**IP3.2** Anti-Malware / EDR / Runtime Protection<br>**IP3.3** Outbound Traffic Control                     |
| **Data protection (DP3)**                | **DP3.1** Encryption in transit                                                                                                                    |
| **Application security (AS3)**           | **AS3.1** Perform threat modeling<br>**AS3.2** WAF with custom rules<br>**AS3.3** Advanced DDoS Mitigation (L7)                                    |
| **Incident response (IR3)**              | **IR3.1** Run TableTop Exercises – Simulations<br>**IR3.2** Automate Critical Playbooks<br>**IR3.3** Security Investigations – Root cause analysis |
| **Resiliency (RS3)**                     | **RS3.1** Disaster Recovery Plan                                                                                                                   |

### 3.4 Phase 4: Optimised

| **Security Capability Domain (Phase 4)** | **Activities (Phase 4 – Optimised)**                                                                                                                                                                      |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security governance (SG4)**            | **SG4.1** Sharing security work and responsibility                                                                                                                                                        |
| **Security assurance (SA4)**             | **SA4.1** Automate Evidence Gathering                                                                                                                                                                     |
| **Identity and access management (IA4)** | **IA4.1** IAM Data Perimeters<br>**IA4.2** IAM Policy Generation Pipeline<br>**IA4.3** Temporary Elevated Access                                                                                          |
| **Threat detection (TD4)**               | **TD4.1** Threat Intelligence<br>**TD4.2** Network Flows analysis (VPC Flow Logs)                                                                                                                         |
| **Vulnerability management (VM4)**       | **VM4.1** Vulnerability Management Team                                                                                                                                                                   |
| **Infrastructure protection (IP4)**      | **IP4.1** Zero Trust Access<br>**IP4.2** Use abstract services                                                                                                                                            |
| **Data protection (DP4)**                | **DP4.1** GenAI Data protection                                                                                                                                                                           |
| **Application security (AS4)**           | **AS4.1** Forming a Red Team (Attacker’s Point of View)                                                                                                                                                   |
| **Incident response (IR4)**              | **IR4.1** Forming a Blue Team (Incident Response)<br>**IR4.2** Advanced security automations<br>**IR4.3** Security Orchestration & Ticketing<br>**IR4.4** Automate deviation correction in configurations |
| **Resiliency (RS4)**                     | **RS4.1** Multi-region Disaster Recovery Automation<br>**RS4.2** Chaos Engineering                                                                                                                        |

## 4. Phase-By-Capability and Activity Deep Dive
### 4.1 Phase 1 – Quick Wins
#### 4.1.1 Security Governance

##### SG1.1 Assign Security Contacts

  * **Objective:** Ensure that AWS can contact the correct technical stakeholders regarding security notifications, abuse reports, or billing anomalies, rather than relying solely on the root account email.
  * **Recommended practices (checklist):**
    1.  SG1.1-A: You MUST configure the 'Alternate Contacts' for Security, Billing, and Operations in the AWS Account Management Console for every account or via the delegated administrator in AWS Organizations.
    2.  SG1.1-B: You SHOULD use distribution lists (e.g., `aws-security@example.com`) rather than individual email addresses to ensure continuity during personnel changes.
    3.  SG1.1-C: You MUST verify the email address used is valid and monitored.

##### SG1.2 Select the region(s) to use and block the rest

  * **Objective:** Reduce the attack surface and ensure data residency compliance by technically restricting the deployment of resources to authorized AWS Regions only.
  * **Recommended practices (checklist):**
    1.  SG1.2-A: You MUST define a list of allowed regions for your organisation.
    2.  SG1.2-B: You MUST disable unused regions in the AWS Account Management console where possible (for regions introduced after March 2019, this is default).
    3.  SG1.2-C: You MUST apply a Service Control Policy (SCP) via AWS Organizations to deny all actions in non-Approved regions.
    4.  SG1.2-D: You SHOULD configure AWS Config aggregators or equivalent inventory tooling to verify that no resources exist in non-Approved Regions, and treat any such resources as incidents.

-----

#### 4.1.2 Security Assurance

##### SA1.1 Evaluate Cloud Security Posture (CSPM)

  * **Objective:** Establish continuous visibility into the security configuration of the environment against industry benchmarks and best practices.
  * **Recommended practices (checklist):**
    1.  SA1.1-A: You MUST enable AWS Security Hub in all used regions and designate a Delegated Administrator account.
    2.  SA1.1-B: You MUST enable the "AWS Foundational Security Best Practices" (FSBP) standard.
    3.  SA1.1-C: You SHOULD enable the "CIS AWS Foundations Benchmark" standard.
    4.  SA1.1-D: You MUST enable AWS Config (a prerequisite for Security Hub) to record all resources.
    4.  SA1.1-D: You SHOULD configure Security Hub to aggregate findings from GuardDuty, Macie, Inspector, and other integrated products into the central security account.
    5.  SA1.1-E: You MAY integrate a third-party CSPM solution using read-only cross-Account roles where additional analytics, dashboarding, or risk scoring are required.    

-----

#### 4.1.3 Identity and Access Management

##### IA1.1 Multi-Factor Authentication

  * **Objective:** Prevent credential compromise from leading to account takeover by requiring a second factor for authentication for all human users.
  * **Recommended practices (checklist):**
    1.  IA1.1-A: You MUST enforce MFA for the root user immediately.
    2.  IA1.1-B: You MUST enforce MFA for all IAM Users with console access (if IAM users are still in use).
    3.  IA1.1-C: You MUST enforce MFA for all federated users accessing via AWS IAM Identity Center.
    4.  IA1.1-D: You SHOULD minimise or eliminate IAM users for humans, preferring IdP-Backed SSO sessions with MFA, and treat any remaining IAM users as exceptions with compensating controls.

##### IA1.2 Root Account Protection

  * **Objective:** Secure the most privileged identity in the AWS account, which cannot be restricted by IAM policies.
  * **Recommended practices (checklist):**
    1.  IA1.2-A: You MUST NOT create access keys for the root user.
    2.  IA1.2-B: You MUST use a strong, complex, random password for the root user and store it in a privileged access management (PAM) vault or physical safe.
    3.  IA1.2-C: You MUST attach an SCP to the AWS Organization root or OUs that denies the usage of the root user (except for specific root-only tasks).
    4.  IA1.2-D: You MUST ensure there are no active access keys for the root user; any existing keys MUST be deleted immediately.
    5.  IA1.2-E: You MUST configure CloudTrail and EventBridge to detect and alert on any root activity (for example userIdentity.type = "Root" events) in real time.

##### IA1.3 Identity Federation

  * **Objective:** Eliminate the use of long-term IAM User credentials by implementing centralised identity management.
  * **Recommended practices (checklist):**
    1.  IA1.3-A: You SHOULD enable AWS IAM Identity Center (formerly AWS SSO).
    2.  IA1.3-B: You SHOULD integrate IAM Identity Center with your corporate Identity Provider (IdP) (e.g., Entra ID, Okta, Ping) via SAML 2.0 and SCIM.
    3.  IA1.3-C: You MUST use Permission Sets to map job functions to AWS permissions, avoiding direct IAM User creation.
    4.  IA1.3-D: You SHOULD configure session durations, MFA requirements, and device posture policies in the IdP appropriate to the sensitivity of AWS access.
    5.  IA1.3-E: You MAY use additional IAM conditions (for example aws:PrincipalOrgID, aws:PrincipalTag) to restrict role assumption paths to your IdP and approved accounts.

##### IA1.4 Cleanup unintended accesses

  * **Objective:** Minimise the blast radius by removing unused roles, users, and permissions (principle of least privilege hygiene).
  * **Recommended practices (checklist):**
    1.  IA1.4-A: You MUST enable IAM Access Analyzer to identify resources shared externally.
    2.  IA1.4-B: You SHOULD regularly review the IAM Credential Report and delete IAM users/roles that have not authenticated in \>90 days.
    3.  IA1.4-C: You MUST delete default VPCs if they are not intended for use, to prevent accidental deployment into public subnets.
    4.  IA1.4-D: You SHOULD identify and refactor overly permissive IAM policies (for example `Action: "*"`, `Resource: "*"`) into least-privilege policies, starting with highly privileged roles.

-----

#### 4.1.4 Threat detection

##### TD1.1 Detect Common Threats

  * **Objective:** Enable intelligent threat detection to identify compromised instances, account reconnaissance, and unusual data access.
  * **Recommended practices (checklist):**
    1.  TD1.1-A: You MUST enable Amazon GuardDuty in all regions and accounts.
    2.  TD1.1-B: You SHOULD designate a Delegated Administrator for GuardDuty to centralise findings.
    3.  TD1.1-C: You SHOULD configure notification and ticketing workflows (for example EventBridge + SNS/ChatOps + ticketing system) for high and critical GuardDuty findings.
    4. TD1.1-D: You SHOULD tune GuardDuty findings where necessary (for example whitelisting known-good scanners) while avoiding broad suppression of high-severity types.
    5. TD1.1-E: You MAY enable Amazon Detective in the central security account to support investigation of GuardDuty and other findings for moderate and high-risk environments.

##### TD1.2 Audit API calls

  * **Objective:** Ensure full traceability of actions taken against the AWS control plane for forensic investigation and compliance.
  * **Recommended practices (checklist):**
    1.  TD1.2-A: You MUST configure at least one organisation-wide AWS CloudTrail organisation trail that captures all management events in all Regions and delivers them to a central, encrypted S3 bucket in a log-Archive account.
    2.  TD1.2-B: You MUST enable Log File Validation on the CloudTrail definition to prove immutability.
    3.  TD1.2-C: You SHOULD store CloudTrail logs in a centralised, immutable S3 bucket (locked with Object Lock/WORM compliance mode) in a separate Log Archive account.
    4.  TD1.2-D: You MAY configure additional trails or event selectors for high-value resources (e.g. data event logging for specific S3 buckets or Lambda functions) as needed.
##### TD1.3 Billing alarms

  * **Objective:** Detect potential account compromise (e.g., crypto-jacking) via unexpected spikes in infrastructure cost.
  * **Recommended practices (checklist):**
    1.  TD1.3-A: You MUST configure AWS Budgets to alert administrators when forecasted spend exceeds a defined threshold (e.g., 120% of last month).
    2.  TD1.3-B: You SHOULD enable AWS Cost Anomaly Detection to automatically identify unusual spending patterns.
    3.  TD1.3-C: You MUST ensure alerts are routed to a distribution list that includes security personnel.
    4.  TD1.3-D: You SHOULD define a simple runbook for investigating billing anomalies, including checking GuardDuty, CloudTrail, and workload metrics.

-----

#### 4.1.5 Infrastructure Protection

##### IP1.1 Cleanup Risky Open Ports

  * **Objective:** Prevent unauthorized network access to compute resources by eliminating exposure of management ports to the internet.
  * **Recommended practices (checklist):**
    1.  IP1.1-A: You MUST identify all security groups and network controls that permit 0.0.0.0/0 access to high-risk ports (e.g. 22, 3389, database ports) and remove or tighten these rules.
    2.  IP1.1-B: You SHOULD use AWS Security Hub, AWS Config, or equivalent queries to continuously detect internet-Exposed ports and track remediation.
    3.  IP1.1-C: You MUST ensure that administrative access to instances (SSH/RDP) is brokered through controlled mechanisms (e.g. VPN, SSM Session Manager, or bastions) instead of direct public exposure.

-----

#### 4.1.6 Data Protection

##### DP1.1 Block Public Access

  * **Objective:** Prevent accidental data leaks caused by misconfigured S3 bucket permissions.
  * **Recommended practices (checklist):**
    1.  DP1.1-A: You MUST enable "Block Public Access" (BPA) at the Account level for all accounts.
    2.  DP1.1-B: You MUST identify existing publicly accessible S3 buckets and either remediate them or document and approve them under strict controls.
    3.  DP1.1-C: You SHOULD use AWS Config and Security Hub controls to monitor for S3 public access and track drift from the desired state.
    4.  DP1.1-D: You SHOULD ensure that public content delivery uses CloudFront or similar, with origin access control, rather than directly exposing buckets.


##### DP1.2 Analyse Data Security Posture

  * **Objective:** Discover where sensitive data resides and identify external exposure.
  * **Recommended practices (checklist):**
    1.  DP1.2-A: You SHOULD enable and configure basic data discovery tools (e.g. Amazon Macie for S3) for high-value buckets where feasible.
    2.  DP1.2-B: You MUST review the S3 permission settings within the Amazon S3 console or Security Hub to identify buckets with authenticated broad read access.
    3.  DP1.2-C: You MUST identify and catalogue key data stores (S3 buckets, RDS instances, DynamoDB tables, etc.) that contain or are likely to contain sensitive data.
    4.  DP1.2-D: You SHOULD ensure that encryption at rest is enabled for high-value data stores, using AWS-managed or customer-managed KMS keys.
    5.  DP1.2-E: You MAY define simple data classification tags (e.g. `DataClassification=Confidential`) and apply them to high-sensitivity resources for future policy enforcement.


-----

#### 4.1.7 Application Security

##### AS1.1 WAF With Managed Rules

  * **Objective:** Protect public-facing web applications from common exploits (OWASP Top 10) without requiring deep security expertise.
  * **Recommended practices (checklist):**
    1.  AS1.1-A: You MUST deploy AWS WAF (Web Application Firewall) on all public-facing Application Load Balancers (ALBs), API Gateways, and CloudFront distributions.
    2.  AS1.1-B: You MUST enable the "AWS Managed Rules - Common Rule Set.
    3.  AS1.1-C: You SHOULD enable the "AWS Managed Rules - Amazon IP Reputation list.
    4.  AS1.1-D: You SHOULD implement simple rate limiting or bot control rules for high-risk endpoints (e.g. login, authentication APIs).


-----

#### 4.1.8 Incident Response

##### IR1.1 Act on Critical Security Findings

  * **Objective:** Ensure that high-severity security signals are not ignored and result in human intervention.
  * **Recommended practices (checklist):**
    1.  IR1.1-A: You MUST establish a process to route findings rated "Critical" or "High" from Security Hub/GuardDuty to a ticketing system (Jira/ServiceNow) or instant messaging channel (Slack/Teams).
    2.  IR1.1-B: You MUST define a Service Level Agreement (SLA) for acknowledging and remediating critical findings (e.g., acknowledge within 1 hour, fix within 24 hours).
    3.  IR1.1-C: You MUST define ownership for responding to critical security findings (e.g. a cloud security on-Call role) and document responsibilities.

-----

#### 4.1.9 Resiliency

##### RS1.1 Evaluate Resilience

  * **Objective:** Understand the current recovery capabilities of workloads to determine if they meet business requirements.
  * **Recommended practices (checklist):**
    1.  RS1.1-A: You SHOULD capture simple availability and recovery objectives (e.g. RTO/RPO) for critical systems, even if informal.
    2.  RS1.1-A: You MUST identify critical workloads and document their current resilience characteristics (e.g. AZ usage, region usage, backup status).
    3.  RS1.1-C: You MUST verify that backups (snapshots, automated backups) exist for critical data stores and are retained for a minimum period aligned to business needs.
    4.  RS1.1-D: You MAY use Config, tagging, and reports to highlight resources that are clear single points of failure (e.g. single-instance production workloads).

### 4.2 Phase 2 – Foundational

#### 4.2.1 Security Governance

##### SG2.1 Identify Security and Regulatory Requirements

* **Objective:** Establish a compliance baseline by mapping business obligations to specific technical controls within the cloud environment.
* **Recommended practices:**
    1.  **SG2.1-A:** You MUST identify applicable regulatory frameworks (e.g., GDPR, PCI-DSS, HIPAA) and internal security policies.
    2.  **SG2.1-B:** You SHOULD map these requirements to specific AWS configuration rules (e.g., using AWS Config conformance packs or Security Hub standards).
    3.  **SG2.1-C:** You SHOULD implement a resource tagging strategy that supports data classification and compliance tracking (e.g., `ComplianceScope=PCI`).
    4.  SG2.1-D: You MUST create and maintain a central register of applicable requirements (e.g. SOC 2, ISO 27001, PCI DSS, GDPR, local regulations) and explicitly scope which AWS systems and data are in-scope for each.

##### SG2.2 Cloud Security Training Plan

* **Objective:** Ensure engineering and security teams possess the necessary skills to operate the cloud environment securely.
* **Recommended practices:**
    1.  **SG2.2-A:** You SHOULD define role-Based security training paths for developers, operators, and auditors.
    2.  **SG2.2-B:** You SHOULD encourage or require key staff to obtain relevant AWS certifications (e.g., AWS Certified Security – Specialty).
    3.  **SG2.2-C:** You MAY supplement formal training with practical labs or game days that exercise guardrails, detection, and incident response workflows in AWS.
    4.  SG2.2-D: You SHOULD implement periodic refresher training (at least annually) focusing on real incidents, common misconfigurations, and changes to AWS guardrails and standards.

#### 4.2.2 Security Assurance

##### SA2.1 Inventory & Configuration Monitoring

* **Objective:** maintain a complete, historical record of resource configurations to detect drift and facilitate forensic analysis.
* **Recommended practices:**
    1.  **SA2.1-A:** You MUST enable AWS Config in all in-scope accounts and approved regions, with configuration items recorded for all relevant resource types.
    2.  **SA2.1-B:** You SHOULD deploy AWS Managed Rules for AWS Config to enforce compliance with the governance requirements identified in SG2.1.
    3.  **SA2.1-C:** You MUST configure one or more AWS Config aggregators to centralise configuration and compliance data into a security/audit account for organisation-wide visibility.

#### 4.2.3 Identity and Access Management

##### IA2.1 GuardRails: Organisational Policies with SCPs/RCPs

* **Objective:** Implement coarse-grained preventive controls at the organisation level to stop users from performing prohibited actions, regardless of their IAM permissions.
* **Recommended practices:**
    1.  **IA2.1-A:** You MUST apply Service Control Policies (SCPs) to the Organization Root or OUs to deny critical risks (e.g., disabling CloudTrail, leaving the Organization, modifying billing contacts).
    2.  **IA2.1-B:** You SHOULD apply Resource Control Policies (RCPs) to enforce data perimeters on supported resources (e.g., restricting S3 bucket access to organisation principals only).
    3.  **IA2.1-C:** You MUST implement a baseline set of SCPs that enforce non-negotiable controls (e.g. deny non-Approved regions, deny disabling CloudTrail/Config/Security Hub, deny creating access keys for the root user).
    4.  IA2.1-D: You SHOULD adopt Control Tower or equivalent to manage core guardrails (e.g. mandatory logging, configuration recording) consistently across accounts.

##### IA2.2 Use Temporary Credentials

* **Objective:** Eliminate the risk of long-term credential theft by relying on short-lived, rotatable credentials.
* **Recommended practices:**
    1.  **IA2.2-A:** You MUST use IAM Roles for all compute resources (EC2, Lambda, ECS) rather than embedding long-term access keys in code or configuration files.
    2.  **IA2.2-B:** You SHOULD require the use of `AssumeRole` for cross-Account access.
    3.  **IA2.2-C:** You SHOULD define maximum session durations and re-Authentication requirements for high-privilege roles to limit exposure from compromised sessions.
    4.  IA2.2-D: You SHOULD implement policies and checks that prohibit creation of new long-lived access keys for human users and restrict service accounts to tightly scoped roles.


##### IA2.3 Instance Metadata Service (IMDS) v2

* **Objective:** Mitigate Server-Side Request Forgery (SSRF) attacks by enforcing session-oriented access to EC2 instance metadata.
* **Recommended practices:**
    1.  **IA2.3-A:** You MUST configure new EC2 launch templates/launch configurations to require IMDSv2 only and to disable IMDS entirely for instances that do not need it.
    2.  **IA2.3-B:** You SHOULD set the hop limit to 1 for containerised workloads to prevent containers from accessing the host instance role credentials, unless specifically required.
    3.  **IA2.3-C:** You SHOULD use organisational guardrails (e.g. Control Tower, Config rules, or policy checks in IaC pipelines) to prevent deployment of instances that allow IMDSv1.
    4.  IA2.3-D: You MAY monitor CloudTrail and Config for changes to instance metadata options and treat unapproved relaxations (e.g. re-Enabling IMDSv1) as policy violations.

#### 4.2.4 Threat Detection

##### TD2.1 Advanced Threat Detection

* **Objective:** Expand detection capabilities beyond basic log analysis to identify sophisticated attack patterns and anomalous behaviour.
* **Recommended practices:**
    1.  **TD2.1-A:** You MUST ensure GuardDuty is enabled organisation-wide with all relevant data sources (CloudTrail, VPC Flow Logs, DNS logs, EKS audit logs where applicable) and that coverage includes all approved regions and accounts.
    2.  **TD2.1-B:** You MUST integrate GuardDuty and other native detections (e.g. Inspector findings, Macie alerts) into a central aggregation point (Security Hub, SIEM, or Security Lake) with consistent severity mappings.
    3.  **TD2.1-C:** You SHOULD integrate Amazon EventBridge with GuardDuty to trigger automated notifications or basic remediation functions (e.g., isolating an instance).
    4.  TD2.1-D: You SHOULD perform regular tuning of high-noise findings (e.g. allow-lists, suppression rules, or tagging) while documenting rationale and ensuring that truly risky events are not suppressed.
    5.  TD2.1-E: You MAY begin collecting and centralising additional telemetry (e.g. VPC Flow Logs, ALB logs, WAF logs) into log analytics platforms to support more advanced correlation in later phases.

#### 4.2.5 Vulnerability Management

##### VM2.1 Manage Infrastructure Vulnerabilities

* **Objective:** Automatically detect and patch operating system vulnerabilities to reduce the exploit surface.
* **Recommended practices:**
    1.  **VM2.1-A:** You MUST enable Amazon Inspector (EC2 scanning) to automatically detect CVEs and network exposure on instances.
    2.  VM2.1-B: You MUST define remediation SLAs for Infrastructure vulnerabilities by severity (e.g. Critical/High MUST be remediated within X days) and assign ownership to teams.
    3.  **VM2.1-C:** You SHOULD use AWS Systems Manager (SSM) Patch Manager to define and automate patching schedules (Maintenance Windows).
    4.  **VM2.1-D:** You SHOULD standardise on hardened base images (e.g. through an image pipeline) and ensure that patching is performed regularly via automation (SSM Patch Manager, image rebuilds, or configuration management).
    5.  VM2.1-E: You MAY use tags or resource groups to scope scanning and reporting to specific environments (prod/non-prod) and to support exception handling for legacy systems.

##### VM2.2 Manage Application Vulnerabilities

* **Objective:** Identify vulnerabilities in application dependencies and container images before they are exploited.
* **Recommended practices:**
    1.  **VM2.2-A:** You MUST implement software composition analysis (SCA) for key languages and package managers used in your applications and integrate it into CI pipelines to detect vulnerable dependencies.
    2.  **VM2.2-B:** You MAY establish simple “security quality gates” in CI (e.g. build fails if new Critical vulnerabilities are introduced) and enforce them at least for production-Bound branches.
    3.  VM2.2-C: You SHOULD implement static application security testing (SAST) for critical services, at least on main branches, and triage findings into actionable defects.
    4.  **VM2.2-D:** You MUST establish a process to block the deployment of artefacts containing "Critical" severity vulnerabilities.

#### 4.2.6 Infrastructure Protection

##### IP2.1 Limit Network Access

* **Objective:** Reduce the blast radius of network intrusions by enforcing strict ingress and egress filtering.
* **Recommended practices:**
    1.  **IP2.1-A:** You MUST define standardised security group patterns (e.g. web tier, app tier, data tier) and require that all workloads use these patterns rather than ad hoc rules.
    2.  **IP2.1-B:** You MUST restrict inbound internet access to a minimal set of entry points (e.g. load balancers, API gateways) and prohibit direct public ingress to back-End services.
    3.  **IP2.1-C:** You SHOULD avoid using the 'default' VPC and 'default' Security Groups; create custom VPCs and empty default security groups.
    4.  IP2.1-D: You MAY implement AWS Network Firewall or equivalent controls for inspection of traffic to and from sensitive network segments.

##### IP2.2 Secure EC2 Instances Management

* **Objective:** Ensure administrative access to compute resources is authenticated, authorised, and audited without exposing network ports.
* **Recommended practices:**
    1.  **IP2.2-A:** You MUST use controlled access mechanisms (e.g. SSM Session Manager, VPN plus bastion) for managing EC2 instances and MUST NOT rely on direct SSH/RDP from the public internet.
    2.  **IP2.2-B:** You MUST ensure that all EC2 instances run with appropriate IAM roles and that interactive logins use individual or auditable identities (not shared keys).
    3.  IP2.2-C: You SHOULD standardise on hardened AMIs and configuration baselines (e.g. via image pipelines, configuration management, or SSM).
    4.  IP2.2-D: You SHOULD configure SSM inventory, patching, and compliance features to track patch status and configuration drift across the instance fleet.
    5.  IP2.2-E: You MAY disable SSH/RDP completely for some classes of workloads and rely solely on automated deployment and SSM for operations.

##### IP2.3 Network Segmentation (VPCs)

* **Objective:** Isolate workloads based on environment and sensitivity to contain breaches.
* **Recommended practices:**
    1.  **IP2.3-A:** You MUST separate production and non-production workloads into distinct VPCs (and preferably distinct accounts).
    2.  IP2.3-B: You MUST control connectivity between VPCs (and to on-premises or other clouds) using peering, Transit Gateway, or private link mechanisms with explicit route and security group controls.
    3.  **IP2.3-C:** You SHOULD design VPCs with public subnets (for external load balancers/NAT) and private subnets (for compute/databases).
    4.  IP2.3-D: You SHOULD adopt a standard VPC design (CIDR strategy, subnets, routing patterns) and enforce its use via IaC modules and account vending pipelines.
    5.  **IP2.3-E:** You MUST route egress traffic from private subnets through NAT Gateways or Egress-Only Internet Gateways, preventing direct internet addressing.
    6.  IP2.3-f: You MAY restrict or eliminate direct internet egress from sensitive VPCs, routing outbound traffic via central egress points with filtering.

##### IP2.4 Multi-Account Management

* **Objective:** Use the AWS account as a strong isolation boundary for security, billing, and limits.
* **Recommended practices:**
    1.  **IP2.4-A:** You MUST place all AWS accounts under a single AWS Organization with centrally managed guardrails and security services.
    2.  **IP2.4-B:** You SHOULD implement a Landing Zone strategy (e.g., using AWS Control Tower) to vend standardized accounts.
    3.  **IP2.4-C:** You MUST define account categories (e.g. security, logging, shared services, workload accounts) and ensure that each account has a clear purpose and owner.
    4.  IP2.4-D: You SHOULD provision new accounts via an account vending process (e.g. Control Tower Account Factory or IaC automation) that applies baseline configurations automatically.
    5.  IP2.4-E: You SHOULD restrict cross-Account access to least privilege and use resource-Based policies and IAM roles rather than sharing credentials.
    6.  IP2.4-f: You MAY implement a standard naming and tagging convention for accounts (and their resources) to support reporting, cost allocation, and automated policy targeting.

#### 4.2.7 Data Protection

##### DP2.1 Data Encryption at Rest

* **Objective:** Protect data confidentiality if physical media is accessed or if volume snapshots are leaked.
* **Recommended practices:**
    1.  **DP2.1-A:** You MUST enable encryption at rest for all supported managed data services (e.g. S3, RDS, EBS, DynamoDB, EFS, OpenSearch) by default in IaC baselines.
    2.  **DP2.1-B:** You MUST define key management policies for customer-managed KMS keys (e.g. rotation, access control, alias conventions) and assign clear key ownership.
    3.  **DP2.1-C:** You SHOULD use AWS Config rules and Security Hub controls to detect unencrypted resources and track remediation.
    4.  DP2.1-D: You MAY segregate keys by environment, system, or data classification to limit the impact of key compromise and simplify access reviews.

##### DP2.2 Backups

* **Objective:** Ensure business continuity and recovery capability in the event of data corruption or ransomware.
* **Recommended practices:**
    1.  **DP2.2-A:** You MUST identify all critical data stores and define RPO/RTO targets that drive backup frequency and retention policies.
    2.  **DP2.2-B:** You MUST configure automated backups and/or snapshots for these data stores (e.g. RDS automated backups, EBS snapshots, DynamoDB backups) and store them in durable, encrypted locations.
    3.  **DP2.2-C:** You SHOULD use AWS Backup or equivalent tooling to manage backup policies centrally across accounts and services.
    4.  DP2.2-D: You SHOULD perform periodic restore tests (at least annually per critical system) to validate that backups are usable and that recovery procedures work as expected.
    5.  DP2.2-E: You MAY use cross-Account and/or cross-region backup strategies for high-value systems to protect against account or regional compromise.

##### DP2.3 Discover Sensitive Data

* **Objective:** Maintain visibility of sensitive data locations to apply appropriate controls.
* **Recommended practices:**
    1.  **DP2.3-A:** You MUST define data classification levels (e.g. Public, Internal, Confidential, Highly Confidential) and document examples relevant to your workloads.
    2.  **DP2.3-B:** You MUST identify key data stores likely to contain sensitive data and prioritise them for automated discovery and classification.
    3.  DP2.3-C: You SHOULD enable tools such as Amazon Macie (for S3) or equivalent scanners for higher-risk buckets and review high-severity findings promptly.
    4.  DP2.3-D: You SHOULD tag resources that contain sensitive data with classification tags and use those tags to drive additional guardrails (e.g. encryption, logging, access controls).
    5.  DP2.3-E: You MAY integrate data discovery results with your risk register or GRC tooling to track remediation of misplacements or overexposed data.

#### 4.2.8 Application Security

##### AS2.1 Involve Security Teams in Development

* **Objective:** Integrate security considerations early in the software development lifecycle (Shift Left).
* **Recommended practices:**
    1.  **AS2.1-A:** You MUST define criteria for when security review is required (e.g. new internet-facing services, changes handling sensitive data, significant architectural changes) and enforce it via existing change processes.
    2.  AS2.1-B: You MUST ensure that security reviews produce concrete, tracked actions (e.g. Jira tickets) rather than informal feedback, and that these are resolved before go-live or within agreed timeframes.
    3.  **AS2.1-C:** You SHOULD establish a process for developers to request security guidance without bureaucratic friction.
    4.  AS2.1-D: You SHOULD embed security representatives into key product or platform teams (e.g. as virtual team members or “security champions”) to improve collaboration and reduce friction.
    5.  AS2.1-E: You MAY create lightweight security design templates or threat modelling checklists that teams MUST complete for new services above a defined risk threshold.

##### AS2.2 No Secrets in Code

* **Objective:** Prevent credential leakage by decoupling secrets from application code and version control.
* **Recommended practices:**
    1.  **AS2.2-A:** You MUST prohibit storing secrets in source control and enforce this via policy, developer education, and automated secret scanning tools on repositories and pipelines.
    2.  AS2.2-B: You MUST use dedicated secret management services (e.g. AWS Secrets Manager, SSM Parameter Store with encryption) to store secrets used by applications and infrastructure automation.
    3.  **AS2.2-C:** You SHOULD use pre-Commit hooks (e.g., `git-secrets`, `trufflehog`) to scan local repositories for accidental secret commits.
    4.  **AS2.2-D:** You SHOULD define rotation policies for critical secrets (e.g. database credentials, third-party API keys) and automate rotation where supported.

#### 4.2.9 Incident Response

##### IR2.1 Define Incident Response Playbooks

* **Objective:** Ensure a consistent, repeatable response to common security incidents to minimise mean time to resolution (MTTR).
* **Recommended practices:**
    1.  **IR2.1-A:** You MUST define at least a small set of playbooks for high-likelihood/high-impact scenarios (e.g. compromised IAM credentials, public S3 bucket with sensitive data, GuardDuty crypto-mining finding).
    2.  IR2.1-B: You SHOULD store playbooks in a version-Controlled repository or central knowledge base and review them at least annually or after relevant incidents.
    3. IR2.1-C: You MAY run table-top exercises or small-scale simulations of these playbooks to validate that they are practical and that responders are familiar with them.
    4.  **IR2.1-D:** You MUST document clear roles, responsibilities, and decision points in each playbook, including when to escalate to management, legal, or communications.

#### 4.2.10 Resiliency

##### RS2.1 Redundancy Using Multiple Availability Zones

* **Objective:** Protect workloads against data centre failures by distributing resources across isolated fault domains.
* **Recommended practices:**
    1.  **RS2.1-A:** You MUST ensure that production load-Balanced services (e.g. behind ALBs, NLBs, API Gateways) are deployed across at least two AZs in each region where they run.
    2.  **RS2.1-B:** You MUST configure managed data services (e.g. RDS, DynamoDB, OpenSearch) to use multi-AZ or equivalent high-Availability configurations where supported and justified by criticality.
    3.  **RS2.1-C:** You SHOULD avoid single-instance EC2 deployments for critical workloads and instead use auto scaling groups or at least pairs of instances spread across AZs.
    4.  RS2.1-D: You SHOULD validate that AZ-Aware routing and health checks (e.g. in load balancers, DNS) correctly fail over when an AZ or component becomes unavailable.
    5.  RS2.1-E: You MAY include AZ-failure scenarios in resilience testing and assess whether observed behaviour meets agreed availability objectives.

### 4.3 Phase 3 – Efficient

#### 4.3.1 Security Governance

##### SG3.1 Design Your Secure Architecture

* **Objective:** Standardise security patterns and enforce architectural decisions that align with the organisation's risk appetite before deployment.
* **Recommended practices:**
    1.  **SG3.1-A:** You MUST create reference architectures for common workload types (e.g. internet-facing web apps, internal services, data platforms) covering accounts, VPCs, IAM, logging, and key security services.
    2.  **SG3.1-B:** You MUST require new production workloads to conform to an approved reference architecture or obtain a documented exception approved by security and architecture owners.
    3.  **SG3.1-C:** You SHOULD maintain architecture diagrams and decision records for critical systems in a version-Controlled repository, updated as part of the change process.
    4.  SG3.1-D: You MAY align reference architectures with an internal cloud “design review” process, making conformance a prerequisite for go-live.

##### SG3.2 Use Infrastructure as Code

* **Objective:** Eliminate configuration drift and enable automated security scanning of infrastructure prior to provisioning.
* **Recommended practices:**
    1.  **SG3.2-A:** You MUST define all production infrastructure using declarative code (e.g., AWS CloudFormation, Terraform, AWS CDK).
    2.  **SG3.2-B:** You MUST restrict write access to the AWS Console in production environments, ensuring changes are only applied via the CI/CD pipeline.
    3.  **SG3.2-C:** You MUST require that all changes to production infrastructure flow through version-Controlled IaC repositories with code review and CI/CD pipelines.
    4.  SG3.2-D: You SHOULD implement automated validation in pipelines (linting, policy-As-Code, security scanning) to catch misconfigurations before deployment.
    5.  SG3.2-E: You MAY automatically reconcile drift by detecting resources that diverge from IaC and either remediating them or failing builds until they are brought back into alignment.

##### SG3.3 Tagging Strategy

* **Objective:** Enable granular cost allocation, security automation, and operational ownership through consistent metadata.
* **Recommended practices:**
    1.  **SG3.3-A:** You MUST define a minimal mandatory tag set (e.g. `Owner`, `System`, `Environment`, `Criticality`, `DataClassification`) and publish it as a formal standard.
    2.  **SG3.3-B:** You MUST enforce mandatory tags on new resources via IaC modules, tag policies, or pipeline checks, at least for production and regulated environments.
    3.  **SG3.3-C:** You SHOULD automate the remediation or reporting of untagged resources using AWS Config.
    4.  SG3.3-D: You MAY periodically run tag hygiene campaigns to fix legacy resources, using automated reports and bulk-tagging tools where safe.

#### 4.3.2 Security Assurance

##### SA3.1 Create Your Compliance Reports

* **Objective:** Streamline the generation of audit evidence and view the organisation's compliance status against chosen frameworks.
* **Recommended practices:**
    1.  **SA3.1-A:** You MUST define which controls and frameworks (e.g. SOC 2, ISO 27001, internal policies) require AWS evidence and map each control to specific data sources (e.g. Security Hub, Config, CloudTrail, IAM reports).
    2.  **SA3.1-B:** You MUST automate extraction of core evidence artefacts (e.g. Config compliance summaries, Security Hub findings, IAM credential reports) into a central evidence store with timestamps.
    3.  SA3.1-C: You SHOULD standardise evidence formats and locations so that auditors and internal stakeholders can retrieve them consistently without ad hoc requests.
    3.  **SA3.1-D:** You MAY generate tailored reports from Security Hub to demonstrate control effectiveness to stakeholders.

#### 4.3.3 Identity and Access Management

##### IA3.1 Least Privilege Review

* **Objective:** Systematically reduce permissions granted to principals based on actual historical usage patterns.
* **Recommended practices:**
    1.  **IA3.1-A:** You SHOULD use IAM Access Analyzer "policy generation" to create fine-grained policies based on CloudTrail activity.
    2.  **IA3.1-B:** You MUST perform periodic reviews (at least annually, preferably more frequently for high-privilege roles) of IAM policies and roles using usage data (e.g. Access Analyzer, last accessed data, CloudTrail).
    3.  **IA3.1-C:** You SHOULD implement a process where permissions are initially broad in lower environments (Dev) but strictly scoped in Production based on observed behaviour.
    4.  IA3.1-D: You SHOULD implement an approvals and change process for creating or modifying high-privilege roles, including explicit justification and expiry/review dates.

##### IA3.2 Customer IAM: Security of Your Customers

* **Objective:** Segregate workforce identities from customer identities to prevent privilege escalation and lateral movement.
* **Recommended practices:**
    1.  **IA3.2-A:** You MUST NOT manage customer identities (end-users of your application) within AWS IAM; you MUST use a dedicated Customer IAM (CIAM) solution like Amazon Cognito or an external OIDC provider.
    2.  **IA3.2-B:** You SHOULD enable advanced security features for customer identities, such as adaptive authentication or compromised credential detection.
    3.  **IA3.2-C:** You MUST ensure customer JWTs (JSON Web Tokens) are validated on the server-side (e.g., via API Gateway Authorizers or ALB OIDC integration).
    4.  IA3.2-D: You SHOULD monitor and log cross-Account accesses associated with customer integrations (e.g. AssumeRole calls) and be able to trace actions back to specific customers and purposes.

#### 4.3.4 Threat Detection

##### TD3.1 Custom Threat Detection Capabilities (SecLake / SIEM)

* **Objective:** Centralise security telemetry from AWS and non-AWS sources to correlate events and detect complex, multi-vector attacks.
* **Recommended practices:**
    1.  **TD3.1-A:** You MUST centralise relevant logs (e.g. CloudTrail, VPC Flow Logs, DNS logs, WAF, ALB, application logs, GuardDuty/Inspector/Macie findings) into a security data platform (e.g. Security Lake, SIEM, or log analytics stack).
    2.  **TD3.1-B:** You MUST define and implement a core library of custom detection rules (detection-As-Code) covering key threats relevant to your environment (e.g. suspicious assume-role patterns, unusual data exfiltration, rare API usage).
    3.  **TD3.1-C:** You SHOULD measure and tune detection quality (e.g. false-positive/false-negative rates, alert volume, mean time to acknowledge) and adjust rules based on incident learnings.
    4.  TD3.1-D: You MAY integrate detection outputs with enrichment sources (e.g. asset inventory, tags, threat intelligence) to improve triage context and prioritisation.

#### 4.3.5 Vulnerability Management

##### VM3.1 Security Champions Program

* **Objective:** Scale security culture by embedding security knowledgeable engineers within development squads.
* **Recommended practices:**
    1.  **VM3.1-A:** You MUST identify at least one security champion per significant product or platform team, with clear responsibilities and time allocation agreed with their managers.
    2.  VM3.1-B: You MUST provide champions with targeted training and guidance (e.g. secure coding, AWS guardrails, incident response) and access to security tooling and dashboards.
    3.  **VM3.1-C:** You SHOULD empower Champions to approve low-risk security decisions or pull requests.
    4.  VM3.1-D: You SHOULD involve champions in risk assessments, threat modelling, and prioritisation of security backlog items for their teams.
    5.  VM3.1-E: You MAY recognise and reward effective champion contributions (e.g. through performance feedback or internal awards) to sustain engagement.

##### VM3.2 DevSecOps: Security in the Pipeline

* **Objective:** Detect vulnerabilities in code and dependencies before they are deployed to infrastructure.
* **Recommended practices:**
    1.  **VM3.2-A:** You MUST integrate core security tooling (e.g. SCA, SAST, IaC scanning, container image scanning) into CI pipelines for critical services and infrastructure.
    2.  **VM3.2-B:** You MUST define and enforce minimal security gates (e.g. blocking builds that introduce new Critical/High vulnerabilities without an approved exception) for production-Bound branches.
    3.  **VM3.2-C:** You SHOULD configure the pipeline to fail the build if vulnerabilities exceeding a defined severity threshold are detected.
    4.  VM3.2-D: You MAY use policy-As-Code tools (e.g. Open Policy Agent, conftest, custom validators) to enforce organisational rules in pipelines (e.g. disallowing certain AWS services or configurations).

#### 4.3.6 Infrastructure Protection

##### IP3.1 Image Generation Pipeline

* **Objective:** Automate the creation of hardened, patched Machine Images (AMIs) or Container Images to ensure consistency.
* **Recommended practices:**
    1.  **IP3.1-A:** You MUST implement an image pipeline (e.g. EC2 Image Builder, Packer plus CI) for generating standard base AMIs and container base images used across workloads.
    2.  **IP3.1-B:** You MUST apply security hardening baselines (e.g. OS configuration, disabling unnecessary services, agent installation) within the image pipeline rather than per-instance.
    3.  **IP3.1-C:** You SHOULD integrate vulnerability scanning into the image pipeline and fail builds that contain unpatched Critical/High vulnerabilities without approved exceptions.
    4.  IP3.1-D: You SHOULD version, tag, and document images (including changelogs) so that workloads can be pinned to known-good versions and rolled forward/back as needed.
    5.  IP3.1-E: You MAY deprecate and block use of non-standard or outdated images via IaC validation and/or Config rules.

##### IP3.2 Anti-Malware / EDR / Runtime Protection

* **Objective:** Detect and stop malicious code execution or file manipulation at the operating system level.
* **Recommended practices:**
    1.  **IP3.2-A:** You MUST select and deploy a standard EDR/runtime protection solution for applicable compute types (e.g. EC2, containers, Kubernetes nodes) in production environments.
    2.  **IP3.2-B:** If required by compliance (e.g., PCI-DSS), you MUST install File Integrity Monitoring (FIM) and Anti-Virus (AV) software.
    3.  **IP3.2-C:** You SHOULD ensure agents report telemetry to the central SIEM or Security Hub.
    4.  IP3.2-D: You SHOULD define response procedures for common EDR alerts (e.g. suspected malware, privilege escalation) including isolation/quarantine steps.
    5.  IP3.2-E: You MAY tune policies per environment (e.g. stricter blocking in production, more permissive in dev) while maintaining a consistent global baseline.

##### IP3.3 Outbound Traffic Control

* **Objective:** Prevent data exfiltration and Command & Control (C2) communication by filtering egress traffic.
* **Recommended practices:**
    1.  **IP3.3-A:** You MUST restrict outbound internet access for sensitive workloads using security groups, network ACLs, and/or central egress patterns (e.g. NAT gateways plus firewall).
    2.  **IP3.3-B:** You MUST avoid blanket `0.0.0.0/0` egress where possible and define tighter rules (e.g. specific CIDR ranges, endpoints, or VPC endpoints for AWS services).
    3.  **IP3.3-C:** You SHOULD use DNS filtering, network firewalls, or proxies to enforce domain-level allow/block lists for key environments.
    4.  IP3.3-D: You SHOULD log and periodically review outbound connections (e.g. via VPC Flow Logs, firewall logs) for anomalous or unauthorised destinations.
    5.  IP3.3-E: You MAY require sensitive workloads to reach internet services only through explicit VPC endpoints or private connectivity rather than public IPs.

#### 4.3.7 Data Protection

##### DP3.1 Encryption in Transit

* **Objective:** Protect data integrity and confidentiality while moving between clients and services.
* **Recommended practices:**
    1.  **DP3.1-A:** You MUST enforce TLS 1.2 or higher for all public endpoints (ALB, CloudFront, API Gateway).
    2.  **DP3.1-B:** You MUST use S3 Bucket Policies to deny requests that do not use HTTPS (`aws:SecureTransport` condition).
    3.  DP3.1-C: You MUST encrypt internal service-to-service traffic for critical systems where technically feasible (e.g. mutual TLS, TLS for database connections).
    4.  **DP3.1-D:** You SHOULD use AWS Certificate Manager (ACM) to auto-renew and manage public and private TLS certificates.
    5.  DP3.1-E: You MAY implement automated checks (e.g. scanners, Config rules, pipeline tests) to detect non-TLS endpoints or insecure configurations and block their deployment.

#### 4.3.8 Application Security

##### AS3.1 Perform Threat Modeling

* **Objective:** Identify design flaws and logic vulnerabilities that automated scanners cannot detect.
* **Recommended practices:**
    1.  **AS3.1-A:** You MUST perform threat modelling for high-risk systems (e.g. internet-facing, sensitive data, critical business processes) at design time and on major changes.
    2.  **AS3.1-B:** You MUST document identified threats, assumptions, and selected mitigations in a repeatable format and store them with system architecture artefacts.
    3.  AS3.1-C: You SHOULD review threat models periodically and after major incidents to ensure they reflect current reality and lessons learnt.
    4.  AS3.1-D: You MAY derive detection and test cases from threat models (e.g. attack simulations, chaos experiments) to validate that mitigations are effective.

##### AS3.2 WAF with Custom Rules

* **Objective:** Defend against application-specific attacks (e.g., business logic abuse) not covered by managed rule sets.
* **Recommended practices:**
    1.  AS3.2-A: You MUST identify critical endpoints and patterns that require custom WAF protections (e.g. login, transaction APIs, admin interfaces) based on risk and threat models.
    2.  **AS3.2-B:** You SHOULD implement rate-Based rules to mitigate brute force login attempts or API scraping.
    3.  **AS3.2-C:** You MAY implement WAF Bot Control to manage automated traffic.
    4.  AS3.2-D: You MAY integrate WAF rule hits into detection pipelines (e.g. correlation with GuardDuty, authentication logs) to identify attack campaigns and inform further rule improvements.

##### AS3.3 Advanced DDoS Mitigation (L7)

* **Objective:** Protect application availability against sophisticated Layer 7 floods and resource exhaustion attacks.
* **Recommended practices:**
    1.  **AS3.3-A:** You MUST enable baseline DDoS protections for critical public endpoints (e.g. AWS Shield Standard by default; consider Shield Advanced for higher-risk assets).
    2.  **AS3.3-B:** You MUST define and document DDoS response procedures, including tuning WAF rate-Based rules, adjusting scaling policies, and engaging provider support where applicable.
    3.  **AS3.3-C:** You SHOULD use rate limiting, CAPTCHA/bot control, and adaptive throttling on high-risk endpoints (e.g. login, search) to protect back-End resources.
    4.  AS3.2-D: You SHOULD monitor key metrics (latency, error rates, request volume, WAF block counts) and establish alerting thresholds for potential DDoS conditions.

#### 4.3.9 Incident Response

##### IR3.1 Run TableTop Exercises – Simulations

* **Objective:** Validate playbooks and train the team through simulated security incidents.
* **Recommended practices:**
    1.  **IR3.1-A:** You MUST schedule regular table-top exercises (at least annually) for cloud-related scenarios involving key stakeholders (security, engineering, operations, leadership).
    2.  **IR3.1-B:** You MUST design scenarios that reflect realistic AWS incidents (e.g. compromised credentials, misconfigured S3 bucket, destructive API calls) and test end-to-End response.
    3.  IR3.1-C: You SHOULD capture lessons learned and concrete improvement actions from each exercise and track them to completion.
    4.  IR3.1-D: You SHOULD vary scenarios over time to cover different services, teams, and attack paths, avoiding repetition.

##### IR3.2 Automate Critical Playbooks

* **Objective:** Reduce reaction time for high-severity events by automating containment actions.
* **Recommended practices:**
    1.  **IR3.2-A:** You MUST implement automation (e.g. EventBridge → Lambda/SSM/Step Functions) for at least a small set of high-impact actions, with clear approval and rollback mechanisms.
    2.  **IR3.2-B:** You MUST identify candidate playbooks for automation (e.g. isolating compromised instances, disabling credentials, blocking IPs) based on frequency and risk.
    3.  **IR3.2-C:** You SHOULD integrate automated actions with ticketing and communication tools so that responders have full visibility of what has been executed.

##### IR3.3 Security Investigations – Root Cause Analysis

* **Objective:** Enable deep-Dive forensics to understand the scope and method of a breach.
* **Recommended practices:**
    1.  **IR3.3-A:** You MUST perform RCAs for material security incidents (e.g. data exposure, significant compromise, major control failure) within a defined timeframe after resolution.
    2.  **IR3.3-B:** You MUST document incident timelines, contributing factors, root causes, and agreed corrective actions in a central repository.
    3.  IR3.3-C: You SHOULD include representatives from impacted teams, security, and leadership in RCA reviews to ensure buy-in on outcomes.
    4.  IR3.3-D: You MAY anonymise and share key learnings across the organisation to improve awareness and prevent recurrence.

#### 4.3.10 Resiliency

##### RS3.1 Disaster Recovery Plan

* **Objective:** Prepare for region-wide failures or data destruction events with a tested recovery strategy.
* **Recommended practices:**
    1.  **RS3.1-A:** You MUST identify workloads that require formal DR planning and document their DR strategies (e.g. active–active, warm standby, backup-And-restore) and required RTO/RPO values.ads.
    2.  **RS3.1-B:** You MUST describe concrete recovery procedures for each critical workload (e.g. how to recreate infrastructure in another region/account, restore data, flip traffic) and store them in an accessible lo
    3.  RS3.1-C: You SHOULD test DR plans periodically (e.g. partial or full failover exercises) and record results, issues, and improvements.
    4.  RS3.1-D: You SHOULD ensure that DR requirements are reflected in IaC and automation (e.g. secondary region templates, replicated data, cross-region backups) rather than purely manual runbooks.

### 4.4 Phase 4 – Optimised

#### 4.4.1 Security Governance 

##### SG4.1 Sharing Security Work and Responsibility

* **Objective:** Democratise security ownership by empowering development teams to own the security risks of their services, moving the central security team into a governance and consulting role.
* **Recommended practices:**
    1.  **SG4.1-A:** You MUST define a cloud security RACI that assigns ownership for guardrails, detections, incident response, and remediation between central security, platform, and product teams.
    2.  **SG4.1-B:** You SHOULD embed security objectives (e.g. reduction of High findings, compliance scores, time-to-remediate) into team OKRs/KPIs and review them regularly at engineering governance forums.
    3.  **SG4.1-C:** You SHOULD provide self-service security capabilities (e.g. reusable IaC modules, CI security templates, dashboards) so product teams can implement and monitor controls without constant security team intervention.
    4.  SG4.1-D: You MAY run periodic “security ownership” reviews to rebalance responsibilities as the AWS estate and team structure evolve.

#### 4.4.2 Security Assurance

##### SA4.1 Automate Evidence Gathering

* **Objective:** Achieve continuous audit readiness by replacing manual evidence collection with real-time API-Driven verification.
* **Recommended practices:**
    1.  **SA4.1-A:** You MUST define an evidence catalogue that lists required artefacts per control (e.g. Config rules, Security Hub summaries, CloudTrail queries, IAM reports) and their extraction methods.
    2.  **SA4.1-B:** You MUST implement scheduled jobs (e.g. Lambda, Step Functions, CI pipelines) that pull evidence from AWS services (Config, Security Hub, CloudTrail, IAM, Backup, Organizations) and store it in a tamper-resistant evidence repository
    3.  SA4.1-C: You SHOULD standardise evidence formats (e.g. JSON exports, CSV reports, signed PDFs) and naming conventions to make cross-period comparisons and audits straightforward.
    4.  SA4.1-D: You SHOULD track evidence freshness (e.g. timestamps, versioning) and surface staleness in dashboards so that controls with outdated evidence can be refreshed automatically.


#### 4.4.3 Identity and Access Management

##### IA4.1 IAM Data Perimeters

* **Objective:** Construct a robust data perimeter that ensures trusted identities are accessing trusted resources from trusted networks only.
* **Recommended practices:**
    1.  **IA4.1-A:** You MUST implement Resource Control Policies (RCPs) and VPC Endpoint Policies that strictly limit access to principals belonging to your AWS Organization (`aws:PrincipalOrgID`).
    2.  **IA4.1-B:** You SHOULD use Service Control Policies (SCPs) to prevent data exfiltration by denying actions (e.g., `s3:PutObject`) to resources outside the organisation's perimeter.
    3.  **IA4.1-C:** You SHOULD tag sensitive resources consistently and use tag-Based conditions in IAM and resource policies to scope access by classification and tenant.
    4.  IA4.1-D: You SHOULD use IAM Access Analyzer and custom checks to validate that resource policies do not inadvertently break data perimeter assumptions.

##### IA4.2 IAM Policy Generation Pipeline

* **Objective:** Automate the creation of least-privilege policies based on code analysis or pre-production activity, removing human error from policy authoring.
* **Recommended practices:**
    1.  **IA4.2-A:** You SHOULD integrate tools (e.g., IAM Access Analyzer Policy Generation or client-side scanning) into the CI/CD pipeline to suggest policies based on the application code (e.g., analysing boto3 calls).
    2.  **IA4.2-B:** You SHOULD treat IAM policies as code, with versioning, peer review, and change history, and avoid in-Console editing of policies in production accounts.
    3.  IA4.2-C: You SHOULD support automatic or semi-Automatic tightening of policies over time (e.g. removing unused actions) based on observed usage, subject to approval.
    4.  IA4.2-D: You MAY expose a self-service interface (e.g. internal portal or CLI) where teams can request access profiles and receive generated, reviewable IAM policy snippets that conform to organisational standards.

##### IA4.3 Temporary Elevated Access

* **Objective:** Remove all standing privileges for sensitive operations, requiring Just-In-Time (JIT) access requests.
* **Recommended practices:**
    1.  **IA4.3-A:** You MUST implement a "break-glass" or JIT mechanism (e.g., via AWS IAM Identity Center or a custom portal) where operators request elevated roles for a specific time window.
    2.  **IA4.3-B:** You MUST require approvals (e.g. via ITSM or chat-Based workflows) and documented justification before granting elevated access for production environments.
    3.  **IA4.3-C:** You SHOULD automate the revocation of access immediately after the task is complete or the window expires.
    4.  IA4.3-D: You MAY implement automated reviews of elevated access usage (e.g. weekly reports) to detect abuse, unusual patterns, or unnecessary elevation requests.

#### 4.4.4 Threat Detection

##### TD4.1 Threat Intelligence

* **Objective:** Proactively defend against known adversaries by integrating external threat data into detection logic.
* **Recommended practices:**
    1.  **TD4.1-A:** You SHOULD activate Amazon GuardDuty Threat Intelligence features to use AWS-managed threat lists.
    2.  **TD4.1-B:** You SHOULD upload custom trusted threat intelligence feeds (STIX/TAXII) to GuardDuty or your SIEM to detect indicators of compromise (IoCs) specific to your industry.
    3.  **TD4.1-C:** You SHOULD focus on high-Confidence, high-relevance intelligence (e.g. sector-specific or cloud-targeted campaigns) and avoid flooding systems with low-quality feeds.
    4.  TD4.1-D: You SHOULD map intelligence reporting to MITRE ATT&CK or similar frameworks and use it to drive new or improved detection rules in your Security Lake/SIEM.
    5.  TD4.1-E: You MAY establish feedback loops where incidents and investigations feed back into curated internal intelligence that informs future rules and engineering controls.

##### TD4.2 Network Flows Analysis (VPC Flow Logs)

* **Objective:** Analyse network telemetry for deep forensic visibility and detection of subtle traffic anomalies.
* **Recommended practices:**
    1.  **TD4.2-A:** You MUST ingest VPC Flow Logs into a solution capable of analytics (e.g., Amazon Athena, Amazon OpenSearch Service, or a partner SIEM), not just storage.
    2.  **TD4.2-B:** You SHOULD apply retention and partitioning strategies so that flow data remains queryable for meaningful forensic windows without excessive cost.
    3.  **TD4.2-C:** You SHOULD use automated analysis to detect "beaconing" behaviour or long-Duration connections indicative of C2 channels.
    4.  TD4.2-D: You MAY use flow analysis to validate and tune network segmentation (e.g. detect unexpected lateral movement paths or unused allowed paths) and feed these insights back into IP controls.

#### 4.4.5 Vulnerability Management

##### VM4.1 Vulnerability Management Team

* **Objective:** Establish a strategic function dedicated to managing the lifecycle of vulnerabilities, moving beyond simple patching to risk-Based prioritisation.
* **Recommended practices:**
    1.  **VM4.1-A:** You MUST define and enforce Service Level Agreements (SLAs) for remediation based on vulnerability severity (e.g., Criticals < 24 hours).
    2.  **VM4.1-B:** You MUST establish a vulnerability management function with defined roles (e.g. scanning owner, triage lead, remediation coordinators) and representation from security, platform, and key product teams.
    3.  **VM4.1-C:** You SHOULD correlate vulnerability data with threat intelligence to prioritise CVEs that are actively being exploited in the wild (EPSS scoring).
    4.  VM4.1-D: You SHOULD run regular vulnerability review ceremonies (e.g. weekly) to assign owners, agree remediation plans, and review overdue items.
    5.  VM4.1-E: You MAY integrate vulnerability metrics (e.g. mean time to remediate, number of overdue criticals) into team and organisational KPIs to drive continuous improvement.

#### 4.4.6 Infrastructure Protection

##### IP4.1 Zero Trust Access

* **Objective:** Remove implicit trust based on network location, authenticating and authorising every request based on identity and context.
* **Recommended practices:**
    1.  **IP4.1-A:** You MUST reduce or eliminate implicit network trust for administrative access by favouring identity-Aware proxies, SSM Session Manager, and strongly authenticated endpoints over traditional VPN + wide-open internal networks.
    2.  **IP4.1-B:** You MUST require strong identity signals (MFA, device posture, conditional access) for access to AWS management and critical internal services, enforced via IdP policies and endpoint controls.
    3.  **IP4.1-C:** You MUST ensure mutual TLS (mTLS) is used for internal service communication where supported.
    4.  IP4.1-D: You SHOULD segment access policies by user, device, and context (e.g. location, risk score) and deny access when signals are missing or anomalous, even inside “trusted” networks.

##### IP4.2 Use Abstract Services

* **Objective:** Minimise the attack surface by shifting responsibility for operating system management and patching to AWS.
* **Recommended practices:**
    1.  **IP4.2-A:** You MUST preferentially select managed services over self-managed equivalents in new designs where they meet functional and regulatory requirements (e.g. RDS vs self-managed DB, Fargate vs unmanaged EC2).
    2.  **IP4.2-B:** You SHOULD provide standard patterns and IaC modules for serverless and managed-service architectures (e.g. API Gateway + Lambda + DynamoDB) to lower adoption friction for teams.
    3.  IP4.2-C: You SHOULD track the proportion of workloads using managed vs self-managed services as a KPI and target continual migration to higher-Abstraction services over time.

#### 4.4.7 Data Protection

##### DP4.1 GenAI Data Protection

* **Objective:** Secure Generative AI workloads and prevent the leakage of sensitive data into public models.
* **Recommended practices:**
    1.  **DP4.1-A:** You MUST define and enforce policies for which data classifications may be sent to GenAI services and under what conditions (e.g. only pseudonymised data, no customer PII, no key material).
    2.  **DP4.1-B:** You MUST configure GenAI-related services (e.g. Bedrock, custom model endpoints, third-party APIs) to disable training on customer content where possible and restrict data retention to mandated windows.
    4.  DP4.1-C: You SHOULD proxy outbound GenAI calls through controlled services (e.g. API gateways, service meshes) where inputs and outputs can be logged, inspected, and filtered based on policy.
    5.  DP4.1-D: You SHOULD tag and track GenAI workloads and data flows in your architecture and data catalogues, and incorporate them into your DPIA/DPA or other regulatory impact assessments where applicable.

#### 4.4.8 Application Security

##### AS4.1 Forming a Red Team (Attacker’s Point of View)

* **Objective:** Validate defences through unannounced, adversarial simulation to find gaps in detection and response.
* **Recommended practices:**
    1.  **AS4.1-A:** You SHOULD conduct regular Red Team exercises targeting the AWS environment, ensuring coordination with AWS Support if testing goes beyond standard penetration testing policies.
    2.  **AS4.1-B:** You MUST define scope, rules of engagement, and safety controls for red team operations, including clear boundaries for production impact and customer-facing behaviour.
    3.  **AS4.1-C:** You MUST ensure that red team findings are triaged, tracked, and remediated via the same defect and risk management mechanisms as other security issues, with appropriate severity.
    4.  AS4.1-D: You SHOULD coordinate red and blue team activities (e.g. purple teaming) to validate that detections fire and responders react appropriately to simulated attacks.
    5.  AS4.1-E: You MAY leverage outcomes from red team exercises to prioritise roadmap items for guardrails, detections, and architectural changes in AWS.

#### 4.4.9 Incident Response

##### IR4.1 Forming a Blue Team (Incident Response)

* **Objective:** Establish a dedicated team focused on proactive threat hunting and continuous monitoring improvement.
* **Recommended practices:**
    1.  **IR4.2-A:** You MUST define blue team roles (e.g. Tier 1/2 analysts, incident commanders) and staffing models (follow-the-sun, on-Call) appropriate to your risk profile.
    2.  **IR4.2-B:** You MUST ensure that the blue team has access to all relevant telemetry (Security Hub, Security Lake/SIEM, CloudTrail, GuardDuty, Inspector, Macie, WAF, VPC Flow Logs) and required AWS permissions for investigation.
    3.  IR4.1-C: You SHOULD define SLAs for alert triage, containment, and communication, and monitor adherence via metrics (e.g. MTTA, MTTR).
    4.  IR4.1-D: You SHOULD integrate the blue team into change and architecture reviews, so that detection and response implications are considered up front.

##### IR4.2 Advanced Security Automations

* **Objective:** Handle complex incident lifecycles with minimal human intervention using logic-Based automation.
* **Recommended practices:**
    1.  IR4.2-A: You MUST identify repetitive, high-volume security tasks (e.g. quarantine instances, revoke credentials, tag and isolate resources) and prioritise them for automation using EventBridge, Lambda, Step Functions, or SOAR platforms.
    2.  IR4.2-B: You MUST ensure that automations are version-Controlled, tested, and subject to change management comparable to application code.
    3.  IR4.2-C: You SHOULD design automations to be idempotent and safe, with robust error handling and clear audit trails in CloudTrail, logs, and ticketing systems.
    4.  IR4.2-D: You SHOULD support “approval gates” in automations where high-impact actions require human confirmation but low-risk actions execute fully automatically.
    5.  IR4.2-E: You MAY expose automation controls via chat-ops or internal portals so that responders can trigger standard playbooks consistently.

##### IR4.3 Security Orchestration & Ticketing

* **Objective:** Centralise incident management to coordinate response across tools and teams (SOAR).
* **Recommended practices:**
    1.  **IR4.3-A:** You MUST integrate AWS security event sources (Security Hub, GuardDuty, Inspector, Macie, WAF, CI security tools) with a central case or ticketing system that tracks incidents and investigations.
    2.  IR4.3-B: You MUST define standard fields (e.g. severity, asset, owner, SLA, classification) and workflows in the ticketing system for security issues.
    3.  **IR4.3-C:** You SHOULD ensure bidirectional communication so that closing a ticket updates the finding status in AWS Security Hub.
    4.  IR4.3-D: You SHOULD provide dashboards that show the full lifecycle of security cases (open, in progress, resolved) and support drill-Down by account, system, and control area.

##### IR4.4 Automate Deviation Correction in Configurations

* **Objective:** Achieve a self-healing infrastructure where configuration drift is automatically reverted.
* **Recommended practices:**
    1.  **IR4.4-A:** You MUST identify high-impact configuration drifts (e.g. disabling CloudTrail/Config/GuardDuty, making S3 buckets public, opening high-risk ports) that are candidates for automatic remediation.
    2.  **IR4.4-B:** You MUST implement Config rules, Security Hub controls, or custom checks that detect these drifts and trigger remediation workflows (e.g. Lambda functions, Step Functions) to revert them.
    3.  IR4.4-C: You SHOULD ensure that remediation automations notify resource owners and record actions taken in tickets/logs for auditability.
    4.  IR4.4-D: You SHOULD start remediation in monitor-only or “warn” mode in lower environments before enabling full auto-Correction in production.

#### 4.4.10 Resiliency

##### RS4.1 Multi-Region Disaster Recovery Automation

* **Objective:** Enable rapid, reliable failover to a secondary region with minimal data loss and downtime.
* **Recommended practices:**
    1.  **RS4.1-A:** You MUST identify workloads requiring multi-region DR and define explicit failover strategies (e.g. active–active, active–passive) and automation boundaries (what is handled by AWS vs your tooling).
    2.  **RS4.1-B:** You SHOULD automate the promotion of cross-region read replicas (e.g., Aurora Global Database) to primary status.
    3.  **RS4.1-C:** You MUST implement IaC and replication mechanisms (e.g. cross-region backups, Global Tables, Route 53, CloudFront, multi-region KMS key strategies where appropriate) that can recreate or activate workloads in secondary regions.
    4.  RS4.1-D: You SHOULD run regular multi-region DR tests (partial or full) using scripted procedures and capture metrics on RTO/RPO achievement.

##### RS4.2 Chaos Engineering

* **Objective:** Build confidence in system resilience by intentionally introducing faults in production environments.
* **Recommended practices:**
    1.  **RS4.2-A:** You MUST define guardrails and safety controls for chaos experiments (e.g. blast radius limits, time windows, approval flows, rollback criteria) before running them in production environments.
    2.  **RS4.2-B:** You MUST start chaos engineering in lower environments, focusing on realistic failure modes (e.g. instance termination, AZ impairment, dependency latency) and expand to production only when mature.
    3.  **RS4.2-C:** You SHOULD use automated tooling (e.g. fault injection services, internal scripts) to perform repeatable experiments and capture metrics on system behaviour and customer impact.
    4.  RS4.2-D: You SHOULD link chaos experiments to explicit hypotheses derived from threat models and DR plans (e.g. “system remains available if AZ A fails”) and treat unmet hypotheses as defects.
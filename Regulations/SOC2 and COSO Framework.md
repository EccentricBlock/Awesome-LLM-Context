# SOC 2 and COSO Framework: A Comprehensive Overview

This document provides a comprehensive summary of the System and Organization Controls 2 (SOC 2) framework and its foundational relationship with the COSO Internal Control-Integrated Framework.

## What Is SOC 2?

**System and Organization Controls 2 (SOC 2)** is an auditing framework developed by the American Institute of Certified Public Accountants (AICPA). It is designed specifically for service organizations to report on their internal controls related to information security.

A SOC 2 audit assesses the effectiveness of an organization's controls against five categories known as the **Trust Services Criteria (TSC)**. The resulting SOC 2 report provides customers and stakeholders with assurance that the organization has the appropriate security and privacy controls in place to protect their data.

---

## SOC 2 Trust Services Criteria (TSC)

The SOC 2 framework is built upon five Trust Services Criteria. For any SOC 2 audit, the **Security** criterion is mandatory. The other four criteria—Availability, Processing Integrity, Confidentiality, and Privacy—are optional and are included in the audit's scope based on the organization's business model, services, and contractual commitments to its customers.

### 1. Security (Common Criteria)

**Description:** The Security criterion, also known as the Common Criteria, is the mandatory foundation for all SOC 2 audits. It focuses on the protection of information and systems against unauthorized access, unauthorized disclosure, and damage that could compromise the availability, integrity, confidentiality, or privacy of data. These criteria are derived from the COSO framework.

**Criteria Breakdown:**
The Security criterion is organized into nine "Common Criteria" (CC) categories:

| Control ID | Heading | Description |
| :--- | :--- | :--- |
| **CC1** | Control Environment | Establishes the organization's commitment to integrity, ethical values, oversight, and accountability for security. |
| **CC2** | Communication and Information | Ensures that security objectives, policies, and responsibilities are effectively communicated to internal and external parties. |
| **CC3** | Risk Assessment | The organization identifies, analyzes, and manages risks to its objectives, including potential threats to customer data. |
| **CC4** | Monitoring Activities | Involves the continuous evaluation of control effectiveness to ensure they are present and functioning as intended. |
| **CC5** | Control Activities | The specific policies, procedures, and actions established to mitigate risks and achieve security objectives. |
| **CC6** | Logical and Physical Access Controls | Restricts access to systems, data, and physical locations (like data centers) to authorized individuals and services. |
| **CC7** | System Operations | Covers the management of system operations, including event monitoring, anomaly detection, and incident response. |
| **CC8** | Change Management | Ensures that all changes to systems (infrastructure, software, data) follow a secure, authorized, and documented process. |
| **CC9** | Risk Mitigation | Focuses on mitigating risks through contingency planning, asset protection, and managing risks from third-party vendors. |

**Example High-Level Controls:**
* Establishing a formal Code of Conduct, acknowledged by all employees.
* Performing background checks for new hires.
* Conducting annual risk assessments and maintaining a risk register.
* Implementing multi-factor authentication (MFA) and principles of least privilege for system access.
* Using firewalls, intrusion detection systems (IDS), and continuous monitoring tools.
* Maintaining a formal change management policy that requires testing and approval for all production changes.
* Having a documented incident response plan that is tested regularly.

---

### 2. Availability

**Description:** This criterion addresses the accessibility of information and systems as committed to by the organization. It evaluates controls that support operations, monitoring, and maintenance to ensure systems meet agreed-upon service levels (SLAs) and can recover from disruptions.

**Criteria Breakdown:**

| Control ID | Heading | Description |
| :--- | :--- | :--- |
| **A1.1** | Capacity Management | Ensures systems are provisioned and monitored to meet usage demands without performance degradation. |
| **A1.2** | Environmental Protections | Covers safeguards against environmental threats, power loss, or hardware failures that could cause outages. |
| **A1.3** | Backup and Recovery Testing | Requires regular testing of data backup and disaster recovery systems to validate the ability to restore data and services. |

**Example High-Level Controls:**
* Monitoring system performance and resource utilization with alerts for capacity thresholds.
* Using redundant power supplies (UPS) and network connections in data centers.
* Implementing auto-scaling groups in a cloud environment (e.g., AWS).
* Performing and testing data backups regularly, with copies stored offsite and encrypted.
* Conducting annual Disaster Recovery (DR) tests.

---

### 3. Processing Integrity

**Description:** This criterion assesses whether systems process data in a way that is complete, valid, accurate, timely, and authorized. It ensures that data processing achieves its intended purpose without errors, delays, or unauthorized manipulation.

**Criteria Breakdown:**

| Control ID | Heading | Description |
| :--- | :--- | :--- |
| **PI1.1** | Defined Processing Requirements | Systems must operate based on clearly documented rules and requirements for handling data. |
| **PI1.2** | Input Validation | Controls must be in place to ensure only complete, accurate, and valid data is processed by systems. |
| **PI1.3** | Accurate Processing | Controls must detect and correct processing errors in real-time or as quickly as possible. |
| **PI1.4** | Reliable Output Delivery | Verifies that processed data and reports are delivered to the correct recipients and are accurate and intact. |
| **PI1.5** | Data Retention and Protection | Protects the integrity of data while it is being stored, including logs and transaction records. |

**Example High-Level Controls:**
* Implementing input validation checks (e.g., type, format, range) on all data entry fields.
* Using batch totals or hash checks to reconcile data before and after processing.
* Creating automated alerts for processing failures or exceptions.
* Securing processing logs with write-once, read-many (WORM) protections.

---

### 4. Confidentiality

**Description:** This criterion focuses on the organization's ability to protect information that is designated as **confidential**. This can include trade secrets, intellectual property, financial reports, and other sensitive business data. It applies to the entire data lifecycle, from collection to secure disposal.

**Criteria Breakdown:**

| Control ID | Heading | Description |
| :--- | :--- | :--- |
| **C1.1** | Data Classification | The organization must identify data that is confidential and establish policies for how it should be handled. |
| **C1.2** | Protection Mechanisms | Enforces controls like encryption, access restrictions, and secure disposal protocols to protect confidential data. |

**Example High-Level Controls:**
* A formal data classification policy and procedures for labeling sensitive data.
* Encrypting all confidential data at rest (e.g., using AWS S3 server-side encryption) and in transit (e.g., using TLS 1.2+).
* Using strict access control lists (ACLs) and Identity and Access Management (IAM) policies.
* Implementing data loss prevention (DLP) tools.
* Following secure data disposal procedures, such as cryptographic shredding.

---

Here is the updated **5. Privacy** section with the requested `Control ID` column added to the criteria breakdown table.

---

### 5. Privacy

**Description:** The Privacy criterion is similar to Confidentiality but applies specifically to **personal information (PII)**. It assesses controls against the AICPA's privacy principles, which are closely aligned with global privacy regulations like GDPR. It covers how personal data is collected, used, retained, disclosed, and disposed of.

**Criteria Breakdown:**

| Control ID | Heading | Description |
| :--- | :--- | :--- |
| **P1.1** | Notice and communication | Providing clear notice to individuals (data subjects) about the organization's privacy practices. |
| **P1.2** | Choice and consent | Giving individuals options regarding the collection and use of their data and obtaining explicit consent. |
| **P1.3** | Collection | Collecting personal information only for the specific purposes stated in the privacy notice. |
| **P1.4** | Use, retention, and disposal | Limiting the use of personal data, retaining it only as long as necessary, and securely disposing of it. |
| **P1.5** | Access | Providing individuals with the ability to access, review, and correct their personal information. |
| **P1.6** | Disclosure and notification | Informing individuals about any data sharing with third parties and providing notification of data breaches. |
| **P1.7** | Quality | Maintaining accurate, complete, and relevant personal information. |
| **P1.8** | Monitoring and enforcement | Monitoring compliance with privacy policies and having a clear process for handling complaints and inquiries. |

**Example High-Level Controls:**
* A publicly accessible, easy-to-understand Privacy Notice.
* A cookie consent banner or user settings page for managing data use preferences.
* Data minimization practices to ensure only necessary PII is collected.
* A formal data retention and disposal policy.
* A defined process for handling Data Subject Access Requests (DSARs).

---

## COSO Framework: The Foundation of SOC 2

The SOC 2 framework is not built from scratch. The **Security (Common Criteria) TSC** is directly based on the **COSO Internal Control-Integrated Framework**.

COSO (The Committee of Sponsoring Organizations of the Treadway Commission) is an initiative that provides thought leadership and guidance on internal control, enterprise risk management (ERM), and fraud deterrence. The COSO framework, first issued in 1992 and updated in 2013, is the most widely accepted framework for internal controls globally, often used by public companies to comply with Sarbanes-Oxley (SOX).

The AICPA adopted COSO's five components and 17 principles as the basis for the SOC 2 Common Criteria, adapting them from their original focus on financial reporting to be relevant to a service organization's security controls.

---

## SOC 2 and COSO Mapping

The 17 COSO principles are organized into five components. These five components map directly to the first five SOC 2 Common Criteria (CC1–CC5). The remaining criteria (CC6–CC9) are additional controls specified by the AICPA to cover logical and physical access, operations, change management, and risk mitigation in greater detail.

Below is the direct mapping of the COSO framework to the SOC 2 Common Criteria.

### CC1: Control Environment
This criterion aligns with the **COSO Control Environment** component, which sets the "tone at the top" for the organization.
* **Principle 1:** The organization demonstrates a commitment to integrity and ethical values.
* **Principle 2:** The board of directors demonstrates independence from management and exercises oversight of internal control.
* **Principle 3:** Management establishes, with board oversight, structures, reporting lines, and appropriate authorities and responsibilities.
* **Principle 4:** The organization demonstrates a commitment to attract, develop, and retain competent individuals.
* **Principle 5:** The organization holds individuals accountable for their internal control responsibilities.

### CC2: Communication and Information
This criterion aligns with the **COSO Information & Communication** component, focusing on the quality and flow of information.
* **Principle 13:** The organization obtains or generates and uses relevant, high-quality information to support the functioning of internal control.
* **Principle 14:** The organization internally communicates information, including objectives and responsibilities for internal control.
* **Principle 15:** The organization communicates with external parties regarding matters affecting the functioning of internal control.

### CC3: Risk Assessment
This criterion aligns with the **COSO Risk Assessment** component, which forms the basis for how risks are identified and managed.
* **Principle 6:** The organization specifies objectives with sufficient clarity to enable the identification and assessment of risks.
* **Principle 7:** The organization identifies risks to the achievement of its objectives and analyzes risks to determine how they should be managed.
* **Principle 8:** The organization considers the potential for fraud in assessing risks.
* **Principle 9:** The organization identifies and assesses changes that could significantly impact the system of internal control.

### CC4: Monitoring Activities
This criterion aligns with the **COSO Monitoring Activities** component, which ensures that controls are effective over time.
* **Principle 16:** The organization selects, develops, and performs ongoing and/or separate evaluations to ascertain whether the components of internal control are present and functioning.
* **Principle 17:** The organization evaluates and communicates internal control deficiencies in a timely manner to those responsible for taking corrective action.

### CC5: Control Activities
This criterion aligns with the **COSO Control Activities** component, which includes the specific actions taken to mitigate risk.
* **Principle 10:** The organization selects and develops control activities that contribute to the mitigation of risks to acceptable levels.
* **Principle 11:** The organization selects and develops general control activities over technology to support the achievement of objectives.
* **Principle 12:** The organization deploys control activities through policies that establish expectations and procedures that put policies into action.
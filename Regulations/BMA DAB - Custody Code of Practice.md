
# Document Overview
This document provides a summary of the Bermuda Monetary Authority's (BMA) Digital Asset Business Custody Code of Practice (CoP) (Feb 2024).

The BMA Digital Asset Business Custody CoP provides comprehensive guidelines and standards to ensure the safekeeping and integrity of client digital assets. The code underscores the necessity of maintaining client assets separate from the custodian's own assets, ensuring the return of these assets in the event of insolvency or theft. 

Key components include:

1. **Section 2: Business Control Requirements**:
 Emphasis is placed on liquidity management, the use of hot and cold storage, fraud detection, compliance standards, dedicated personnel roles, insurability, proof of reserves, and collusion mitigation. Each aspect aims to enhance the robustness and resilience of digital asset custodians.

2. **Section 3: Technology Controls Part 1 (Custody Safekeeping)**: This section details the requirements for secure key and seed generation, management procedures, physical security for on-site cold storage, and the assurance of perpetual access for clients. Key generation must follow industry standards to ensure unguessable and confidential seed creation, with rigorous procedures for managing and revoking keys.

3. **Section 4: Technology Controls Part 2 (Custody Transaction Handling)**: The code mandates multi-signature authorization for transactions, periodic audits, and strict transaction authorization requirements. These controls aim to prevent fraud and ensure the integrity of all transaction processes.

4. **Section 5: Technology Controls Part 3 (Audit)**: Regular audits, at least biannually, are required for key and seed management processes, multi-signature authorizations, and transaction logs. These audits are crucial for verifying compliance and ensuring that all procedures adhere to the highest standards.

# Section 2: Business Control Requirements
A DAB must not underestimate the importance of sound business controls. There are a number of facets to business controls relating to staffing, outsourcing partners, access controls, operational risk management and business continuity. The business control standards are as follows:

## Section 2.1 - Liquidity
### Summary
BMA requires Digital Asset Businesses (DAB) to have documented mechanisms for assessing their liquidity needs, encompassing funds necessary for trading and client transactions.

### Detailed Information

- **Documented Mechanisms**: The DAB must establish and maintain documented procedures to assess and manage liquidity requirements.
- **Assessment of Liquidity Needs**: 
  - **Trading Funds**: Evaluate the amount of liquidity needed for daily trading activities.
  - **Client Transactions**: Determine the liquidity required to support various types of client transactions.

### Key Technical Concepts and Compliance Requirements
- **Documented Mechanisms**: Ensure formal documentation of procedures and mechanisms for liquidity assessment.
- **Liquidity Needs Assessment**:
  - **Trading**: Identify and document the liquidity required for ongoing trading operations.
  - **Client Transactions**: Establish and document the liquidity needs for client transaction processes.



## Section 2.2 - Hot and Cold Storage
### Summary
The Bermuda Monetary Authority's Digital Asset Business Custody Code of Practice mandates a risk assessment for both hot (online) and cold (offline) storage of digital assets, considering various factors such as asset nature, transaction volume, transaction speed, reversibility, and client risk tolerance.

### Detailed Information
- **Risk Assessment for Storage Methods**
  - A risk assessment is required for both cold storage (offline) and hot storage (online).
  - Factors to consider include:
    - **Nature of the Assets**: Evaluate the characteristics and specific requirements of the digital assets.
    - **Volume of Transactions**: Assess the quantity and frequency of transactions to determine the most suitable storage method.
    - **Transaction Speed**: Consider the required speed for completing transactions.
    - **Transaction Reversibility**: Analyze the ability to reverse transactions if needed.
    - **Client Risk Tolerance**: Understand and factor in the risk tolerance levels of the Digital Asset Business's (DAB) clients.

### Key Technical Concepts and Compliance Requirements

- **Cold Storage (Offline)**
  - Must undergo a thorough risk assessment.
  - Suitable for assets requiring high security and lower transaction frequency.

- **Hot Storage (Online)**
  - Must also undergo a thorough risk assessment.
  - Suitable for assets requiring quick transaction execution.

- **Risk Assessment Factors**
  - **Nature of the Assets**: Different assets have different security and accessibility needs.
  - **Volume of Transactions**: High-frequency transactions may favor hot storage.
  - **Transaction Speed**: Immediate transaction needs may necessitate hot storage.
  - **Transaction Reversibility**: The ability to reverse transactions can impact storage choice.
  - **Client Risk Tolerance**: Storage solutions should align with the client's risk comfort levels.


## Section 2.3 - Fraud Detection and Compliance Standards
### Summary
BMA mandates that Digital Asset Businesses (DABs) implement a comprehensive fraud detection protocol and internal compliance standards. This includes systems for identifying and reviewing suspicious transactions.

### Detailed Information
- **Protocol Development**: DABs must establish a detailed protocol for fraud detection.
- **Detection System**: Implement a detection system designed to identify suspicious transactions.
- **Review Procedures**: Develop a systematic procedure for reviewing transactions flagged as suspicious.

### Key Technical Concepts and Compliance Requirements
- **Fraud Detection Protocol**: A structured approach to identifying potential fraudulent activities within digital asset transactions.
- **Suspicious Transaction Identification**: Mechanisms and algorithms used to detect anomalies or patterns indicative of fraud.
- **Review Procedures**: Steps and guidelines for the assessment and verification of flagged transactions to determine the legitimacy and compliance status.

## Section 2.4 - Personnel Dedicated Roles and Responsibilities
### Summary
The BMA mandates that Digital Asset Businesses (DABs) must establish and document roles and responsibilities for custody operations and custody operational risk management, with formal approval from senior management.

### Detailed Information
- **Custody Operations Roles and Responsibilities**:
  - DABs are required to define specific roles and responsibilities related to custody operations.
  - These roles must be formally documented to ensure clarity and accountability.

- **Custody Operational Risk Management Roles and Responsibilities**:
  - DABs must also delineate roles and responsibilities for managing custody operational risks.
  - The documentation of these roles should outline the procedures and responsibilities to mitigate operational risks associated with custody services.

- **Formal Documentation and Approval**:
  - All roles and responsibilities, both for custody operations and risk management, must be formally approved by the senior management team.
  - The formal approval process ensures that senior management is accountable and that the roles are aligned with the strategic objectives and regulatory requirements.

### Key Technical Concepts and Compliance Requirements
- **Custody Operations**: The processes and procedures involved in securely managing and storing digital assets.
- **Custody Operational Risk Management**: Strategies and practices aimed at identifying, assessing, and mitigating risks associated with the custody of digital assets.
- **Formal Documentation**: The process of creating official records of roles and responsibilities, which provides a reference for accountability and compliance.
- **Senior Management Approval**: The requirement that the highest level of management must review and endorse the documented roles and responsibilities to ensure alignment with organizational goals and regulatory standards.


## Section 2.5 - Insurability and Other Protections
### Summary
The BMA's Digital Asset Business (DAB) Custody Code of Practice mandates that DABs must ensure assets under custody are protected through appropriate insurance or other financial safeguards to mitigate potential loss exposure.

### Detailed Information
- **Requirement**: DABs must demonstrate that assets under custody carry appropriate insurance or other financial protections.
- **Objective**: The goal is to cover or mitigate potential loss exposure.
- **Scope**: This applies to all assets under custody by DABs.
- **Compliance Criteria**: 
  - **Insurance**: DABs must secure insurance policies that adequately cover the value of assets under custody.
  - **Financial Protections**: Alternatives to insurance, such as financial guarantees or other mechanisms, must be sufficient to mitigate potential losses.
- **Documentation**: DABs must maintain documentation that evidences the existence and adequacy of such protections.

### Key Technical Concepts and Compliance Requirements

- **Insurance Requirement**: Assets under custody must be insured to cover potential losses.
- **Alternative Financial Protections**: Financial guarantees or other protective measures must be in place if insurance is not utilized.
- **Evidence of Compliance**: Proper documentation must be maintained to prove that these protections are in place and sufficient.



## Section 2.6 - Proof of Reserves (POR)
### Summary
The BMA's Digital Asset Business Custody Code of Practice mandates that Digital Asset Businesses (DABs) must maintain sufficient reserves of each type of digital asset held in custody to meet client obligations. This requirement includes maintaining accurate records, implementing robust systems and controls, ensuring segregation of duties, and establishing redundancy and business continuity procedures.

### Detailed Information
- **Section 18(3) of the Act**: "A Digital Asset Business (DAB) that has custody of one or more digital assets for one or more clients must maintain in its custody a sufficient amount of each type of digital asset in order to meet its obligations to clients."
- **Record-Keeping Requirements**:
  - DABs must maintain adequate accounting records.
  - DABs must keep other relevant records necessary for tracking ownership and quantity of client digital assets.
- **Systems and Controls**:
  - DABs must implement adequate systems and controls to accurately track client digital asset ownership and quantities.
  - These systems should be robust and reliable to ensure continuous accuracy.
- **Segregation of Duties**:
  - DABs must ensure adequate segregation of duties to protect the integrity of the record-keeping process.
- **Redundancy and Business Continuity**:
  - DABs must have appropriate redundancy processes in place.
  - Business continuity procedures must be established to ensure records of client digital assets in custody are accessible at all times, including post-natural and other disasters.

### Key Technical Concepts and Compliance Requirements

- **Sufficient Reserves**: Maintaining a sufficient amount of each type of digital asset to meet client obligations.
- **Accurate Record-Keeping**: Implementing and maintaining accurate accounting and other relevant records.
- **Robust Systems and Controls**: Ensuring systems and controls are adequate to track ownership and quantity of digital assets.
- **Segregation of Duties**: Protecting the integrity of records by segregating duties appropriately.
- **Redundancy and Business Continuity**: Establishing redundancy and continuity procedures to ensure continuous access to records, especially post-disaster.

## Section 2.7 - Collusion Mitigation
### Summary:
The Bermuda Monetary Authority's Digital Asset Business Custody Code of Practice mandates Digital Asset Businesses (DABs) to implement effective collusion mitigation strategies to control the signing process and prevent bad faith actions. The Code outlines specific methods for mitigating collusion, including oversight controls, distribution of signatories, anonymity among signatories, and the rotation of signing entities and procedures.

### Detailed Information:
- **Method for Controlling the Signing Process:** DABs must implement controls to prevent a quorum of individuals from colluding or acting in bad faith.
- **Controls and Oversight:** Implement oversight or separation of duties to prevent a linear process where the same individuals can create, approve, sign, and broadcast transactions to distributed ledger networks.
- **Distribution of Signatories:** Utilize signatories with differing incentives, such as clients, custodians, and third parties.
- **Anonymity Among Signatories:** Ensure that the identities of signatories are unknown to each other.
- **Rotation of Signing Procedures:** Regularly rotate signatories, signing times, or signing locations to minimize collusion risks.
- **Operational Risk Assessments:** Address the risk of collusion and other malicious acts as part of recurring operational risk assessments.

**Key Technical Concepts and Compliance Requirements:**
- **Collusion Mitigation Strategies:** Implement various methods to prevent collusion among individuals involved in the signing process.
- **Oversight and Separation of Duties:** Prevent a linear workflow by separating responsibilities and implementing oversight controls.
- **Diverse Signatories:** Use signatories with different incentives to reduce the likelihood of collusion.
- **Signatory Anonymity:** Maintain anonymity among signatories to further prevent collusion.
- **Regular Rotation:** Regularly change signatories, signing times, and locations to reduce risks.
- **Risk Assessments:** Incorporate collusion risks into ongoing operational risk assessments to continually address and mitigate these risks.


# Section 3: Technology Controls Part 1 (Custody Safekeeping)
One of the most important responsibilities of the DAB is the safekeeping of digital assets in its custody. Controls must be in place to ensure digital assets are securely created and stored. Additionally, uninterrupted availability of assets is another important requirement.

## Section 3.1 -  Seed Generation
### Summary:
The BMA Digital Custody CoP mandates the secure generation of cryptographic seeds and keys, emphasizing confidentiality and the use of unguessable numbers. The process involves deterministic or non-deterministic random bit generators, multi-party involvement, and stringent protocols to ensure the seeds' and keys' integrity and security.

### Detailed Information:
- **Confidentiality and Un-guessable Numbers:**
  - Ensures that newly created keys or seeds are not read or copied by unauthorized parties.
  - Requires the creation of keys or seeds that cannot be guessed or determined by unauthorized parties.

- **Deterministic Random Bit Generator:**
  - Seeds should be created using a compliant deterministic random bit generator.
  - Non-deterministic key generation mechanisms are also acceptable.

- **Entropy Requirements:**
  - Seeds must have a minimum random sequence of 256-bit entropy.
  - The result must be encoded into a mnemonic 24-word phrase as a minimum.

- **Hashing Function:**
  - Utilizes a hashing function to generate a 512-bit value minimally.
  - The 24-word phrase serves as a backup seed, enabling regeneration of the seed.

- **Multi-Party Involvement:**
  - A minimum of three individuals must perform the process of creating entropy and producing the seed.
  - No single person should ever possess the entirety of the seed or the backup mnemonic word phrase.

- **Signatory Seed Production:**
  - When producing a seed for a signatory, the signatory must not be involved in producing the public and private keys.
  - Seed creators are prohibited from participating in cryptographic signing or accessing transaction-facilitating systems.

### Key Technical Concepts and Compliance Requirements:

- Confidentiality and security in cryptographic key and seed generation.
- Use of deterministic random bit generators or secure non-deterministic mechanisms.
- Minimum 256-bit entropy for seed creation.
- Encoding seeds into mnemonic 24-word phrases.
- Hashing to generate a minimum 512-bit value.
- Multi-party involvement in seed generation.
- Separation of duties in key production and signing processes.


## Section 3.2 - Key Pair Generation
### Summary:
The BMA mandates that Digital Asset Businesses (DABs) employ industry-standard methods for key pair generation, ensuring that revoked signatories do not have access to backup seeds or phrases. Additionally, all keys must be encrypted to prevent compromised signatories from recovering the seed.

### Detailed Information:
- **Industry-Standard Method Requirement**: Digital Asset Businesses (DABs) must utilize key generation techniques that align with recognized industry standards.
- **Revoked Signatory Access Prevention**: Measures must be in place to ensure that any signatory who has been revoked does not retain access to the backup seed or any knowledge of the phrase used during key creation.
- **Encryption of Keys**: All generated keys must be encrypted robustly to safeguard against a compromised signatory being able to retrieve the seed.

### Key Technical Concepts and Compliance Requirements:
- **Industry-Standard Key Generation**: Utilization of widely accepted and secure methods for creating key pairs.
- **Access Control for Revoked Signatories**: Implementation of security measures to restrict revoked signatories from accessing critical key creation data.
- **Robust Encryption**: Ensuring all keys are encrypted in such a manner that prevents unauthorized recovery of the seed by compromised individuals.

## Section 3.3 - Data Sanitisation
The BMA's Custody Code of Practice mandates secure deletion and destruction mechanisms to eliminate unwanted artifacts resulting from seed, key, and wallet generation processes. This requirement ensures that sensitive data is irretrievably erased to prevent unauthorized access or misuse.

### Detailed Information


- **Post Seed and Key Generation**: 
  - **Requirement**: Secure deletion and destruction mechanisms must be in place.
  - **Purpose**: To prevent unwanted artifacts from seed, key, and wallet generation.
  - **Implication**: Ensures irretrievable erasure of sensitive data to avoid unauthorized access or misuse.

### Key Technical Concepts and Compliance Requirements

- **Data Sanitisation**:
  - Mechanisms for secure deletion and destruction are mandatory.
  - Must cover artifacts from seed generation, key generation, and wallet creation.
  - Ensures sensitive data is completely and irretrievably erased.

## Section 3.4 - Seed and Key Management Procedure

The BMA mandates a comprehensive seed and key management procedure encompassing security, redundancy, backup, availability, and logical access controls to protect client private keys and mnemonic backup seed phrases. This procedure ensures strong encryption, separation of backups, and the use of certified Hardware Security Modules (HSMs) for critical key storage.

### Detailed Information
- **Requirement**: A formally documented procedure detailing security, redundancy, backup, availability, and logical access controls.
  - **Reference**: Section 3.4

- **Encryption and Storage**:
  - **Requirement**: Strong encryption and secure device storage for client private keys not in use (cold wallets).
  - **Reference**: Section 3.4.1

- **Logical Access Controls**:
  - **Requirement**: Logical access controls must prevent achieving a quorum of transaction signatures from keys stored in a single location.
  - **Reference**: Section 3.4.2

- **Mnemonic Backup Seed Phrase**:
  - **Requirement**: Mnemonic backup seed phrase must be broken into at least two or more parts, ensuring no sufficient number of parts can be stored in a single facility to facilitate a transaction.
  - **Reference**: Section 3.4.3

- **Key and Seed Backups**:
  - **Requirement**: Key and seed backups must be stored separately from primary key and seed, with strong encryption equal to or better than that used for the primary key, and protected by access controls.
  - **Reference**: Section 3.4.4

- **Hardware Security Modules (HSMs)**:
  - **Requirement**: For critical seeds, keys, and key parts, HSMs certified to Federal Information Processing Standard 140-2 are recommended as the most secure key storage mechanism, applicable to both physical and virtual devices.
  - **Reference**: Section 3.4.5

### Key Technical Concepts and Compliance Requirements

- **Documented Seed and Key Management Procedure**: Must detail security, redundancy, backup, availability, and logical access controls.

- **Strong Encryption and Secure Storage**: Required for client private keys not in use (cold wallets).

- **Logical Access Controls**: Must prevent quorum of transaction signatures from keys stored in a single location.

- **Mnemonic Backup Seed Phrase**: Must be split into multiple parts, ensuring no single facility holds sufficient parts to facilitate a transaction.

- **Separate and Secure Key/Seed Backups**: Backups must be stored separately with strong encryption and access controls.

- **Federal Information Processing Standard 140-2 Certified HSMs**: Recommended for critical key storage, applicable to both physical and virtual HSMs.


## Section 3.5 - Key Access and Compromise Procedure
### Summary

The BMA mandates that Digital Asset Businesses (DABs) implement a formal procedure to manage access to cryptographic keys or seeds and to respond to key compromises, ensuring comprehensive audit trails and risk management protocols.

### Detailed Information
- **Procedure Documentation**: 
  - A formal, documented procedure must outline the process when a staff member gains access to keys or seeds.
  - This procedure must include comprehensive details on the handling of keys or seeds by staff members.

- **Audit Trail Requirements**:
  - Maintain an audit trail recording every change of access, specifying the individual who performed the change.
  - Ensure that the audit trail is detailed and secure to facilitate future audits and investigations.

- **Key Compromise Procedure**:
  - Document a specific key compromise procedure.
  - The procedure must address events triggering the protocol, including:
    - Compromise of the whole seed.
    - Partial seed compromise.
    - Compromise of a key derived from a seed.
  - The response mechanism must detail the process for creating new wallets and migrating assets if the underlying seed is compromised.

- **Risk Event Documentation**:
  - If a key is determined to be compromised, a risk event must be documented.
  - The risk event must be thoroughly investigated to understand the extent and impact of the compromise.

### Key Technical Concepts and Compliance Requirements

- **Formal Procedures**: Establish and document clear procedures for access to cryptographic keys and seeds by staff.
- **Audit Trails**: Maintain detailed records of all changes in key or seed access, including responsible individuals.
- **Compromise Response**: Implement a documented response for key compromise events, including asset migration and new wallet creation.
- **Risk Management**: Ensure all key compromises are recorded as risk events and investigated to prevent recurrence.



## Section 3.6 - Key Revocation Procedure
### Summary:
The BMA Digital Asset Business Custody Code of Practice outlines the mandatory procedures for Digital Asset Businesses (DABs) to immediately revoke a signatory's access, emphasizing security and compliance protocols without necessitating the creation of a new wallet.

### Detailed Information:
- **Immediate Revocation of Access**: DABs must have procedures for the immediate revocation of a signatory’s access.
- **Standard Protocol**: The revocation procedure must follow the standard protocol, ensuring that access is removed without the need to create a new wallet.
- **Internal Audits**: DABs are required to perform internal audits to recertify access at least quarterly.
- **Written Procedure Document**: A written document must be in place, detailing the procedures for on/off-boarding signatories.
  - **On/Off-Boarding Procedures**: The document must outline every permission to grant/revoke for each role within the information system.
- **Authenticated Communication Channel**: All grant/revoke requests must be made through an authenticated communication channel and transmitted using an encrypted protocol.

### Key Technical Concepts and Compliance Requirements:
- **Immediate Access Revocation**: Ensuring prompt removal of access rights to maintain system security.
- **Standard Revocation Protocol**: Following established guidelines to revoke access without creating new wallets.
- **Quarterly Internal Audits**: Conducting regular audits to verify and recertify access permissions.
- **Comprehensive Procedure Documentation**: Maintaining a detailed, written procedure for on/off-boarding signatories and managing permissions.
- **Secure Communication**: Utilizing authenticated and encrypted channels for all access modification requests.


## Section 3.7 - Perpetual Access:
### Summary
The DAB Custody Code of Practice mandates that DABs ensure clients have perpetual access to their assets in custody, even if the DAB ceases operations or cannot fulfill its custody agreement. Any exceptions must be explicitly defined in a service level agreement and communicated to the client, potentially involving formal disbursement or custody transfer processes.

### Detailed Information
- A Digital Asset Business (DAB) must ensure that clients have perpetual access to all assets held in custody.
- This requirement applies in situations where the DAB ceases to operate or is unable to fulfill its custody agreement.
- Any exceptions to perpetual access must be clearly defined within a service level agreement (SLA).
- The SLA detailing these exceptions must be communicated to the customer explicitly.
- Exceptions may include:
  - A formal disbursement process.
  - A custody transfer process.

### Key Technical Concepts and Compliance Requirements

- **Perpetual Access Obligation:** DABs are required to guarantee ongoing client access to custodial assets, irrespective of the DAB's operational status.
- **Service Level Agreement (SLA):** Exceptions to perpetual access must be outlined in a formally documented SLA.
- **Client Communication:** The specifics of any exceptions must be clearly communicated to clients.
- **Disbursement and Custody Transfer:** Potential measures for handling exceptions include formal processes for disbursement or transferring custody of the assets.



## Section 3.8 - Account Segregation
### Summary
The BMA mandates Digital Asset Businesses (DABs) to segregate client assets from their own, allowing commingling of client assets only if proper accounting measures are in place to accurately allocate holdings and ensure security levels comparable to a one-to-one client-address relationship.

### Detailed Information
- **Client Asset Separation**: DABs must maintain a clear distinction between client assets and their own assets.
- **Commingling of Client Assets**: DABs are permitted to commingle client assets if it benefits clients.
- **Proper Accounting Measures**: Accurate allocation of each client's holdings must be ensured through robust accounting practices.
- **Security Measures**: The security level of commingled assets must be equivalent to that of a one-to-one client-address relationship.
- **Documentation and Implementation**: DABs must document and implement measures to demonstrate the achieved security level.

### Key Technical Concepts and Compliance Requirements

- **Client Asset Separation**: Ensuring that client assets are kept distinct from the company's own assets.
- **Commingling Benefits**: Conditions under which client assets can be commingled for mutual benefit.
- **Accurate Allocation**: Requirement for precise accounting to track individual client holdings.
- **Security Equivalence**: Need for security measures that provide the same level of protection as individual client-address setups.
- **Documentation and Implementation**: Obligation to document and implement security measures demonstrating compliance with segregation standards.

## Section 3.9 - Physical Security and Access Standards for On-Site Cold Storage
### Summary:
The BMA mandates that on-site cold storage facilities undergo a risk assessment to determine asset storage and requisite physical controls. Digital Asset Businesses (DABs) must ensure that storage facilities meet appropriate industry standards.

### Detailed Information:
  - **Risk Assessment Requirements:** 
    - Each storage facility must undergo a risk assessment.
    - The assessment must evaluate what assets are stored at each facility.
    - The assessment must identify necessary physical controls for those assets.
  - **Demonstration of Compliance:**
    - Digital Asset Businesses (DABs) are required to demonstrate that all storage facilities meet appropriate industry standards.
    - This compliance should be evidenced through documentation and physical inspections as needed.

### Key Technical Concepts and Compliance Requirements:

- **Risk Assessment:**
  - Conduct a thorough evaluation of asset types stored.
  - Identify and document physical controls necessary for safeguarding assets.
- **Industry Standard Compliance:**
  - Ensure storage facilities adhere to recognized physical security and access control standards.
  - Maintain records proving compliance with these standards.
- **Physical Controls:**
  - Implement appropriate security measures (e.g., surveillance, secure access points).
  - Regularly review and update security measures based on the latest industry practices.

# Section 4: Technology Controls Part 2 (Custody Transaction Handling)
A DAB must ensure that transactions are subject to controls to ensure they are secure and trusted and that measures are in place to prevent fraud. Transactions must be recorded in system audit records. These records must then be subject to periodic audits.

## Section 4.1 - Multi-Signature Authorisation
### Summary

The BMA's mandates a documented multi-signature authorization procedure using an M-of-N standard, requiring a minimum of three signatories for transaction authorization, with annual audits.

### Detailed Information
- **Procedure Documentation**: A documented procedure must be established for multi-signature authorization.
- **M-of-N Multi-Signature Standard**: DABs (Digital Asset Businesses) must employ an M-of-N multi-signature standard.
- **Minimum Signatories**: A minimum of three signatories is required for a quorum signature standard for all transaction types.
- **Mitigating Controls**: If the M-of-N standard is not feasible, an appropriate mitigating authorization control using multiple signatures must be implemented.
- **Annual Audits**: Multi-signature authorizations must undergo an annual audit.

### Key Technical Concepts and Compliance Requirements
- **Multi-Signature Authorization**: A security measure requiring multiple signatures to authorize transactions, enhancing security by distributing control among several parties.
- **M-of-N Standard**: A multi-signature scheme where M out of N possible signatories are required to authorize a transaction.
- **Quorum Signature Standard**: Ensures that a minimum number of signatories (at least three) is met for validating transactions.
- **Mitigating Authorization Control**: Alternative control measures when the M-of-N standard cannot be applied, still adhering to the principle of requiring multiple signatures.
- **Annual Audit Requirement**: Regular, systematic examination of multi-signature authorization processes to ensure compliance and security integrity.

## Section 4.2 - Transaction Authorisation Requirements:
### Summary
BMA mandates a risk assessment of transaction types to define and implement appropriate transaction authorization controls, with documentation of decision approval retained for five years.

### Detailed Information
- **Risk Assessment of Transaction Types:** A comprehensive risk assessment must be conducted for all transaction types to identify potential risks and vulnerabilities.
- **Defining Transaction Authorisation Control Requirements:** The risk assessment outcomes must be used to establish specific transaction authorization controls tailored to mitigate identified risks.
- **Implementation of Appropriate Controls:** Based on the defined control requirements, suitable controls must be implemented to ensure secure transaction processing.
- **Retention of Decision Approval Evidence:** All evidence of decision approvals, including the chain of custody, must be meticulously documented and retained for a minimum of five years for compliance and review purposes.

### Key Technical Concepts and Compliance Requirements
- **Risk Assessment:** Detailed evaluation of potential risks associated with different transaction types.
- **Transaction Authorisation Controls:** Specific measures and controls established to authorize transactions securely.
- **Implementation of Controls:** Practical application of defined controls to mitigate transaction risks.
- **Documentation and Retention:** Maintenance and retention of decision approval evidence, including chain of custody, for five years.


## Section 4.3 Periodic Transactions Audit
### Summary:
The Bermuda Monetary Authorities Digital Asset Business Custody Code of Practice mandates quarterly internal audits of transaction samples by Digital Asset Businesses (DABs) to ensure process integrity, with required remediation actions and stringent record-keeping and audit trails.

### Detailed Information:
- **Quarterly Audit Requirement**: DABs must audit a sample of transactions quarterly to ensure internal processes are functioning as intended. Remediation actions are mandatory if faults are discovered.
- **Integrity Controls**: Records and audit trails must be immutable.
  
**Contractual Nature of Evidence**:
- **Signatory Evidence Agreement**: All signatories must contractually agree on the evidence required to authorize a transaction. If transaction approval and signing are separate processes, transaction approvers must have the requisite expertise to evaluate the evidence before authorization.
  
**Proof of Evidence**:
- **Evidence Submission**: Each approver or signatory must provide proof of the referenced evidence for authorization.

**Proof of Elapsed Time**:
- **Time Tracking**: Specific time durations must be tracked for each transaction and associated signature action, especially for transactions with time-based evidence conditions.
  
**Auditability**:
- **Internal Evidence Storage**: DABs must internally store all evidence and have it reviewed at multiple levels within a transaction. A minimum of two separate individuals must review each specific request.
- **Checklist Documentation**: Evidence is collected based on a set checklist tailored to the signatory's role. DABs must periodically evaluate and adjust controls around these processes.
  
**Books and Records**:
- **Audit Trail Maintenance**: DABs must maintain a comprehensive audit trail of all user and admin actions, including:
  - Date and time of the transaction
  - Transaction event type
  - Jurisdiction of the client and relevant signatories
  - Account balances and transaction value
- **Audit Log Storage**: The audit log must be retained for at least five years and be available for review by the Authority.

### Key Technical Concepts and Compliance Requirements:
- **Quarterly Internal Transaction Audits**: Mandated to ensure process integrity.
- **Immutable Records and Audit Trails**: Required to safeguard the integrity of records.
- **Signatory Evidence Agreement**: Contractual agreement on required evidence for transaction authorization.
- **Evidence Submission and Proof**: Mandatory proof of evidence by each signatory.
- **Time Duration Tracking**: Essential for transactions with time-based conditions.
- **Multiple-Level Review**: At least two individuals must review each request, based on a role-specific checklist.
- **Comprehensive Audit Trails**: Detailed record-keeping of transactions, including date, time, event type, jurisdiction, account balances, and value, retained for five years.


# Section 5: Technology Controls Part 3 (Audit)
An annual IT audit plan must be developed and approved by the audit committee of the board or its equivalent. Audits may be carried out by a qualified internal audit resource or by qualified third parties.

## Section 5.1 - Recurring Audit Requirements for Digital Assets
### Summary
BMA mandates biannual audits for specified procedures related to digital assets, with comprehensive documentation and retention of audit records for at least five years.

### Detailed Information


- **Audit Frequency and Documentation**: 
  - Procedures listed must be audited every six months.
  - Audit evidence must be documented and available to BMA upon request.
- **Key and Seed Generation and Management Processes**: Regular audit of the processes used to generate and manage cryptographic keys and seeds.
- **Key Revocation Procedure** (Reference 3.6): Audit of the procedures for revoking keys to ensure security compliance.
- **Multi-Signature Authorizations** (Reference 4.1): Verification of the multi-signature authorization process.
- **Transaction System Audit Logs** (Reference 4.3): Detailed review of transaction system logs.
    - **Contractual Nature of Evidence**: Audits conducted quarterly to ensure contractual obligations are met.
    - **Proof of Evidence**: Quarterly audits to verify the evidence provided meets required standards.
    - **Proof of Elapsed Time**: Quarterly audits to confirm the time-related evidence.
    - **Completed Transaction Audit**: Ensures transactions comply with proof of evidence protocols.
- **Suspicious Transaction Handling**: Audit of the handling and documentation of suspicious transactions.
- **Migration of Storage Devices (Cold to Hot Storage)**: Verification of protocols for migrating digital asset storage. 
- **Proof of Solvency Random Address**: Random audits to confirm solvency using address verification.

**Retention of Audit Records**: All audit records must be retained for a minimum of five years and be readily accessible to the Authority upon request.

### Key Technical Concepts and Compliance Requirements
- **Biannual Audit Requirements**: Mandatory audits every six months for key processes and procedures.
- **Quarterly Audit Specifications**: Certain elements, such as proof of evidence and elapsed time, require quarterly audits.
- **Documentation and Retention**: Comprehensive documentation of audit evidence.
  - Retention of audit records for at least five years.
- **Specific Audit Areas**: Key generation and management, key revocation, multi-signature authorizations, transaction logs, suspicious transaction handling, and storage migration.
- **Proof of Solvency**: Verification through random address audits.

# Conclusion
The BMA's Digital Asset Business Custody Code of Practice is a critical framework for ensuring the security and integrity of digital assets under custody. By establishing stringent business control and technology requirements, the code mitigates risks associated with digital asset management, such as fraud, misappropriation, and operational failures. The mandatory and best practice standards provide a clear pathway for custodians to achieve and maintain a high level of operational resilience and client trust.

The broader implications of adhering to this code extend beyond compliance. It fosters a secure and transparent environment for digital asset transactions, thereby enhancing market stability and investor confidence. Practically, it necessitates that custodians adopt advanced cryptographic practices, implement rigorous internal controls, and maintain comprehensive audit trails, which collectively contribute to the overall health and sustainability of the digital asset ecosystem.

Ensuring internal coherence, this summary highlights the essential elements of the BMA's Code of Practice, providing a standalone overview that conveys the critical compliance and technical requirements. It serves as a quick reference for understanding the obligations and best practices necessary for digital asset custodians operating under the BMA's jurisdiction.
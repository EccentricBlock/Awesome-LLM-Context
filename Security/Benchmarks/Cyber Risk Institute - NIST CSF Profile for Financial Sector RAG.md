# CRI Profile v2.0: Detailed Mapping to NIST CSF for the Financial Sector
## Introduction
This document outlines the Cyber Risk Institute (CRI) has developed CRI's Profile v2.0 framework to create an efficient approach to technology and cybersecurity risk management that effectively counters dynamic and evolving threats and provides adequate assurance to government supervisors.  This profile is built ontop of the NIST Cybersecurity Framework as a community profile.


## CRI Profile Impact Tiers
The four-tier system categorises financial institutions and services based on the breadth and scale of their potential adverse impact. Tier 1 covers globally critical institutions with designations from top-level regulatory bodies, Tier 2 addresses subnationally significant institutions crucial to regional economies, Tier 3 includes highly interconnected entities critical to the sector as a whole, and Tier 4 comprises locally impactful organisations with comparatively limited scope.

| **Tier** | **Definition** |
| --- | --- |
| **Tier 1: National/Super-National Impact** | - Designated as most critical by global regulators (e.g., GSIB, Executive Order 13636 Section 9).<br>- Gross cyber risk could affect national economic stability or global markets. |
| **Tier 2: Subnational Impact** | - Provide mission-critical services with millions of customer accounts.<br>- Adverse impact could substantially affect the financial services sector and regional economy, though not at Tier 1 level. |
| **Tier 3: Sector Impact** | - Highly interconnected institutions or key nodes within the financial sector.<br>- The nature of services provided significantly contributes to their criticality. |
| **Tier 4: Localised Impact** | - Limited overall impact on the financial services sector and national economy.<br>- Typically smaller, local presence with fewer than 1 million customers or providers of low criticality services. |



# NIST Functions
The CRI community profile functions provide a strategic structure to manage cybersecurity risk through a continuous cycle of improvement. They comprise fisixve core functions `Govern, Identify, Protect, Detect, Respond, Recover and Extend` that guide organisations in understanding their risk environment, implementing safeguards, promptly detecting incidents, mitigating impacts through coordinated responses, and restoring operations after an event. This integrated approach not only facilitates clear communication and alignment of cybersecurity efforts across all organisational levels but also promotes ongoing adaptation and resilience in the face of evolving threats.

## GOVERN (GV)
GOVERN (GV): The organization's technology and cybersecurity risk management strategy, expectations, and policy are established, communicated, and monitored

### GOVERN / Organizational Context (GV.OC)
Organizational Context (GV.OC): The circumstances - mission, stakeholder expectations, dependencies, and legal, regulatory, and contractual requirements - surrounding the organization's technology and cybersecurity risk management decisions are understood

#### GOVERN / Organizational Context / Organizational Mission (GV.OC-01)
GV.OC-01: The organizational mission is understood and informs technology and cybersecurity risk management

| Category ID  | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OC-01.01  | Technology and cybersecurity strategies, architectures, and programs are formally governed to align with and support the organization's mission, objectives, priorities, tactical initiatives, and risk profile.      | Yes    | Yes    | Yes    | Yes    | GV.OC-01          |

#### GOVERN / Organizational Context / Stakeholder Risk Management Expectations (GV.OC-02)
GV.OC-02: Internal and external stakeholders are understood, and their needs and expectations regarding technology and cybersecurity risk management are understood and considered

| Category ID  | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OC-02.01  | The organization's obligation to its customers, employees, and stakeholders to maintain safety and soundness, while balancing size and complexity, is reflected in the organization's risk management strategy and framework,  its risk appetite and risk tolerance statements, and in a risk-aware culture.  | Yes    | Yes    | Yes    | Yes    | GV.OC-02         |
| GV.OC-02.02  | Technology and cybersecurity risk management strategies identify and communicate the organization�s role within the financial services sector as a component of critical infrastructure.         | Yes    | No     | No     | No     | GV.OC-02         |
| GV.OC-02.03  | Technology and cybersecurity risk management strategies identify and communicate the organization's role as it relates to other critical infrastructure sectors outside of the financial services sector and the interdependency risks.                        | Yes    | No     | No     | No     | GV.OC-02         |

#### GOVERN / Organizational Context / Legal, Regulatory, & Contractual Requirements (GV.OC-03)
GV.OC-03: Legal, regulatory, and contractual requirements regarding technology and cybersecurity - including privacy and civil liberties obligations - are understood and managed

| Category ID  | Outcome                          | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OC-03.01  | The organization's technology and cybersecurity strategy, framework, and policies align and are consistent with the organization's legal, statutory, contractual, and regulatory obligations and ensure that compliance responsibilities are unambiguously assigned. | Yes    | Yes    | Yes    | Yes    | GV.OC-03         |
| GV.OC-03.02  | The organization implements and maintains a documented policy or policies that address customer data privacy that is approved by a designated officer or the organization�s appropriate governing body (e.g., the Board or one of its committees).                  | Yes    | Yes    | Yes    | Yes    | GV.OC-03         |

#### GOVERN / Organizational Context / Stakeholder Service Expectations (GV.OC-04)
GV.OC-04: Critical objectives, capabilities, and services that stakeholders depend on or expect from the organization are understood and communicated

| Category ID  | Outcome               | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OC-04.01  | The organization maintains an inventory of key internal assets, business functions, and external dependencies that includes mappings to other assets, business functions, and information flows.     | Yes    | Yes    | Yes    | No     | GV.OC-04         |
| GV.OC-04.02  | The organization documents the business processes that are critical for the delivery of services and the functioning of the organization, and the impacts to the business if those processes are degraded or not functioning.                             | Yes    | Yes    | Yes    | Yes    | GV.OC-04         |
| GV.OC-04.03  | Resilience requirements to support the delivery of critical services are established for all operating states (e.g., under duress/attack, during recovery, and normal operations). | Yes    | No     | No     | No     | GV.OC-04         |
| GV.OC-04.04  | The organization prioritizes the resilience design, planning, testing, and monitoring of systems and other key internal and external dependencies according to their criticality to the supported business functions, enterprise mission, and to the financial services sector. | Yes    | Yes    | No     | No     | GV.OC-04         |

#### GOVERN / Organizational Context / Organizational Service Dependencies (GV.OC-05)
GV.OC-05: Outcomes, capabilities, and services that the organization depends on are understood and communicated

| Category ID  | Outcome| Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OC-05.01  | The organization identifies, assesses, and documents the key dependencies, interdependencies, and potential points of failure to support the delivery of critical services (e.g., systems, business processes, workforce, third parties, facilities, etc.)             | Yes    | Yes    | Yes    | Yes    | GV.OC-05         |
| GV.OC-05.02  | The organization has prioritized its external dependencies according to their criticality to the supported enterprise mission, business functions, and to the financial services sector.        | Yes    | Yes    | Yes    | No     | GV.OC-05         |
| GV.OC-05.03  | The organization defines objectives (e.g., Recovery Time Objective, Maximum Tolerable Downtime, Impact Tolerance) for the resumption of critical operations in alignment with business imperatives, stakeholder obligations, and critical infrastructure dependencies.   | Yes    | Yes    | Yes    | Yes    | GV.OC-05         |
| GV.OC-05.04  | Recovery point objectives to support data integrity are consistent with the organization's recovery time objectives, information flow dependencies between systems, and business obligations.   | Yes    | Yes    | Yes    | No     | GV.OC-05         |

---

### GOVERN / Risk Management Strategy (GV.RM)
Risk Management Strategy (GV.RM): The organization’s priorities, constraints, risk tolerance and appetite statements, and assumptions are established, communicated, and used to support operational risk decisions

#### GOVERN / Risk Management Strategy / Risk Management Objectives Agreement (GV.RM-01)
GV.RM-01: Risk management objectives are established and agreed to by organizational stakeholders

| Category ID   | Outcome                          | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-01.01   | Technology and cybersecurity risk management strategies and frameworks are approved by the governing authority (e.g., the Board or one of its committees) and incorporated into the overall business strategy and enterprise risk management framework.              | Yes    | Yes    | Yes    | Yes    | GV.RM-01         |
| GV.RM-01.02   | Technology and cybersecurity risk management strategies and frameworks are informed by applicable international, national, and financial services industry standards and guidelines.          | Yes    | Yes    | Yes    | Yes    | GV.RM-01         |
| GV.RM-01.03   | The organization has established, and maintains, technology and cybersecurity programs designed to protect the confidentiality, integrity and availability of its information and operational systems, commensurate with the organization's risk appetite and business needs. | Yes    | Yes    | Yes    | Yes    | GV.RM-01         |
| GV.RM-01.04   | Technology and cybersecurity risk management programs incorporate risk identification, measurement, monitoring, and reporting.          | Yes    | Yes    | Yes    | Yes    | GV.RM-01         |
| GV.RM-01.05   | The organization's technology, cybersecurity, resilience, and third-party risk management programs, policies, resources, and priorities are aligned and mutually supporting.                 | Yes    | Yes    | Yes    | No     | GV.RM-01         |

#### GOVERN / Risk Management Strategy / Risk Appetite & Risk Tolerance Statements (GV.RM-02)
GV.RM-02: Risk appetite and risk tolerance statements are established, communicated, and maintained

| Category ID   | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-02.01   | The governing authority (e.g., the Board or one of its committees) endorses and regularly reviews technology and cybersecurity risk appetite and is regularly informed about the status of, and material changes to, the organization's inherent risk profile.                     | Yes    | Yes    | Yes    | Yes    | GV.RM-02         |
| GV.RM-02.02   | The organization has established statements of technology and cybersecurity risk tolerance consistent with its risk appetite, and has integrated them into technology, cybersecurity, operational, and enterprise risk management practices.      | Yes    | Yes    | Yes    | No     | GV.RM-02         |
| GV.RM-02.03   | Determination of the organization's risk appetite and tolerance includes consideration of the organization's stakeholder obligations, role in critical infrastructure, and sector-specific risk analysis.  | Yes    | Yes    | Yes    | No     | GV.RM-02         |

#### GOVERN / Risk Management Strategy / Enterprise Risk Integration (GV.RM-03)
GV.RM-03: Technology and cybersecurity risk management activities and outcomes are included in enterprise risk management processes

| Category ID   | Outcome            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-03.01   | Technology and cybersecurity risk management frameworks and programs are integrated into the enterprise risk management framework.            | Yes    | Yes    | Yes    | Yes    | GV.RM-03         |
| GV.RM-03.02   | The organization's business continuity and resilience strategy and program align with and support the overall enterprise risk management framework.          | Yes    | Yes    | No     | No     | GV.RM-03         |
| GV.RM-03.03   | Technology and cybersecurity risk management and risk assessment processes are consistent with the organization's enterprise risk management policies, procedures, and methodologies and include criteria for the evaluation and categorization of enterprise-specific risks and threats. | Yes    | Yes    | Yes    | No     | GV.RM-03         |
| GV.RM-03.04   | Technology and cybersecurity risk management considerations are integrated into daily operations, cultural norms, management discussions, and management decision-making, and are tailored to address enterprise-specific risks (both internal and external). | Yes    | Yes    | No     | No     | GV.RM-03         |

#### GOVERN / Risk Management Strategy / Risk Response Strategic Direction (GV.RM-04)
GV.RM-04: Strategic direction that describes appropriate risk response options is established and communicated

| Category ID   | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-04.01   | The governing authority (e.g., the Board or one of its committees) and senior management provide guidance, direction, and credible challenge in the design and implementation of risk management strategies, assessment of identified risks against risk appetite and risk tolerance, and in the selection of risk treatment approaches. | Yes    | Yes    | Yes    | Yes    | GV.RM-04         |

#### GOVERN / Risk Management Strategy / Lines of Communication (GV.RM-05)
GV.RM-05: Lines of communication across the organization are established for technology and cybersecurity risks, including risks from suppliers and other third parties

| Category ID   | Outcome    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-05.01   | The organization has a process for monitoring its technology, cybersecurity, and third-party risks, including escalating those risks that exceed risk appetite to management and identifying risks with the potential to impact multiple operating units.| Yes    | Yes    | Yes    | Yes    | GV.RM-05         |
| GV.RM-05.02   | The organization establishes minimum requirements for its third-parties that include how the organizations will communicate and coordinate in times of emergency, including:<br>1) Joint maintenance of contingency plans;<br>2) Responsibilities for responding to incidents, including forensic investigations;<br>3) Planning and testing strategies that address severe events in order to identify single points of failure that would cause wide-scale disruption; and<br>4) Incorporating the potential impact of an incident into their BCM process and ensure resilience capabilities are in place. | Yes    | Yes    | Yes    | Yes    | GV.RM-05         |

#### GOVERN / Risk Management Strategy / Standardized Risk Management Method (GV.RM-06)
GV.RM-06: A standardized method for calculating, documenting, categorizing, and prioritizing technology and cybersecurity risks is established and communicated

| Category ID   | Outcome           | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-06.01   | Technology and cybersecurity risk management and risk assessment processes and methodologies are documented and regularly reviewed and updated to address changes in the risk profile and risk appetite, the evolving threat environment, and new technologies, products, services, and interdependencies.                | Yes    | Yes    | Yes    | Yes    | GV.RM-06         |

#### GOVERN / Risk Management Strategy / Strategic Opportunities (GV.RM-07)
GV.RM-07: Strategic opportunities (i.e., positive risks) are characterized and are included in organizational technology and cybersecurity risk discussions

| Category ID   | Outcome                 | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-07.01   | The organization has mechanisms in place to ensure that strategies, initiatives, opportunities, and emerging technologies (e.g., artificial intelligence, quantum computing, etc.) are evaluated both in terms of risks and uncertainties that are potentially detrimental to the organization, as well as potentially advantageous to the organization (i.e., positive risks). | Yes    | Yes    | No     | No     | GV.RM-07         |

#### GOVERN / Risk Management Strategy / Technology Assimilation & Implementations (GV.RM-08)
GV.RM-08: The risks of technology assimilation and implementations are managed

| Category ID   | Outcome| Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-08.01   | Technology and cybersecurity risk management frameworks are applied to, and are adapted as needed by, the organization's innovations in technology use and adoption of emerging technologies.            | Yes    | Yes    | Yes    | Yes    | None             |
| GV.RM-08.02   | Technology and cybersecurity risk management frameworks are applied to all technology projects and procurements to ensure that security requirements (e.g., data confidentiality, access control, event logging, etc.) are addressed consistently from project onset.           | Yes    | Yes    | Yes    | Yes    | None             |
| GV.RM-08.03   | The organization defines, maintains, and uses technical security standards, architectures, processes or practices (including automated tools when practical) to ensure the security of its applications and infrastructure.| Yes    | Yes    | Yes    | No     | None             |
| GV.RM-08.04   | The organization integrates the use of technology architecture in its governance processes to support consistent approaches to security and technology design, integration of third party services, consideration and adoption of new technologies, and investment and procurement decisioning.                   | Yes    | Yes    | Yes    | No     | None             |
| GV.RM-08.05   | The technology architecture and associated management processes should be comprehensive (e.g., consider the full life cycle of infrastructure, applications, emerging technologies, and relevant data) and designed to achieve security and resilience commensurate with business needs.                         | Yes    | Yes    | No     | No     | None             |
| GV.RM-08.06   | Technology programs and projects are formally governed and stakeholder engagement is managed to facilitate effective communication, awareness, credible challenge, and decision-making.                   | Yes    | Yes    | Yes    | Yes    | None             |
| GV.RM-08.07   | Technology projects follow an established project management methodology to manage delivery and delivery risks, produce consistent quality, and achieve business objectives and value.                   | Yes    | Yes    | Yes    | Yes    | None             |

#### GOVERN / Risk Management Strategy / Business Continuity & Resilience Risk Management (GV.RM-09)
GV.RM-09: The organization's business continuity and resilience requirement risks are managed

| Category ID   | Outcome                     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RM-09.01   | The organization has an enterprise-wide resilience strategy and program, including architecture, cyber resilience, business continuity, disaster recovery, and incident response, which support its mission, stakeholder obligations, critical infrastructure role, and risk appetite.  | Yes    | Yes    | Yes    | Yes    | None             |
| GV.RM-09.02   | The resilience program ensures that the organization can continue operating critical business functions and deliver services to stakeholders, to include critical infrastructure partners, during adverse incidents and cyber attacks (e.g., propagation of malware or extended system outages). | Yes    | No     | No     | No     | None             |

---

### GOVERN / Roles, Responsibilities, and Authorities (GV.RR)
Roles, Responsibilities, and Authorities (GV.RR): Technology and cybersecurity roles, responsibilities, and authorities to foster accountability, performance assessment, and continuous improvement are established and communicated

#### GOVERN / Roles, Responsibilities, and Authorities / Organizational Leadership Responsibility (GV.RR-01)
GV.RR-01: Organizational leadership is responsible and accountable for technology and cybersecurity risks and fosters a culture that is risk-aware, ethical, and continually improving

| Category ID   | Outcome          | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RR-01.01   | The governing authority (e.g., the Board or one of its committees) oversees and holds senior management accountable for implementing the organization�s technology and cybersecurity risk management strategies and frameworks.    | Yes    | Yes    | Yes    | Yes    | GV.RR-01         |
| GV.RR-01.02   | The governing authority (e.g., the Board or one of its committees) regularly reviews, oversees, and holds senior management accountable for implementing the organization�s third-party risk management strategy and program and for managing the organization's ongoing risks associated with the aggregate and specific use of third parties. | Yes    | Yes    | Yes    | Yes    | GV.RR-01         |
| GV.RR-01.03   | The governing authority (e.g., the Board or one of its committees) regularly reviews, oversees, and holds senior management accountable for implementing the organization�s resilience strategy and program and for managing the organization's ongoing resilience risks.   | Yes    | Yes    | Yes    | Yes    | GV.RR-01         |
| GV.RR-01.04   | The organization has designated a qualified Cybersecurity Officer (e.g., CISO) who is responsible and accountable for developing a cybersecurity strategy, overseeing and implementing its cybersecurity program, and enforcing its cybersecurity policy.  | Yes    | Yes    | Yes    | Yes    | GV.RR-01         |
| GV.RR-01.05   | The organization designates a qualified Technology Officer (e.g., CIO or CTO) who is responsible and accountable for developing technology strategy, overseeing and implementing its technology program, and enforcing its technology policy.          | Yes    | Yes    | Yes    | Yes    | GV.RR-01         |

#### GOVERN / Roles, Responsibilities, and Authorities / Risk Management Roles & Responsibilities (GV.RR-02)
GV.RR-02: Roles, responsibilities, and authorities related to technology and cybersecurity risk management are established, communicated, understood, and enforced

| Category ID   | Outcome                          | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RR-02.01   | The roles, responsibilities, qualifications, and skill requirements for personnel (employees and third parties) that implement, manage, and oversee the technology, cybersecurity, and resilience programs are defined, aligned, coordinated, and holistically managed.          | Yes    | Yes    | Yes    | Yes    | GV.RR-02         |
| GV.RR-02.02   | The organization has established and assigned roles and responsibilities for systematic cybersecurity threat identification, monitoring, detection, and event reporting processes, and ensures adequate coverage and organizational alignment for these functions.                | Yes    | Yes    | Yes    | No     | GV.RR-02         |
| GV.RR-02.03   | Resilience program roles and responsibilities are assigned to management across the organization to ensure risk assessment, planning, testing, and execution coverage for all critical business functions.      | Yes    | Yes    | Yes    | Yes    | GV.RR-02         |
| GV.RR-02.04   | Roles and responsibilities for the Third-Party Risk Management Program and for each third-party engagement are defined and assigned.            | Yes    | Yes    | Yes    | Yes    | GV.RR-02         |
| GV.RR-02.05   | Personnel (employees and third parties) who fulfill the organization�s physical security and cybersecurity objectives understand their roles and responsibilities.           | Yes    | Yes    | Yes    | Yes    | GV.RR-02         |
| GV.RR-02.06   | Roles and responsibilities for the inventory, ownership, and custodianship of applications, data and other technology assets are established and maintained.| Yes    | Yes    | Yes    | No     | GV.RR-02         |
| GV.RR-02.07   | Technology and cybersecurity risk management frameworks provide for segregation of duties between policy development, implementation, and oversight.        | Yes    | Yes    | No     | No     | GV.RR-02         |

#### GOVERN / Roles, Responsibilities, and Authorities / Resource Adequacy (GV.RR-03)
GV.RR-03: Adequate resources are allocated commensurate with technology and cybersecurity risk strategy, roles, responsibilities, and policies

| Category ID   | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RR-03.01   | The organization's budgeting and resourcing processes identify, prioritize, and address resource needs to manage identified technology and cybersecurity risks (e.g., skill shortages, headcount, new tools, incident-related expenses, and unsupported systems).    | Yes    | Yes    | Yes    | Yes    | GV.RR-03         |
| GV.RR-03.02   | The organization regularly assesses its skill and resource level requirements against its current personnel complement to determine gaps in resource need.                   | Yes    | Yes    | Yes    | Yes    | GV.RR-03         |
| GV.RR-03.03   | The organization provides adequate resources, appropriate authority, and access to the governing authority for the designated Cybersecurity Officer (e.g., CISO).             | Yes    | Yes    | Yes    | Yes    | GV.RR-03         |

#### GOVERN / Roles, Responsibilities, and Authorities / Human Resource Practices (GV.RR-04)
GV.RR-04: Cybersecurity is included in human resources practices

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.RR-04.01   | The organization conducts (or causes the conduct of) background/screening checks on all personnel (employees and third party) upon hire/retention, at regular intervals throughout employment, and upon a change in role commensurate with their access to critical data and systems.    | Yes    | Yes    | Yes    | Yes    | GV.RR-04         |
| GV.RR-04.02   | The organization establishes processes and controls to mitigate cyber risks related to employment termination, as permitted by law, to include the return or disposition of all organizational assets.                 | Yes    | Yes    | Yes    | Yes    | GV.RR-04         |
| GV.RR-04.03   | The organization integrates insider threat considerations into its human resource, risk management, and control programs to address the potential for malicious or unintentional harm by trusted employees or third parties.                            | Yes    | Yes    | Yes    | No     | GV.RR-04         |

---

### GOVERN / Policies, Processes, and Procedures (GV.PO)
Policies, Processes, and Procedures (GV.PO): Organizational technology and cybersecurity policies are established, communicated, and enforced

#### GOVERN / Policies, Processes, and Procedures / Establishment of Policies & Procedures (GV.PO-01)
GV.PO-01: Policies for managing technology and cybersecurity risks are established based on organizational context, cybersecurity strategy, and priorities and is communicated and enforced

| Category ID   | Outcome                           | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.PO-01.01   | Technology and cybersecurity policies are documented, maintained and approved by the governing authority (e.g., the Board or one of its committees) or a designated executive.              | Yes    | Yes    | Yes    | Yes    | GV.PO-01         |
| GV.PO-01.02   | The accountable governing body, and applicable cybersecurity program and policies, for any given organizational unit, affiliate, or merged entity are clearly established, applied, and communicated. | Yes    | Yes    | No     | No     | GV.PO-01         |
| GV.PO-01.03   | The organization's incentive programs are consistent with cyber risk management objectives, and technology and cybersecurity policies integrate with an employee accountability policy to ensure that all personnel are held accountable for complying with policies. | Yes    | Yes    | Yes    | Yes    | GV.PO-01         |
| GV.PO-01.04   | All personnel (employees and third party) consent to policies addressing acceptable technology use, social media use, personal device use (e.g., BYOD), confidentiality, and/or other security-related policies and agreements as warranted by their position.        | Yes    | Yes    | Yes    | Yes    | GV.PO-01         |
| GV.PO-01.05   | Technology and cybersecurity processes, procedures, and controls are established in alignment with cybersecurity policy.   | Yes    | Yes    | Yes    | Yes    | GV.PO-01         |
| GV.PO-01.06   | Physical and environmental security policies are implemented and managed.| Yes    | Yes    | Yes    | Yes    | GV.PO-01         |
| GV.PO-01.07   | The organization maintains documented business continuity and resilience program policies and procedures approved by the governing authority (e.g., the Board or one of its committees).      | Yes    | Yes    | Yes    | Yes    | GV.PO-01         |
| GV.PO-01.08   | The organization maintains documented third-party risk management program policies and procedures approved by the governing authority (e.g., the Board or one of its committees).            | Yes    | Yes    | Yes    | Yes    | GV.PO-01         |

#### GOVERN / Policies, Processes, and Procedures / Policy & Procedure Review & Update (GV.PO-02)
GV.PO-02: Policies for managing technology and cybersecurity risks are reviewed, updated, communicated, and enforced to reflect changes in requirements, threats, technology, and organizational mission

| Category ID   | Outcome                | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.PO-02.01   | The cybersecurity policy is regularly reviewed, revised, and communicated under the leadership of a designated Cybersecurity Officer (e.g., CISO) to address changes in the risk profile and risk appetite, the evolving threat environment, and new technologies, products, services, and interdependencies.                 | Yes    | Yes    | Yes    | Yes    | GV.PO-02         |

---

### GOVERN / Oversight (GV.OV)
Oversight (GV.OV): Results of organization-wide technology and cybersecurity risk management activities and performance are used to inform, improve, and adjust the risk management strategy

#### GOVERN / Oversight / Risk Management Strategy Outcomes Review (GV.OV-01)
GV.OV-01: Technology and cybersecurity risk management strategy outcomes are reviewed to inform and adjust strategy and direction

| Category ID   | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OV-01.01   | The governing authority (e.g., the Board or one of its committees) regularly reviews and evaluates the organization's ability to manage its technology, cybersecurity, third-party, and resilience risks.                    | Yes    | Yes    | Yes    | Yes    | GV.OV-01         |
| GV.OV-01.02   | The designated Cybersecurity Officer (e.g., CISO) periodically reports to the appropriate governing authority (e.g., the Board or one of its committees) or equivalent governing body on the status of cybersecurity within the organization.    | Yes    | Yes    | Yes    | Yes    | GV.OV-01         |
| GV.OV-01.03   | The designated Technology Officer (e.g., CIO or CTO) regularly reports to the governing authority (e.g., the Board or one of its committees) on the status of technology use and risks within the organization.               | Yes    | Yes    | Yes    | Yes    | GV.OV-01         |

#### GOVERN / Oversight / Risk Management Strategy Review & Adjustment (GV.OV-02)
GV.OV-02: The technology and cybersecurity risk management strategies are reviewed and adjusted to ensure coverage of organizational requirements and risks

| Category ID   | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OV-02.01   | The organization regularly assesses its inherent technology and cybersecurity risks and ensures that changes to the business and threat environment lead to updates to the organization's strategies, programs, risk appetite and risk tolerance.  | Yes    | Yes    | Yes    | Yes    | GV.OV-02         |
| GV.OV-02.02   | The organization determines and articulates how it intends to maintain an acceptable level of residual technology and cybersecurity risk as set by the governing authority (e.g., the Board or one of its committees).                            | Yes    | Yes    | Yes    | No     | GV.OV-02         |

#### GOVERN / Oversight / Risk Management Performance Measurement (GV.OV-03)
GV.OV-03: Organizational technology and cybersecurity risk management performance is evaluated and reviewed for adjustments needed

| Category ID   | Outcome   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.OV-03.01   | The organization develops, implements, and reports to management and the governing body (e.g., the Board or one of its committees) key technology and cybersecurity risk and performance indicators and metrics to measure, monitor, and report actionable indicators.        | Yes    | Yes    | Yes    | No     | GV.OV-03         |
| GV.OV-03.02   | Resilience program performance is measured and regularly reported to senior executives and the governing authority (e.g., the Board or one of its committees).                           | Yes    | Yes    | Yes    | Yes    | GV.OV-03         |

---

### GOVERN / Cybersecurity Supply Chain Risk Management (GV.SC)
Supply Chain Risk Management (GV.SC): Supply chain risk management processes are identified, established, managed, monitored, and improved by organizational stakeholders

#### GOVERN / Supply Chain Risk Management / Supply Chain Risk Management Program (GV.SC-01)
GV.SC-01: A supply chain risk management program, strategy, objectives, policies, and processes are established and agreed to by organizational stakeholders

| Category ID   | Outcome| Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.SC-01.01   | The organization maintains a third-party risk management strategy and program to identify and manage the risks associated with third parties throughout their lifecycles in a timely manner, including in support of sector-critical systems and operations, to ensure alignment within risk appetite.   | Yes    | Yes    | Yes    | Yes    | GV.SC-01         |
| GV.SC-01.02   | The organization regularly assesses the risk of its ongoing use of third parties in aggregate, considering factors such as critical service dependencies, vendor concentration, geographical/geopolitical exposure, fourth-party impacts, and financial sector co-dependencies.       | Yes    | Yes    | No     | No     | GV.SC-01         |

#### GOVERN / Supply Chain Risk Management / Third Party Roles & Responsibilities (GV.SC-02)
GV.SC-02: Roles and responsibilities for suppliers, customers, and partners are established, communicated, and coordinated internally and externally

| Category ID   | Outcome              | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.SC-02.01   | The organization clearly defines, and includes in contractual agreements, the division of cybersecurity and technology risk management responsibilities between the organization and its third parties (e.g., a Shared Responsibilities Model).                    | Yes    | Yes    | Yes    | Yes    | GV.SC-02         |

#### GOVERN / Supply Chain Risk Management / Supply Chain Risk Management Integration (GV.SC-03)
GV.SC-03: Supply chain risk management is integrated into cybersecurity and enterprise risk management, risk assessment, and improvement processes

| Category ID   | Outcome                   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.SC-03.01   | The organization's third-party risk management strategy and program aligns with and supports its enterprise, technology, cybersecurity, and resilience risk management frameworks and programs.                            | Yes    | Yes    | Yes    | Yes    | GV.SC-03         |

#### GOVERN / Supply Chain Risk Management / Supplier Identification & Prioritization (GV.SC-04)
GV.SC-04: Suppliers are known and prioritized by criticality

| Category ID   | Outcome            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.SC-04.01   | The organization regularly identifies, inventories, and risk-ranks third-party relationships that are in place, and addresses any identified relationships that were established without formal approval.           | Yes    | Yes    | Yes    | Yes    | GV.SC-04         |

#### GOVERN / Supply Chain Risk Management / Third Party Incident Management Integration (GV.SC-08)
GV.SC-08: Relevant suppliers and other third parties are included in incident planning, response, and recovery activities

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.SC-08.01   | The organization's resilience strategy, plans, tests, and exercises incorporate its external dependencies and critical business partners.| Yes    | Yes    | Yes    | Yes    | GV.SC-08         |

#### GOVERN / Supply Chain Risk Management / Supply Chain Security Practice Integration (GV.SC-09)
GV.SC-09: Supply chain security practices are integrated into technology, cybersecurity, and enterprise risk management programs, and their performance is monitored throughout the technology product and service life cycle

| Category ID   | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.SC-09.01   | Consideration is specifically given to the implications of organizational third-party dependence, requirements, contracts, and interactions in the design, operation, monitoring, and improvement of policies, procedures, and controls to ensure the fulfillment of business requirements within risk appetite. | Yes    | Yes    | Yes    | No     | GV.SC-09         |

---

### GOVERN / Independent Risk Management Function (GV.IR)
Independent Risk Management Function (GV.IR): The organization has an independent risk management function

#### GOVERN / Independent Risk Management Function / Independent Risk Management Function (GV.IR-01)
GV.IR-01: The independent risk management function provides assurance that the technology and cybersecurity risk management frameworks have been implemented according to policy and are consistent with the organization's risk appetite and tolerance

| Category ID   | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.IR-01.01   | The organization's enterprise-wide technology and cybersecurity risk management frameworks align with and support an independent risk management function that provides assurance that the frameworks are implemented consistently and as intended.        | Yes    | Yes    | Yes    | No     | None             |
| GV.IR-01.02   | The independent risk management function has sufficient independence, stature, authority, resources, and access to the governing body (e.g., the Board or one of its committees), including reporting lines, to ensure consistency with the organization's risk management frameworks.         | Yes    | Yes    | Yes    | No     | None             |
| GV.IR-01.03   | The independent risk management function has an understanding of the organization's structure, technology and cybersecurity strategies and programs, and relevant risks and threats.     | Yes    | Yes    | Yes    | No     | None             |

#### GOVERN / Independent Risk Management Function / Independent Risk Management Evaluation (GV.IR-02)
GV.IR-02: The independent risk management function evaluates the appropriateness of the risk management program for the organization's risk appetite and proposes program improvements as warranted

| Category ID   | Outcome            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.IR-02.01   | The independent risk management function regularly evaluates the appropriateness of the technology and cybersecurity risk management programs to the organization's risk appetite and inherent risk environment| Yes    | Yes    | Yes    | No     | None             |
| GV.IR-02.02   | The independent risk management function regularly assesses the organization's controls and cybersecurity risk exposure, identifies opportunities for improvement based on assessment results, and recommends program improvements   | Yes    | Yes    | Yes    | No     | None             |

#### GOVERN / Independent Risk Management Function / Independent Risk Management Reporting (GV.IR-03)
GV.IR-03: The independent risk management function reports on the implementation of the technology and cybersecurity risk management frameworks to the governing authority (e.g., the Board or one of its committees)

| Category ID   | Outcome                  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.IR-03.01   | The independent risk management function reports to the governing authority (e.g., the Board or one of its committees) and to the designated risk management officer within the organization on the implementation of the technology and cybersecurity risk management frameworks throughout the organization and its independent assessment of risk posture. | Yes    | Yes    | Yes    | No     | None             |

---

### GOVERN / Independent Audit Function (GV.AU)
Independent Audit Function (GV.AU): The organization has an independent audit function to support oversight of the technology and cybersecurity programs

#### GOVERN / Independent Audit Function / Independent Audit Compliance Assessment (GV.AU-01)
GV.AU-01: The independent audit function assesses compliance with internal controls and applicable laws and regulations

| Category ID   | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.AU-01.01   | The organization has an independent audit function (i.e., internal audit group or external auditor) that follows generally accepted audit practices and approved audit policies and procedures.| Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-01.02   | The organization has an independent audit plan that provides for the evaluation of technology and cybersecurity risk, including compliance with the approved risk management framework, policies, and processes for technology, cybersecurity, and resilience; and how well the organization adapts to the evolving risk environment while remaining within its stated risk appetite and tolerance. | Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-01.03   | The independent audit function tests technology management, cybersecurity, incident response, and resilience policies and controls.     | Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-01.04   | The independent audit function evaluates and tests third-party risk management policies and controls, identifies weaknesses and gaps, and recommends improvements to senior management and the governing authority (e.g., the Board or one of its committees). | Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-01.05   | An independent audit function assesses compliance with applicable laws and regulations.           | Yes    | Yes    | Yes    | Yes    | None             |

#### GOVERN / Independent Audit Function / Independent Audit Procedures (GV.AU-02)
GV.AU-02: The independent audit function updates its procedures and audit plans to adjust to the evolving technology and cybersecurity environment

| Category ID   | Outcome           | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.AU-02.01   | A formal process is in place for the independent audit function to review and update its procedures and audit plans regularly or in response to changes in relevant standards, the technology environment, or the business environment.             | Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-02.02   | A formal process is in place for the independent audit function to update its procedures and audit plans based on changes to the organization's risk appetite, risk tolerance, threat environment, and evolving risk profile.                         | Yes    | Yes    | Yes    | Yes    | None             |

#### GOVERN / Independent Audit Function / Independent Audit Reporting (GV.AU-03)
GV.AU-03: The independent audit function identifies, tracks, and reports significant changes in the organization's risk exposure to the governing authority (e.g., the Board or one of its committees)

| Category ID   | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| GV.AU-03.01   | The independent audit function reviews technology and cybersecurity practices and identifies weaknesses and gaps.| Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-03.02   | The independent audit function tracks identified issues and corrective actions from internal audits and independent testing/assessments to ensure timely resolution.   | Yes    | Yes    | Yes    | Yes    | None             |
| GV.AU-03.03   | The independent audit function reports to the governing authority (e.g., the Board or one of its committees) within the organization, including when its assessment differs from that of the organization, or when risk tolerance has been exceeded in any part of the organization.| Yes    | Yes    | Yes    | Yes    | None             |

---
## IDENTIFY (ID)
IDENTIFY (ID): The organization's current technology and cybersecurity risks are understood

### IDENTIFY / Asset Management (ID.AM)
Asset Management (ID.AM): Assets (e.g., data, hardware, software, systems, facilities, services, people) that enable the organization to achieve business purposes are identified and managed consistent with their relative importance to organizational objectives and the organization's risk strategy

#### IDENTIFY / Asset Management / Hardware Inventory (ID.AM-01)
ID.AM-01: Inventories of hardware managed by the organization are maintained

| Category ID  | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-01.01  | The organization maintains a current and complete asset inventory of physical devices, hardware, and information systems.  | Yes    | Yes    | Yes    | Yes    | ID.AM-01         |

#### IDENTIFY / Asset Management / Software, Services, & Systems Inventory (ID.AM-02)
ID.AM-02: Inventories of software, services, and systems managed by the organization are maintained

| Category ID  | Outcome                        | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-02.01  | The organization maintains a current and complete inventory of software platforms, business applications, and other software assets (e.g., virtual machines and virtual network devices). | Yes    | Yes    | Yes    | Yes    | ID.AM-02         |

#### IDENTIFY / Asset Management / Network Communications & Data Flows (ID.AM-03)
ID.AM-03: Representations of the organization’s authorized network communication and internal and external network data flows are maintained

| Category ID  | Outcome         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-03.01  | The organization maintains current maps of network resources, mobile resources, external connections, network-connected third parties, and network data flows.                           | Yes    | Yes    | Yes    | Yes    | ID.AM-03         |

#### IDENTIFY / Asset Management / Supplier Services Inventory (ID.AM-04)
ID.AM-04: Inventories of services provided by suppliers are maintained

| Category ID  | Outcome         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-04.01  | Hardware, software, and data assets maintained by or located at suppliers or other third parties are included in asset management inventories and lifecycle management processes as required for effective management and security.                          | Yes    | Yes    | Yes    | Yes    | ID.AM-04         |

#### IDENTIFY / Asset Management / Asset Protection Prioritization (ID.AM-05)
ID.AM-05: Assets are prioritized based on classification, criticality, resources, and impact on the mission

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-05.01   | The organization establishes and maintains risk-based policies and procedures for the classification of hardware, software, and data assets based on sensitivity and criticality.                  | Yes    | Yes    | Yes    | No     | ID.AM-05         |
| ID.AM-05.02   | The organization's hardware, software, and data assets are prioritized for protection based on their sensitivity, criticality, vulnerability, business value, and dependency role in the delivery of critical services.          | Yes    | Yes    | Yes    | No     | ID.AM-05         |

#### IDENTIFY / Asset Management / Data & Metadata Inventory (ID.AM-07)
ID.AM-07: Inventories of data and corresponding metadata for designated data types are maintained

| Category ID   | Outcome   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-07.01   | The organization maintains a current inventory of the data being created, stored, or processed by its information assets and data flow diagrams depicting key internal and external data flows.    | Yes    | Yes    | Yes    | No     | ID.AM-07         |

#### IDENTIFY / Asset Management / Asset Life Cycle Management (ID.AM-08)
ID.AM-08: Systems, hardware, software, services, and data are managed throughout their life cycles

| Category ID   | Outcome            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.AM-08.01   | The organization establishes and maintains asset lifecycle management policies and procedures to ensure that assets are acquired, tracked, implemented, used, decommissioned, and protected commensurate with their sensitivity, criticality, and business value.           | Yes    | Yes    | Yes    | No     | ID.AM-08         |
| ID.AM-08.02   | The organization establishes policies, and employs methods to identify, assess, and manage technology solutions that are acquired, managed, or used outside of established, governed technology and cybersecurity processes (i.e., "Shadow IT"). | Yes    | Yes    | Yes    | No     | ID.AM-08         |
| ID.AM-08.03   | The organization establishes policies, standards, and procedures for data governance, data management, and data retention consistent with its legal obligations and the value of data as an organizational asset.                             | Yes    | Yes    | Yes    | No     | ID.AM-08         |
| ID.AM-08.04   | The organization's asset management processes ensure the protection of sensitive data throughout removal, transfers, maintenance, end-of-life, and secure disposal or re-use.            | Yes    | Yes    | Yes    | Yes    | ID.AM-08         |
| ID.AM-08.05   | The organization defines and implements standards and procedures, consistent with its data retention policy, for destroying or securely erasing data, media, and storage devices when the data is no longer needed.                          | Yes    | Yes    | Yes    | Yes    | ID.AM-08         |
| ID.AM-08.06   | Minimum cybersecurity requirements for third-parties cover the entire relationship lifecycle, from the acquisition of data through the return or destruction of data, to include limitations on data use, access, storage, and geographic location.      | Yes    | Yes    | Yes    | Yes    | ID.AM-08         |

---

### IDENTIFY / Risk Assessment (ID.RA)
Risk Assessment (ID.RA): The technology and cybersecurity risks to the organization, assets, and individuals are understood by the organization

#### IDENTIFY / Risk Assessment / Asset Vulnerability Identification (ID.RA-01)
ID.RA-01: Vulnerabilities in assets are identified, validated, and recorded

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-01.01   | The organization identifies, assesses, and documents risks and potential vulnerabilities associated with assets, to include workforce, data, technology, facilities, services, and connections.    | Yes    | Yes    | Yes    | Yes    | ID.RA-01         |
| ID.RA-01.02   | The organization's business units ensure that information regarding cyber risk is shared with the appropriate level of senior management in a timely manner, so that they can address and respond to emerging cyber risk.       | Yes    | Yes    | Yes    | Yes    | ID.RA-01         |
| ID.RA-01.03   | The organization establishes and maintains standards and capabilities for ongoing vulnerability management, including systematic scans, or reviews reasonably designed to identify known cyber vulnerabilities and upgrade opportunities, across the organization's environments and assets.              | Yes    | Yes    | Yes    | Yes    | ID.RA-01         |

#### IDENTIFY / Risk Assessment / Information Sharing Forums (ID.RA-02)
ID.RA-02: Cyber threat intelligence is received from information sharing forums and sources

| Category ID   | Outcome                    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-02.01   | The organization participates actively (in alignment with its business operations, inherent risk, and complexity) in information-sharing groups and collectives (e.g., cross-industry, cross-government and cross-border groups) to gather, distribute and analyze information about cyber practices, cyber threats, and early warning indicators relating to cyber threats. | Yes    | Yes    | Yes    | No     | ID.RA-02         |
| ID.RA-02.02   | The organization shares authorized information on its cyber resilience framework and the effectiveness of protection technologies bilaterally with trusted external stakeholders to promote the understanding of each party’s approach to securing systems.           | Yes    | Yes    | Yes    | No     | ID.RA-02         |

#### IDENTIFY / Risk Assessment / Threat Identification (ID.RA-03)
ID.RA-03: Internal and external threats to the organization are identified and recorded

| Category ID   | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-03.01   | The organization, on an ongoing basis, identifies, analyzes, correlates, characterizes, and reports threats that are internal and external to the firm.| Yes    | Yes    | Yes    | Yes    | ID.RA-03         |
| ID.RA-03.02   | The organization solicits and considers threat intelligence received from the organization's stakeholders, service and utility providers, and other industry and security organizations.   | Yes    | Yes    | Yes    | Yes    | ID.RA-03         |
| ID.RA-03.03   | The organization includes in its threat analysis those cyber threats which could trigger extreme but plausible cyber events, even if they are considered unlikely to occur or have never occurred in the past.         | Yes    | Yes    | Yes    | No     | ID.RA-03         |
| ID.RA-03.04   | The organization regularly reviews and updates its threat analysis methodology, threat information sources, and supporting tools.    | Yes    | Yes    | Yes    | Yes    | ID.RA-03         |

#### IDENTIFY / Risk Assessment / Impact & Likelihood Analysis (ID.RA-04)
ID.RA-04: Potential impacts and likelihoods of threats exploiting vulnerabilities are identified and recorded

| Category ID   | Outcome            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-04.01   | The organization's risk assessment approach includes the analysis and characterization of the likelihood and potential business impact of identified risks being realized.      | Yes    | Yes    | Yes    | Yes    | ID.RA-04         |

#### IDENTIFY / Risk Assessment / Risk Exposure Determination & Prioritization (ID.RA-05)
ID.RA-05: Threats, vulnerabilities, likelihoods, and impacts are used to understand inherent risk and inform risk response prioritization

| Category ID   | Outcome        | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-05.01   | Threats, vulnerabilities, likelihoods, and impacts are used to determine overall technology, cybersecurity, and resilience risk to the organization.| Yes    | Yes    | Yes    | Yes    | ID.RA-05         |
| ID.RA-05.02   | The organization has established threat modeling capabilities to identify how and why critical assets might be compromised by a threat actor, what level of protection is needed for those critical assets, and what the impact would be if that protection failed.       | Yes    | Yes    | No     | No     | ID.RA-05         |
| ID.RA-05.03   | The organization's business units assess, on an ongoing basis, the technology, cybersecurity, and resilience risks associated with the activities of the business unit.   | Yes    | Yes    | Yes    | No     | ID.RA-05         |
| ID.RA-05.04   | The organization uses scenario planning, table-top-exercises, or similar event analysis techniques to identify vulnerabilities and determine potential impacts to critical infrastructure, technology, and business processes.           | Yes    | Yes    | Yes    | No     | ID.RA-05         |

#### IDENTIFY / Risk Assessment / Risk Response Determination (ID.RA-06)
ID.RA-06: Risk responses are chosen, prioritized, planned, tracked, and communicated

| Category ID   | Outcome   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-06.01   | Technology and cybersecurity risk management programs and risk assessment processes produce actionable recommendations that the organization uses to select, design, prioritize, implement, maintain, evaluate, and modify cybersecurity and technology controls.   | Yes    | Yes    | Yes    | Yes    | ID.RA-06         |
| ID.RA-06.02   | The implementation of responses to address identified risks (i.e., risk avoidance, risk mitigation, risk acceptance, or risk transfer (e.g., cyber insurance)) are formulated, assessed, documented, and prioritized based on criticality to the business.         | Yes    | Yes    | Yes    | Yes    | ID.RA-06         |
| ID.RA-06.03   | Technology and cybersecurity programs identify and implement controls to manage applicable risks within the risk appetite set by the governing authority (e.g., the Board or one of its committees).              | Yes    | Yes    | Yes    | Yes    | ID.RA-06         |
| ID.RA-06.04   | The organization assesses the threats, impacts, and risks that could adversely affect the organization's ability to provide services on an ongoing basis, and develops its resilience requirements and plans to address those risks.                   | Yes    | Yes    | Yes    | Yes    | ID.RA-06         |
| ID.RA-06.05   | The organization defines and implements standards and procedures to prioritize and remediate issues identified in vulnerability scanning or penetration testing, including emergency or zero-day threats and vulnerabilities.                           | Yes    | Yes    | Yes    | Yes    | ID.RA-06         |
| ID.RA-06.06   | The organization follows documented procedures, consistent with established risk response processes, for mitigating or accepting the risk of vulnerabilities or weaknesses identified in exercises and testing or when responding to incidents.          | Yes    | Yes    | Yes    | Yes    | ID.RA-06         |

#### IDENTIFY / Risk Assessment / Change & Exception Management (ID.RA-07)
ID.RA-07: Changes and exceptions are managed, assessed for risk impact, recorded, and tracked

| Category ID   | Outcome   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-07.01   | The organization defines and implements change management standards and procedures, to include emergency change procedures, that explicitly address risk identified both prior to and during a change, any new risk created post-change, as well as the reviewing and approving authorities (e.g., change advisory boards).               | Yes    | Yes    | Yes    | Yes    | ID.RA-07         |
| ID.RA-07.02   | Risk-based criteria are used to categorize each system change, to include emergency changes, to determine the necessary change process standards to apply for change planning, rollback planning, pre-change testing, change access control, post-change verification, and change review and approval.    | Yes    | Yes    | Yes    | No     | ID.RA-07         |
| ID.RA-07.03   | Technology projects and system change processes ensure that requisite changes in security posture, data classification and flows, architecture, support documentation, business processes, and business resilience plans are addressed.        | Yes    | Yes    | Yes    | No     | ID.RA-07         |
| ID.RA-07.04   | Policy exceptions, risk mitigation plans, and risk acceptances resulting from assessments and evaluations, such as testing, exercises, audits, etc., are formally managed, approved, escalated to defined levels of management, and tracked to closure.                  | Yes    | Yes    | Yes    | No     | ID.RA-07         |
| ID.RA-07.05   | The organization establishes and maintains an exception management process for identified vulnerabilities that cannot be mitigated within target timeframes.                 | Yes    | Yes    | Yes    | Yes    | ID.RA-07         |

#### IDENTIFY / Risk Assessment / Vulnerability Disclosure Response (ID.RA-08)
ID.RA-08: Processes for receiving, analyzing, and responding to vulnerability disclosures are established

| Category ID   | Outcome            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.RA-08.01   | The organization has established enterprise processes for soliciting, receiving and appropriately channeling vulnerability disclosures from:<br>(1) Public sources (e.g., customers and security researchers);<br>(2) Vulnerability sharing forums (e.g., FS-ISAC);<br>(3) Third-parties (e.g., cloud vendors);<br>(4) Internal sources (e.g., development teams). | Yes    | Yes    | Yes    | Yes    | ID.RA-08         |
| ID.RA-08.02   | The organization has established enterprise processes to analyze disclosed vulnerabilities with a focus on:<br>(1) Determining its validity;<br>(2) Assessing its scope (e.g., affected assets);<br>(3) Determining its severity and impact;<br>(4) Identifying affected stakeholders or customers; and<br>(5) Analyzing options to respond.                  | Yes    | Yes    | Yes    | Yes    | ID.RA-08         |

---

### IDENTIFY / Improvement (ID.IM)
Improvement (ID.IM): Improvements to organizational technology and cybersecurity risk management processes, procedures and activities are identified across all Profile Functions

#### IDENTIFY / Improvement / Continuous Improvements Evaluation (ID.IM-01)
ID.IM-01: Improvements are identified from evaluations

| Category ID   | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.IM-01.01   | Technology, cybersecurity, and resilience controls are regularly assessed and/or tested for design and operating effectiveness.         | Yes    | Yes    | Yes    | Yes    | ID.IM-01         |
| ID.IM-01.02   | The organization implements a regular process to collect, store, report, benchmark, and assess trends in actionable performance indicators and risk metrics (e.g., threat KRIs, security incident metrics, vulnerability metrics, and operational measures).      | Yes    | Yes    | Yes    | No     | ID.IM-01         |
| ID.IM-01.03   | The organization establishes specific objectives, performance criteria, benchmarks, and tolerance limits to identify areas that have improved or are in need of improvement over time.      | Yes    | Yes    | Yes    | No     | ID.IM-01         |
| ID.IM-01.04   | Technology and cybersecurity programs include elements designed to assess, manage, and continually improve the quality of program delivery in addressing stakeholder requirements and risk reduction.   | Yes    | Yes    | Yes    | Yes    | ID.IM-01         |
| ID.IM-01.05   | The organization's third-party risk management program is regularly assessed, reported on, and improved. | Yes    | Yes    | Yes    | Yes    | ID.IM-01         |

#### IDENTIFY / Improvement / Tests & Exercises (ID.IM-02)
ID.IM-02: Improvements are identified from tests and exercises, including those done in coordination with suppliers and relevant third parties

| Category ID   | Outcome                            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.IM-02.01   | The organization conducts regular, independent penetration testing and red team testing on the organization's network, internet-facing systems, critical applications, and associated controls to identify gaps in cybersecurity defenses.               | Yes    | Yes    | Yes    | Yes    | ID.IM-02         |
| ID.IM-02.02   | The thoroughness and results of independent penetration testing are regularly reviewed to help determine the need to rotate testing vendors to obtain fresh independent perspectives.    | Yes    | Yes    | Yes    | No     | ID.IM-02         |
| ID.IM-02.03   | The organization tests and validates the effectiveness of the incident detection, reporting, and communication processes and protocols with internal and external stakeholders.           | Yes    | Yes    | Yes    | No     | ID.IM-02         |
| ID.IM-02.04   | The organization's testing program validates the effectiveness of its resilience strategy and response, disaster recovery, and resumption plans on a regular basis or upon major changes to business or system functions, and includes external stakeholders as required.    | Yes    | Yes    | Yes    | Yes    | ID.IM-02         |
| ID.IM-02.05   | The organization establishes testing programs that include a range of scenarios, including severe but plausible scenarios (e.g., disruptive, destructive, corruptive), that could affect the organization's ability to service internal and external stakeholders. | Yes    | Yes    | Yes    | Yes    | ID.IM-02         |
| ID.IM-02.06   | The organization designs and tests its systems and processes, and employs third-party support resources (e.g., Sheltered Harbor), to enable recovery of accurate data (e.g., material financial transactions) sufficient to support defined business recovery time and recovery point objectives.  | Yes    | Yes    | Yes    | Yes    | ID.IM-02         |
| ID.IM-02.07   | The organization's governing body (e.g., the Board or one of its committees) and senior management are involved in testing as part of a crisis management team and are informed of test results.                            | Yes    | Yes    | No     | No     | ID.IM-02         |
| ID.IM-02.08   | The organization tests and exercises, independently and in coordination with other critical sector partners, its ability to support sector-wide resilience in the event of extreme financial stress or the instability of external dependencies, such as connectivity to markets, payment systems, clearing entities, etc.      | Yes    | No     | No     | No     | ID.IM-02         |
| ID.IM-02.09   | Corrective actions for gaps identified during security-related, incident management, response plan, and disaster recovery testing are retested and validated, or have a formal risk acceptance or risk exception.           | Yes    | Yes    | Yes    | No     | ID.IM-02         |

#### IDENTIFY / Improvement / Improvements from Lessons Learned (ID.IM-03)
ID.IM-03: Improvements are identified from execution of operational processes, procedures, and activities

| Category ID   | Outcome    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.IM-03.01   | A formal process is in place to improve protection controls and processes by integrating recommendations, findings, and lessons learned from exercises, testing, audits, assessments, and incidents.  | Yes    | Yes    | Yes    | Yes    | ID.IM-03         |
| ID.IM-03.02   | The organization establishes a systematic and comprehensive program to regularly evaluate and improve its monitoring and detection processes and controls as the threat environment changes, tools and techniques evolve, and lessons are learned.| Yes    | Yes    | Yes    | No     | ID.IM-03         |

#### IDENTIFY / Improvement / Plans Affecting Operations (ID.IM-04)
ID.IM-04: Response and recovery plans (e.g., incident response plan, business continuity plan, disaster recovery plan, etc.) are established, communicated, maintained, and improved

| Category ID   | Outcome      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| ID.IM-04.01   | The organization's business continuity, disaster recovery, crisis management, and response plans are in place and managed, aligned with each other, and incorporate considerations of cyber incidents. | Yes    | Yes    | Yes    | Yes    | ID.IM-04         |
| ID.IM-04.02   | The organization's incident response and business continuity plans contain clearly defined roles, responsibilities, and levels of decision-making authority, and include all needed areas of participation and expertise across the organization and key third-parties.                        | Yes    | Yes    | Yes    | Yes    | ID.IM-04         |
| ID.IM-04.03   | Recovery plans include service resumption steps for all operating environments, including traditional, alternate recovery, and highly available (e.g., cloud) infrastructures.    | Yes    | Yes    | Yes    | No     | ID.IM-04         |
| ID.IM-04.04   | The organization has plans to identify, in a timely manner, the status of all transactions and member positions at the time of a disruption, supported by corresponding recovery point objectives.      | Yes    | Yes    | No     | No     | ID.IM-04         |
| ID.IM-04.05   | Recovery plans include restoration of resilience following a long term loss of capability (e.g., at an alternate site or a third-party), detailing when the plan should be activated and implementation steps.                            | Yes    | Yes    | No     | No     | ID.IM-04         |
| ID.IM-04.06   | The organization has established and implemented plans to identify and mitigate the cyber risks it poses through interconnectedness to sector partners and external stakeholders. | Yes    | No     | No     | No     | ID.IM-04         |
| ID.IM-04.07   | The organization pre-identifies, pre-qualifies, and retains third party incident management support and forensic service firms, as required, that can be called upon to quickly assist with incident response, investigation, and recovery.| Yes    | Yes    | Yes    | Yes    | ID.IM-04         |
| ID.IM-04.08   | The organization regularly reviews response strategy, incident management plans, recovery plans, and associated tests and exercises and updates them, as necessary, based on:<br>1) Lessons learned from incidents (internal/external)<br>2) Current cyber threat intelligence (internal/external)<br>3) Recent and wide-scale cyber attack scenarios<br>4) Operationally and technically plausible future cyber attacks<br>5) Organizational or technical environment changes<br>6) New technological developments. | Yes    | Yes    | Yes    | Yes    | ID.IM-04         |

---

## PROTECT (PR)
PROTECT (PR): Safeguards to manage the organization's technology and cybersecurity risks are used

---

### PROTECT / Identity Management, Authentication, and Access Control (PR.AA)
Identity Management, Authentication, and Access Control (PR.AA): Access to physical and logical assets is limited to authorized users, services, and hardware and managed commensurate with the assessed risk of unauthorized access

#### PROTECT / Identity Management, Authentication, and Access Control / Identity & Credential Management (PR.AA-01)
PR.AA-01: Identities and credentials for authorized users, services, and hardware are managed by the organization

| Category ID  | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AA-01.01  | PR.AA-01.01: Identities and credentials are actively managed or automated for authorized devices and users (e.g., removal of default and factory passwords, password strength requirements, automatic revocation of credentials under defined conditions, regular asset owner access review, etc.). | Yes    | Yes    | Yes    | Yes    | PR.AA-01         |
| PR.AA-01.02  | PR.AA-01.02: Physical and logical access to systems is permitted only for individuals who have a legitimate business requirement, have been authorized, and who are adequately trained and monitored. | Yes    | Yes    | Yes    | Yes    | PR.AA-01         |

#### PROTECT / Identity Management, Authentication, and Access Control / Identity Binding to Credentials (PR.AA-02)
PR.AA-02: Identities are proofed and bound to credentials based on the context of interactions

| Category ID  | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AA-02.01  | PR.AA-02.01: The organization authenticates identity, validates the authorization level of a user before granting access to its systems, limits the use of an account to a single individual, and attributes activities to the user in logs and transactions.                | Yes    | Yes    | Yes    | Yes    | PR.AA-02         |

#### PROTECT / Identity Management, Authentication, and Access Control / Authentication (PR.AA-03)
PR.AA-03: Users, services, and hardware are authenticated

| Category ID  | Outcome| Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AA-03.01  | PR.AA-03.01: Based on the risk level of a user access or a specific transaction, the organization defines and implements authentication requirements, which may include multi-factor or out-of-band authentication, and may adopt other real-time risk prevention or mitigation tactics.|           | Yes    | Yes    | Yes    | Yes    | PR.AA-03         |
| PR.AA-03.02  | PR.AA-03.02: Decisions to authorize user access to devices and other assets are made with consideration of: (1) Business need for the access; (2) The type of data being accessed (e.g., customer PII, public data); (3) The risk of the transaction (e.g., internal-to-internal, external-to-internal); (4) The organization's level of trust for the accessing agent (e.g., external application, internal user); and (5) The potential for harm. | Yes    | Yes    | Yes    | Yes    | PR.AA-03         |
| PR.AA-03.03  | PR.AA-03.03: The organization reduces fraudulent activity and protects reputational integrity through email verification mechanisms (e.g., DMARC, DKIM), call-back verification, secure file exchange facilities, out-of-band communications, customer outreach and education, and other tactics designed to thwart imposters and fraudsters.           | Yes    | Yes    | Yes    | Yes    | PR.AA-03         |

#### PROTECT / Identity Management, Authentication, and Access Control / Identity Assertions (PR.AA-04)
PR.AA-04: Identity assertions are protected, conveyed, and verified

| Category ID  | Outcome| Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AA-04.01  | PR.AA-04.01: Access credential and authorization mechanisms for internal systems and across security perimeters (e.g., leveraging directory services, directory synchronization, single sign-on, federated access, credential mapping, etc.) are designed to maintain security, integrity, and authenticity.                          | Yes    | Yes    | Yes    | Yes    | PR.AA-04         |

#### PROTECT / Identity Management, Authentication, and Access Control / Access Authorizations (PR.AA-05)
PR.AA-05: Access permissions, entitlements, and authorizations are defined in a policy, managed, enforced, and reviewed, and incorporate the principles of least privilege and separation of duties

| Category ID  | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AA-05.01  | PR.AA-05.01: The organization limits access privileges to the minimum necessary and with consideration of separation of duties (e.g., through role-based access control, asset owner access recertifications, etc.).                         | Yes    | Yes    | Yes    | Yes    | PR.AA-05         |
| PR.AA-05.02  | PR.AA-05.02: The organization institutes controls over privileged system access by strictly limiting and closely managing staff and services with elevated system entitlements (e.g., multi-factor authentication, dual accounts, privilege and time constraints, etc.)|                   | Yes    | Yes    | Yes    | Yes    | PR.AA-05         |
| PR.AA-05.03  | PR.AA-05.03: The organization institutes controls over service account (i.e., accounts used by systems to access other systems) lifecycles to ensure strict security over creation, use, and termination; access credentials (e.g., no embedded passwords in code); frequent reviews of account ownership; visibility for unauthorized use; and hardening against malicious insider use. | Yes    | Yes    | Yes    | Yes    | PR.AA-05         |
| PR.AA-05.04  | PR.AA-05.04: Specific roles, responsibilities, and procedures to manage the risk of third-party access to organizational systems and facilities are defined and implemented. | Yes    | Yes    | Yes    | Yes    | PR.AA-05         |

#### PROTECT / Identity Management, Authentication, and Access Control / Physical Access (PR.AA-06)
PR.AA-06: Physical access to assets is managed, monitored, and enforced commensurate with risk

| Category ID  | Outcome                       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AA-06.01  | PR.AA-06.01: The organization manages, protects, and logs physical access to sensitive areas, devices, consoles, equipment, and network cabling and infrastructure.                           | Yes    | Yes    | Yes    | Yes    | PR.AA-06         |
| PR.AA-06.02  | PR.AA-06.02: The organization manages and protects physical and visual access to sensitive information assets and physical records (e.g., session lockout, clean desk policies, printer/facsimile output trays, file cabinet/room security, document labelling, etc.)                   | Yes    | Yes    | Yes    | Yes    | PR.AA-06         |

---

### PROTECT / Awareness and Training (PR.AT)
Awareness and Training (PR.AT): The organization’s personnel are provided with cybersecurity awareness and training so that they can perform their cybersecurity-related tasks

#### PROTECT / Awareness and Training / User Awareness & Training (PR.AT-01)
PR.AT-01: Personnel are provided with awareness and training so that they possess the knowledge and skills to perform general tasks with cybersecurity risks in mind

| Category ID    | Outcome                             | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AT-01.01    | PR.AT-01.01: All personnel receive cybersecurity awareness training upon hire and on a regular basis.                      | Yes    | Yes    | Yes    | Yes    | PR.AT-01         |
| PR.AT-01.02    | PR.AT-01.02: Cybersecurity awareness training includes, at a minimum, awareness of and competencies for data protection, personal data handling, compliance obligations, working with third parties, detecting cyber risks, and how to report any unusual activity or incidents.|| Yes    | Yes    | Yes    | Yes    | PR.AT-01         |
| PR.AT-01.03    | PR.AT-01.03: Cybersecurity awareness training is updated on a regular basis to reflect risks and threats identified by the organization, the organization's security policies and standards, applicable laws and regulations, and changes in individual responsibilities.|       | Yes    | Yes    | Yes    | Yes    | PR.AT-01         |
| PR.AT-01.04    | PR.AT-01.04: As new technology is deployed or undergoes change that also requires changes in practices, all impacted personnel (e.g., end-users, developers, operators, etc.) are trained on the new system and any accompanying technology and cybersecurity risks.|             | Yes    | Yes    | Yes    | Yes    | PR.AT-01         |

#### PROTECT / Awareness and Training / Specialized Role Awareness & Training (PR.AT-02)
PR.AT-02: Individuals in specialized roles are provided with awareness and training so that they possess the knowledge and skills to perform relevant tasks with cybersecurity risks in mind

| Category ID    | Outcome      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.AT-02.01    | PR.AT-02.01: Mechanisms are in place to ensure that the personnel working with cybersecurity and technology (e.g., developers, DBAs, network admins, etc.) maintain current knowledge and skills related to changing threats, countermeasures, new tools, best practices, and their job responsibilities.     | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |
| PR.AT-02.02    | PR.AT-02.02: High-risk groups, such as those with elevated privileges or in sensitive business functions (including privileged users, senior executives, cybersecurity personnel and third-party stakeholders), receive cybersecurity situational awareness training for their roles and responsibilities.  | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |
| PR.AT-02.03    | PR.AT-02.03: All personnel (employee and third party) are made aware of and are trained for their role and operational steps in response and recovery plans.             | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |
| PR.AT-02.04    | PR.AT-02.04: The organization maintains and enhances the skills and knowledge of the in-house staff performing incident management and forensic investigation activities. | Yes    | Yes    | Yes    | No     | PR.AT-02         |
| PR.AT-02.05    | PR.AT-02.05: All third party staff receive cybersecurity awareness and job training sufficient for them to perform their duties and maintain organizational security.      | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |
| PR.AT-02.06    | PR.AT-02.06: The organization has established and maintains a cybersecurity awareness program through which the organization's customers are kept aware of new threats and vulnerabilities, basic cybersecurity hygiene practices, and their role in cybersecurity, as appropriate.   | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |
| PR.AT-02.07    | PR.AT-02.07: The organization's governing body (e.g., the Board or one of its committees) and senior management receive cybersecurity situational awareness training to include appropriate skills and knowledge to: (1) Evaluate and manage cyber risks; (2) Promote a culture that recognizes that staff at all levels have important responsibilities in ensuring the organization's cyber resilience; and (3) Lead by example. | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |
| PR.AT-02.08    | PR.AT-02.08: Where the organization's governing authority (e.g., the Board or one of its committees) does not have adequate cybersecurity expertise, they should have direct access to the senior officer responsible for cybersecurity and independent sources of expertise to discuss cybersecurity related matters.|             | Yes    | Yes    | Yes    | Yes    | PR.AT-02         |

---

### PROTECT / Data Security (PR.DS)
Data Security (PR.DS): Data are managed consistent with the organization's risk strategy to protect the confidentiality, integrity, and availability of information

#### PROTECT / Data Security / Protection of Data at Rest (PR.DS-01)
PR.DS-01: The confidentiality, integrity, and availability of data-at-rest are protected

| Category ID    | Outcome|   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.DS-01.01    | PR.DS-01.01: Data-at-rest is protected commensurate with the criticality and sensitivity of the information and in alignment with the data classification and protection policy (e.g., through the use of encryption, authentication, access control, segregation, masking, tokenization, and file integrity monitoring).   | Yes    | Yes    | Yes    | Yes    | PR.DS-01         |
| PR.DS-01.02    | PR.DS-01.02: The organization implements data loss identification and prevention tools to monitor and protect against confidential data theft or destruction by an employee or an external actor.|           | Yes    | Yes    | Yes    | No     | PR.DS-01         |
| PR.DS-01.03    | PR.DS-01.03: The organization defines and implements controls for the protection and use of removable media (e.g., access/use restrictions, encryption, malware scanning, data loss prevention, etc.)|          | Yes    | Yes    | Yes    | Yes    | PR.DS-01         |

#### PROTECT / Data Security / Protection of Data in Transit (PR.DS-02)
PR.DS-02: The confidentiality, integrity, and availability of data-in-transit are protected

| Category ID    | Outcome|                 | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.DS-02.01    | PR.DS-02.01: Data-in-transit is protected commensurate with the criticality and sensitivity of the information and in alignment with the data classification and protection policy (e.g., through the use of encryption, authentication, access control, masking, tokenization, and alternate transit paths).|         | Yes    | Yes    | Yes    | Yes    | PR.DS-02         |

#### PROTECT / Data Security / Protection of Data in Use (PR.DS-10)
PR.DS-10: The confidentiality, integrity, and availability of data-in-use are protected

| Category ID    | Outcome|      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.DS-10.01    | PR.DS-10.01: Data-in-use is protected commensurate with the criticality and sensitivity of the information and in alignment with the data classification and protection policy (e.g., through the use of encryption, authentication, access control, masking, tokenization, visual shielding, memory integrity monitoring, etc.)                             | Yes    | Yes    | Yes    | Yes    | PR.DS-10         |

#### PROTECT / Data Security / Data Backup (PR.DS-11)
PR.DS-11: Backups of data are created, protected, maintained, and tested

| Category ID    | Outcome           | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.DS-11.01    | PR.DS-11.01: The organization defines and implements standards and procedures for configuring and performing backups and data replications, including defining backup requirements by data/application/infrastructure criticality, segregating (e.g., air-gapping) and securing backups, verifying backup integrity, and performing backup restoration testing. | Yes    | Yes    | Yes    | Yes    | PR.DS-11         |

---

### PROTECT / Platform Security (PR.PS)
Platform Security (PR.PS): The hardware, software (e.g., firmware, operating systems, applications), and services of physical and virtual platforms are managed consistent with the organization’s risk strategy to protect their confidentiality, integrity, and availability

#### PROTECT / Platform Security / Configuration Management (PR.PS-01)
PR.PS-01: Configuration management practices are established and applied

| Category ID    | Outcome|                      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-01.01    | PR.PS-01.01: The organization establishes and maintains standard system security configuration baselines, informed by industry standards and hardening guidelines, to facilitate the consistent application of security settings, configurations, and versions.                 | Yes    | Yes    | Yes    | No     | PR.PS-01         |
| PR.PS-01.02    | PR.PS-01.02: The organization's systems are configured to provide only essential capabilities to implement the principle of least functionality.                      | Yes    | Yes    | Yes    | Yes    | PR.PS-01         |
| PR.PS-01.03    | PR.PS-01.03: The organization employs detection measures and performs regular enforcement checks to ensure that non-compliance with baseline security standards is promptly identified and rectified.           | Yes    | Yes    | Yes    | No     | PR.PS-01         |
| PR.PS-01.04    | PR.PS-01.04: The organization documents its requirements for accurate and resilient time services (e.g., synchronization to a mandated or appropriate authoritative time source) and adopts best practice guidance in implementing and using these services for logging, event correlation, forensic analysis, authentication, transactional processing, and other purposes.| Yes    | Yes    | Yes    | Yes    | PR.PS-01         |
| PR.PS-01.05    | PR.PS-01.05: Acceptable encryption standards, methods, and management practices are established in accordance with defined industry standards.                       | Yes    | Yes    | Yes    | Yes    | PR.PS-01         |
| PR.PS-01.06    | PR.PS-01.06: The organization employs defined encryption methods and management practices commensurate with the criticality of the information being protected and the inherent risk of the technical environment where used.                | Yes    | Yes    | Yes    | Yes    | PR.PS-01         |
| PR.PS-01.07    | PR.PS-01.07: Cryptographic keys and certificates are tracked, managed, and protected throughout their lifecycles, to include for compromise and revocation.        | Yes    | Yes    | Yes    | Yes    | PR.PS-01         |
| PR.PS-01.08    | PR.PS-01.08: End-user mobile or personal computing devices accessing the organization's network employ mechanisms to protect network, application, and data integrity, such as "Mobile Device Management (MDM)" and "Mobile Application Management (MAM)" technologies, device fingerprinting, storage containerization and encryption, integrity scanning, automated patch application, remote wipe, and data leakage protections. | Yes    | Yes    | Yes    | Yes    | PR.PS-01         |
| PR.PS-01.09    | PR.PS-01.09: Endpoint systems implemented using virtualization technologies employ mechanisms to protect network, application, and data integrity, such as restricting access to local network and peripheral devices, multi-factor authentication, locking-down device source network locations, and data leakage protections.| | Yes    | Yes    | Yes    | Yes    | PR.PS-01         |

#### PROTECT / Platform Security / Software Maintenance & Replacement (PR.PS-02)
PR.PS-02: Software is maintained, replaced, and removed commensurate with risk

| Category ID    | Outcome           | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-02.01    | PR.PS-02.01: The organization defines and implements controls to identify patches to technology assets, assess patch criticality and risk, test patches, and apply patches within risk/criticality-based target time frames.                    | Yes    | Yes    | Yes    | Yes    | PR.PS-02         |
| PR.PS-02.02    | PR.PS-02.02: The organization establishes standards and practices for ongoing application management to ensure that applications remain secure and continue to meet organizational needs.                       | Yes    | Yes    | Yes    | No     | PR.PS-02         |
| PR.PS-02.03    | PR.PS-02.03: Technology obsolescence, unsupported systems, and end-of-life decommissioning/replacements are addressed in a risk-based manner and actively planned for, funded, managed, and securely executed.  | Yes    | Yes    | Yes    | No     | PR.PS-02         |

#### PROTECT / Platform Security / Hardware Maintenance (PR.PS-03)
PR.PS-03: Hardware is maintained, replaced, and removed commensurate with risk

| Category ID    | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-03.01    | PR.PS-03.01: The organization defines and implements controls for the on-site and remote maintenance and repair of the organization's technology assets (e.g., work must be performed by authorized personnel, use of approved procedures and tools, use of original or vendor-approved spare parts). | Yes    | Yes    | Yes    | No     | PR.PS-03         |

#### PROTECT / Platform Security / Log Record Generation (PR.PS-04)
PR.PS-04: Log records are generated and made available for continuous monitoring

| Category ID    | Outcome          | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-04.01    | PR.PS-04.01: The organization establishes and regularly reviews log management standards and practices, to include the types of events to be detected, log content, security and access considerations, monitoring protocols, integrity checking mechanisms, and retention periods.|             | Yes    | Yes    | Yes    | Yes    | PR.PS-04         |
| PR.PS-04.02    | PR.PS-04.02: The organization defines the scope and coverage of audit/log records to be created and monitored (i.e., internal and external environments, devices, and applications/services/software to be monitored) and has controls in place to ensure that the intended scope is fully covered and that no logging failures are inhibiting the collection of required logs. | Yes    | Yes    | Yes    | Yes    | PR.PS-04         |
| PR.PS-04.03    | PR.PS-04.03: The organization's activity logs and other security event logs are generated, reviewed, securely stored, and retained in accordance with data retention obligations and established standards.   | Yes    | Yes    | Yes    | Yes    | PR.PS-04         |

#### PROTECT / Platform Security / Unauthorized Software Installation & Execution (PR.PS-05)
PR.PS-05: Installation and execution of unauthorized software are prevented

| Category ID    | Outcome|                   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-05.01    | PR.PS-05.01: The organization has policies, procedures, and tools in place to detect and block malware from infecting networks and systems, including automatically updating malware signatures and behavior profiles on all endpoints.     | Yes    | Yes    | Yes    | Yes    | PR.PS-05         |
| PR.PS-05.02    | PR.PS-05.02: The organization implements safeguards against unauthorized mobile code (e.g., JavaScript, ActiveX, VBScript, PowerShell, etc.) on mobile, end point, and server systems.|    | Yes    | Yes    | Yes    | Yes    | PR.PS-05         |
| PR.PS-05.03    | PR.PS-05.03: The organization has policies, procedures, and tools in place to detect, isolate, and block the use of attached malware or malicious links present in email or message services.                | Yes    | Yes    | Yes    | Yes    | PR.PS-05         |

#### PROTECT / Platform Security / Secure Systems Development Practices (PR.PS-06)
PR.PS-06: Secure software development practices are integrated, and their performance is monitored throughout the software development life cycle

| Category ID    | Outcome|        | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-06.01    | PR.PS-06.01: The organization implements Secure Systems Development Lifecycle processes for in-house software design, configuration, and development, employing best practices from secure-by-design methodologies (e.g., secure coding, code review, application security testing, etc.) during all phases of both traditional and agile projects.         | Yes    | Yes    | Yes    | No     | PR.PS-06         |
| PR.PS-06.02    | PR.PS-06.02: The architecture, design, coding, testing, and operationalization of system solutions address the unique security, resilience, technical, and operational characteristics of the target platform environment(s) (e.g., distributed system, mainframe, cloud, API, mobile, database, etc.)|   | Yes    | Yes    | Yes    | No     | PR.PS-06         |
| PR.PS-06.03    | PR.PS-06.03: Functional, operational, resilience, and security requirements for system development and implementation projects are documented, agreed to by relevant stakeholders, and tracked and managed through development, testing, assurance, acceptance, and delivery.        | Yes    | Yes    | Yes    | No     | PR.PS-06         |
| PR.PS-06.04    | PR.PS-06.04: Systems development and testing tools, processes, and environments employ security mechanisms to protect and improve the integrity and confidentiality of both the SDLC process and the resulting product (e.g., secured code repositories, segmented environments, automated builds, etc.)|    | Yes    | Yes    | Yes    | No     | PR.PS-06         |
| PR.PS-06.05    | PR.PS-06.05: A software security testing and validation strategy is developed and implemented in the development lifecycle of all software projects, defining testing requirements and plans; performing/automating testing, vulnerability scanning, and migration activities; and supporting code integrity verification (e.g., using digital signatures).   | Yes    | Yes    | Yes    | No     | PR.PS-06         |
| PR.PS-06.06    | PR.PS-06.06: The system development lifecycle remediates known critical vulnerabilities, and critical vulnerabilities discovered during testing, prior to production deployment.|| Yes    | Yes    | Yes    | No     | PR.PS-06         |
| PR.PS-06.07    | PR.PS-06.07: DevOps/DevSecOps practices and procedures are aligned with Systems Development Lifecycle, security operations, and technology service management processes.|       | Yes    | Yes    | No     | No     | PR.PS-06         |
| PR.PS-06.08    | PR.PS-06.08: The design, configuration, security control, and operation of key applications and system services are documented sufficiently to support ongoing management, operation, change, and assessment.                  | Yes    | Yes    | No     | No     | PR.PS-06         |
| PR.PS-06.09    | PR.PS-06.09: End-user developed solutions, to include models used to support critical business processes and decisions, are formally identified and managed in alignment with their criticality and risk.                     | Yes    | Yes    | No     | No     | PR.PS-06         |
| PR.PS-06.10    | PR.PS-06.10: The organization establishes policies and procedures for the secure design, configuration, modification, and operation of databases, data stores, and data analytics platforms consistent with the criticality of the data being managed.           | Yes    | Yes    | Yes    | No     | PR.PS-06         |

#### PROTECT / Platform Security / Technology Operations, Service, & Support (PR.PS-07)
PR.PS-07: The organization's technology operations and service and support functions are designed and managed to address business operational needs and stakeholder requirements.

| Category ID    | Outcome|               | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.PS-07.01    | PR.PS-07.01: The organization's technology operations, process verification, error detection, issue management, root cause analysis, and problem management functions are formally documented, monitored, and KPIs are regularly reported to stakeholders.                   | Yes    | Yes    | No     | No     | None             |
| PR.PS-07.02    | PR.PS-07.02: Technology service and support functions address stakeholder expectations (e.g., through stated requirements, SLAs, or OLAs) and performance is monitored and regularly reported to stakeholders.                             | Yes    | Yes    | No     | No     | None             |

---

### PROTECT / Technology Infrastructure Resilience (PR.IR)
Technology Infrastructure Resilience (PR.IR): Tehcnology and security architectures are managed with the organization's risk strategy to protect asset confidentiality, integrity, and availability, and organizational resilience

#### PROTECT / Technology Infrastructure Resilience / Logical Access Protections (PR.IR-01)
PR.IR-01: Networks and environments are protected from unauthorized logical access and usage

| Category ID    | Outcome|                | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.IR-01.01    | PR.IR-01.01: Networks, systems, and external connections are segmented (e.g., using firewalls, software-defined networks, guest wireless networks, etc.) to implement defense-in-depth and access isolation principles.                | Yes    | Yes    | Yes    | Yes    | PR.IR-01         |
| PR.IR-01.02    | PR.IR-01.02: Network device configurations (e.g., firewall rules, ports, and protocols) are documented, reviewed and updated regularly and upon change to ensure alignment with network access, segmentation, traversal, and deny-all default requirements.              | Yes    | Yes    | Yes    | Yes    | PR.IR-01         |
| PR.IR-01.03    | PR.IR-01.03: The integrity and resilience of the organization's communications and control network services are enhanced through controls such as denial of service protections, secure name/address resolution, and/or alternate communications paths.                    | Yes    | Yes    | Yes    | No     | PR.IR-01         |
| PR.IR-01.04    | PR.IR-01.04: The organization controls access to its wireless networks and the information that these networks process by implementing appropriate mechanisms (e.g., strong authentication for authentication and transmission, preventing unauthorized devices from connecting to the internal networks, restricting unauthorized traffic, and segregating guest wireless networks).                       | Yes    | Yes    | Yes    | Yes    | PR.IR-01         |
| PR.IR-01.05    | PR.IR-01.05: Remote access is carefully controlled (e.g., restricted to defined systems, access is actively managed (e.g., session timeouts, logging, forced disconnect, etc.), and encrypted connections with multi-factor authentication are used).   | Yes    | Yes    | Yes    | Yes    | PR.IR-01         |
| PR.IR-01.06    | PR.IR-01.06: The organization's production and non-production environments and data are segregated and managed to prevent unauthorized access or changes to the information assets.|     | Yes    | Yes    | Yes    | No     | PR.IR-01         |
| PR.IR-01.07    | PR.IR-01.07: The organization defines and implements controls for securely configuring and operating Operational Technologies, Industrial Control Systems, and Internet-of-Things (IoT) devices (e.g., segregated printer networks, resetting of default passwords, etc.)| Yes    | Yes    | Yes    | No     | PR.IR-01         |
| PR.IR-01.08    | PR.IR-01.08: The organization implements policies, procedures, end-user agreements, and technical controls to address the risks of end-user mobile or personal computing devices accessing the organization's network and resources. | Yes    | Yes    | Yes    | Yes    | PR.IR-01         |

#### PROTECT / Technology Infrastructure Resilience / Environmental Threat Protections (PR.IR-02)
PR.IR-02: The organization’s technology assets are protected from environmental threats

| Category ID    | Outcome      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.IR-02.01    | PR.IR-02.01: The organization designs, documents, implements, tests, and maintains environmental and physical controls to meet defined business resilience requirements (e.g., environmental monitoring, dual power and communication sources, regionally separated backup processing facilities, etc.) | Yes    | Yes    | Yes    | Yes    | PR.IR-02         |

#### PROTECT / Technology Infrastructure Resilience / Resilience Measures (PR.IR-03)
PR.IR-03: Mechanisms are implemented to achieve resilience requirements in normal and adverse situations

| Category ID    | Outcome                  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.IR-03.01    | PR.IR-03.01:  The organization implements mechanisms (e.g., failsafe, load balancing, hot swaps, redundant equipment, alternate services, backup facilities, etc.) to achieve resilience requirements in normal and adverse situations.                             | Yes    | Yes    | Yes    | No     | PR.IR-03         |

#### PROTECT / Technology Infrastructure Resilience / Capacity Management (PR.IR-04)
PR.IR-04: Adequate resource capacity to ensure availability is maintained

| Category ID    | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| PR.IR-04.01    | PR.IR-04.01: Baseline measures of network and system utilization and transaction activity are captured to support capacity planning and anomalous activity detection. | Yes    | Yes    | No     | No     | PR.IR-04         |
| PR.IR-04.02    | PR.IR-04.02: Technology availability and capacity is planned, monitored, managed, and optimized to meet business resilience objectives and reasonably anticipated infrastructure demands.  | Yes    | Yes    | Yes    | No     | PR.IR-04         |

---

# DETECT (DE)
DETECT (DE): Possible cybersecurity attacks and compromises, and other operationally adverse events, are found and analyzed

---

## DETECT / Continuous Monitoring (DE.CM)
Continuous Monitoring (DE.CM): Assets are monitored to find anomalies, indicators of compromise, and other potentially adverse events

### DETECT / Continuous Monitoring / Network Monitoring (DE.CM-01)
DE.CM-01: Networks and network services are monitored to find potentially adverse events

| Category ID  | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.CM-01.01  | DE.CM-01.01:  The organization deploys intrusion detection and intrusion prevention capabilities to detect and prevent a potential network intrusion in its early stages for timely containment and recovery.                       | Yes    | Yes    | Yes    | Yes    | DE.CM-01         |
| DE.CM-01.02  | DE.CM-01.02: The organization implements mechanisms, such as alerting and filtering of sudden high volumes and suspicious incoming traffic, to detect and mitigate Denial of Service, "bot", and credential stuffing attacks.         | Yes    | Yes    | Yes    | No     | DE.CM-01         |
| DE.CM-01.03  | DE.CM-01.03: The organization has policies, procedures, and tools in place to monitor for, detect, and block unauthorized network connections and data transfers.  | Yes    | Yes    | Yes    | No     | DE.CM-01         |
| DE.CM-01.04  | DE.CM-01.04: The organization has policies, procedures, and tools in place to monitor for, detect, and block access from/to devices that are not authorized or do not conform to security policy (e.g., unpatched systems).          | Yes    | Yes    | Yes    | Yes    | DE.CM-01         |
| DE.CM-01.05  | DE.CM-01.05: The organization implements measures to detect and block access to unauthorized, inappropriate, or malicious websites and services (e.g. social media, messaging, file sharing).         | Yes    | Yes    | Yes    | Yes    | DE.CM-01         |
| DE.CM-01.06  | DE.CM-01.06: The organization employs deception techniques and technologies (e.g., honeypots) to detect and prevent a potential intrusion in its early stages to support timely containment and recovery.                            | Yes    | No     | No     | No     | DE.CM-01         |

### DETECT / Continuous Monitoring / Physical Environment Monitoring (DE.CM-02)
DE.CM-02: The physical environment is monitored to find potentially adverse events

| Category ID  | Outcome                  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.CM-02.01  | DE.CM-02.01: The organization's controls include monitoring and detection of anomalous activities and potential intrusion events across the organization's physical environment and infrastructure, including the detection of environmental threats (fire, water, service outages, etc.) and unauthorized physical access to high-risk system components and locations. | Yes    | Yes    | Yes    | Yes    | DE.CM-02         |

### DETECT / Continuous Monitoring / Personnel Activity Monitoring (DE.CM-03)
DE.CM-03: Personnel activity and technology usage are monitored to find potentially adverse events

| Category ID  | Outcome                                                                                                                    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.CM-03.01  | DE.CM-03.01: Account access, authentication, and authorization activities are logged and monitored, for both users and devices, to enforce authorized access.                                | Yes    | Yes    | Yes    | Yes    | DE.CM-03         |
| DE.CM-03.02  | DE.CM-03.02: The organization's controls actively monitor personnel (both authorized and unauthorized) for access, authentication, usage, connections, devices, and anomalous behavior to rapidly detect potential cybersecurity events.                         | Yes    | Yes    | Yes    | Yes    | DE.CM-03         |
| DE.CM-03.03  | DE.CM-03.03: The organization logs and reviews the activities of privileged users and accounts, and monitoring for anomalous behaviors is implemented.    | Yes    | Yes    | Yes    | No     | DE.CM-03         |

### DETECT / Continuous Monitoring / Service Provider Monitoring (DE.CM-06)
DE.CM-06: External service provider activities and services are monitored to find potentially adverse events

| Category ID  | Outcome                                                                                    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.CM-06.01  | DE.CM-06.01: The organization reviews, documents, authorizes, and monitors all third-party connections, data transfer mechanisms, and Application Programming Interfaces (APIs).                 | Yes    | Yes    | Yes    | Yes    | DE.CM-06         |
| DE.CM-06.02  | DE.CM-06.02: The organization implements an explicit approval and logging process and sets up automated alerts to monitor and prevent any unauthorized access to a critical system by a third-party service provider.            | Yes    | Yes    | Yes    | No     | DE.CM-06         |

### DETECT / Continuous Monitoring / Hardware, Software, & Data Monitoring (DE.CM-09)
DE.CM-09: Computing hardware and software, runtime environments, and their data are monitored to find potentially adverse events

| Category ID  | Outcome                                                                                                                | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.CM-09.01  | DE.CM-09.01: The organization uses integrity checking mechanisms to verify software, firmware and information integrity and provenance (e.g., checksums, Software Bill of Materials, etc.)| Yes    | Yes    | No     | No     | DE.CM-09         |
| DE.CM-09.02  | DE.CM-09.02: The organization uses integrity checking mechanisms to verify hardware integrity.                           | Yes    | Yes    | No     | No     | DE.CM-09         |
| DE.CM-09.03  | DE.CM-09.03: The organization has policies, procedures, and tools in place to monitor for, detect, and block the use of unsupported or unauthorized software, hardware, or configuration changes.                        | Yes    | Yes    | Yes    | Yes    | DE.CM-09         |

---

## DETECT / Adverse Event Analysis (DE.AE)
Adverse Event Analysis (DE.AE): Anomalies, indicators of compromise, and other potentially adverse events are analyzed to characterize the events and detect cybersecurity incidents

### DETECT / Adverse Event Analysis / Potentially Adverse Event Analysis (DE.AE-02)
DE.AE-02: Potentially adverse events are analyzed to better understand associated activities

| Category ID  | Outcome          | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.AE-02.01  | DE.AE-02.01: The organization performs timely collection of event data, as well as advanced and automated analysis (including the use of security tools such as antivirus and IDS/IPS) on the detected events to: (1) Assess and understand the nature, scope and method of the attack; (2) Predict and block a similar future attack; and (3) Report timely risk metrics.                           | Yes    | Yes    | Yes    | Yes    | DE.AE-02         |
| DE.AE-02.02  | DE.AE-02.02: The organization establishes, documents, and regularly reviews event alert parameters and thresholds, as well as rule-based triggers to support automated responses, when known attack patterns, signatures or behaviors are detected.                                         | Yes    | Yes    | Yes    | Yes    | DE.AE-02         |

### DETECT / Adverse Event Analysis / Event Information Correlation (DE.AE-03)
DE.AE-03: Information is correlated from multiple sources

| Category ID  | Outcome        | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.AE-03.01  | DE.AE-03.01: The organization implements systematic and real-time logging, collection, monitoring, detection, and alerting measures across multiple layers of the organization's infrastructure, including physical perimeters, network, operating systems, applications, data, and external (cloud and outsourced) environments, sufficient to protect the organization's information assets. | Yes    | Yes    | Yes    | Yes    | DE.AE-03         |
| DE.AE-03.02  | DE.AE-03.02: The organization performs real-time central analysis, aggregation, and correlation of anomalous activities, network and system alerts, and relevant event and cyber threat intelligence, including both internal and external (cloud and outsourced) environments, to better detect and prevent multifaceted cyber attacks.  | Yes    | Yes    | Yes    | Yes    | DE.AE-03         |

### DETECT / Adverse Event Analysis / Impact & Scope Determination (DE.AE-04)
DE.AE-04: The estimated impact and scope of adverse events are understood

| Category ID  | Outcome                                                                                                       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.AE-04.01  | DE.AE-04.01: The organization has a documented process to analyze and triage incidents to assess root cause, technical impact, mitigation priority, and business impact on the organization, as well as across the financial sector and other third party stakeholders. | Yes    | Yes    | Yes    | Yes    | DE.AE-04         |

### DETECT / Adverse Event Analysis / Event Information Sharing (DE.AE-06)
DE.AE-06: Information on adverse events is provided to authorized staff and tools

| Category ID  | Outcome                                                                                                              | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.AE-06.01  | DE.AE-06.01: The organization has established processes and protocols to communicate, alert, and regularly report potential cyber attacks and incident information, including its corresponding analysis and cyber threat intelligence, to authorized internal and external stakeholders. | Yes    | Yes    | Yes    | Yes    | DE.AE-06         |

### DETECT / Adverse Event Analysis / Contextual Analysis (DE.AE-07)
DE.AE-07: Cyber threat intelligence and other contextual information are integrated into the analysis

| Category ID  | Outcome                                                                                               | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.AE-07.01  | DE.AE-07.01: The organization implements measures for monitoring external sources (e.g., social media, the dark web, etc.) to integrate with other intelligence information to better detect and evaluate potential threats and compromises. | Yes    | Yes    | No     | No     | DE.AE-07         |
| DE.AE-07.02  | DE.AE-07.02: Relevant event data is packaged for subsequent review and triage and events are categorized for efficient handling, assignment, and escalation.              | Yes    | Yes    | Yes    | No     | DE.AE-07         |

### DETECT / Adverse Event Analysis / Incident Declaration (DE.AE-08)
DE.AE-08: Incidents are declared when adverse events meet the defined incident criteria

| Category ID  | Outcome                                                                                                         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| DE.AE-08.01  | DE.AE-08.01: Defined criteria and severity levels are in place to facilitate the declaration, escalation, organization, and alignment of response activities to response plans within the organization and across relevant third parties. | Yes    | Yes    | Yes    | No     | DE.AE-08         |

---

## RESPOND (RS)
RESPOND (RS): Actions regarding a detected adverse incidents are taken

### RESPOND / Incident Management (RS.MA)
Incident Management (RS.MA): Responses to detected adverse incidents are managed

#### RESPOND / Incident Management / Response Plan Execution (RS.MA-01)
RS.MA-01: The incident response plan is executed in coordination with relevant third parties once an incident is declared

| Category ID   | Outcome                                                                                                                  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MA-01.01   | RS.MA-01.01: The organization's response plans are in place and executed during or after an incident, to include coordination with relevant third parties and engagement of third-party incident support services.       | Yes    | Yes    | Yes    | Yes    | RS.MA-01          |

#### RESPOND / Incident Management / Incident Triage & Validation (RS.MA-02)
RS.MA-02: Incident reports are triaged and validated

| Category ID   | Outcome                         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MA-02.01   | RS.MA-02.01: Tools and processes are in place to ensure timely detection, inspection, assessment, and analysis of security event data for reliable activation of incident response processes.                                 | Yes    | Yes    | Yes    | Yes    | RS.MA-02          |

#### RESPOND / Incident Management / Incident Categorization & Prioritization (RS.MA-03)
RS.MA-03: Incidents are categorized and prioritized

| Category ID   | Outcome| Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MA-03.01   | RS.MA-03.01: The organization categorizes and prioritizes cybersecurity incident response consistent with response plans and criticality of systems and services to the enterprise.             | Yes    | Yes    | Yes    | Yes    | RS.MA-03          |

#### RESPOND / Incident Management / Incident Escalation (RS.MA-04)
RS.MA-04: Incidents are escalated or elevated as needed

| Category ID   | Outcome                            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MA-04.01   | RS.MA-04.01: Response activities are centrally coordinated, response progress and milestones are tracked and documented, and new incident information is assimilated into ongoing tasks, assignments, and escalations.          | Yes    | Yes    | Yes    | No     | RS.MA-04          |

#### RESPOND / Incident Management / Recovery Initiation (RS.MA-05)
RS.MA-05: The criteria for initiating incident recovery are applied

| Category ID   | Outcome                            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MA-05.01   | RS.MA-05.01: The organization's incident response plans define severity levels and associated criteria for initiating response plans and escalating event response to appropriate stakeholders and management levels.            | Yes    | Yes    | Yes    | Yes    | RS.MA-05          |

### RESPOND / Incident Analysis (RS.AN)
Incident Analysis (RS.AN): Investigations are conducted to ensure effective response and support forensics and recovery activities

#### RESPOND / Incident Analysis / Incident Analysis & Root Cause Determination (RS.AN-03)
RS.AN-03: Analysis is performed to establish what has taken place during an incident and the root cause of the incident

| Category ID   | Outcome                                                                                                              | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.AN-03.01   | RS.AN-03.01: The organization performs a thorough investigation to determine the nature and scope of an event, possible root causes, and the potential damage inflicted.              | Yes    | Yes    | Yes    | Yes    | RS.AN-03          |

#### RESPOND / Incident Analysis / Investigation Documentation (RS.AN-06)
RS.AN-06: Actions performed during an investigation are recorded, and the records� integrity and provenance are preserved

| Category ID   | Outcome                         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.AN-06.01   | RS.AN-06.01: The organization establishes a risk-based approach and procedures for quarantining systems, conducting investigations, and collecting and preserving evidence per best practices and forensic standards.       | Yes    | Yes    | Yes    | No     | RS.AN-06          |

#### RESPOND / Incident Analysis / Incident Data Collection & Preservation (RS.AN-07)
RS.AN-07: Incident data and metadata are collected, and their integrity and provenance are preserved

| Category ID   | Outcome                                                                                                            | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.AN-07.01   | RS.AN-07.01: Incident-related forensic data is captured, secured, and preserved in a manner supporting integrity, provenance, and evidentiary value.                                | Yes    | Yes    | Yes    | No     | RS.AN-07          |

#### RESPOND / Incident Analysis / Incident Magnitude Determination (RS.AN-08)
RS.AN-08: An incident's magnitude is estimated and validated

| Category ID   | Outcome      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.AN-08.01   | RS.AN-08.01: Available incident information is assessed to determine the extent of impact to the organization and its stakeholders, the potential near- and long-term financial implications, and whether or not the incident constitutes a material event.            | Yes    | Yes    | Yes    | Yes    | RS.AN-08          |

### RESPOND / Incident Response Reporting and Communication (RS.CO)
Incident Response Reporting and Communication (RS.CO): Response activities are coordinated with internal and external stakeholders as required by laws, regulations, or policies

#### RESPOND / Incident Response Reporting and Communication / Stakeholder Incident Notification (RS.CO-02)
RS.CO-02: Internal and external stakeholders are notified of incidents

| Category ID    | Outcome              | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.CO-02.01    | RS.CO-02.01: The organization's incident response program includes defined and approved escalation protocols, linked to organizational decision levels and communication strategies, including which types of information will be shared, with whom (e.g., the organization's governing authority and senior management), and how information provided to the organization will be acted upon. | Yes    | Yes    | Yes    | Yes    | RS.CO-02         |
| RS.CO-02.02    | RS.CO-02.02: In the event of an incident, the organization notifies impacted stakeholders including, as required, government bodies, self-regulatory agencies and/or other supervisory bodies, within required timeframes.    | Yes    | Yes    | Yes    | Yes    | RS.CO-02         |
| RS.CO-02.03    | RS.CO-02.03: The organization maintains and regularly tests incident response communication procedures, with associated contact lists, call trees, and automatic notifications, to quickly coordinate and communicate with internal and external stakeholders during or following an incident.   | Yes    | Yes    | Yes    | Yes    | RS.CO-02         |

#### RESPOND / Incident Response Reporting and Communication / Stakeholder Incident Information Sharing (RS.CO-03)
RS.CO-03: Information is shared with designated internal and external stakeholders

| Category ID    | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.CO-03.01    | RS.CO-03.01: The organization ensures that cyber threat intelligence is made available, in a secure manner, to authorized staff with responsibility for the mitigation of cyber risks at the strategic, tactical and operational levels within the organization.           | Yes    | Yes    | Yes    | No     | RS.CO-03         |
| RS.CO-03.02    | RS.CO-03.02: In the event of an incident, the organization shares authorized information, in a defined manner and through trusted channels, to facilitate the detection, response, resumption and recovery of its own systems and those of other partners and critical sector participants. | Yes    | Yes    | Yes    | Yes    | RS.CO-03         |

### RESPOND / Incident Mitigation (RS.MI)
Incident Mitigation (RS.MI): Activities are performed to prevent expansion of an event and mitigate its effects

#### RESPOND / Incident Mitigation / Incident Containment (RS.MI-01)
RS.MI-01: Incidents are contained

| Category ID    | Outcome         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MI-01.01    | RS.MI-01.01: The organization has established processes to implement vulnerability mitigation plans, involve third-party partners and outside expertise as needed, and contain incidents in a timely manner.   | Yes    | Yes    | Yes    | Yes    | RS.MI-01         |

#### RESPOND / Incident Mitigation / Incident Eradication (RS.MI-02)
RS.MI-02: Incidents are eradicated

| Category ID    | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| RS.MI-02.01    | RS.MI-02.01: Targeted investigations and actions are taken to ensure that all vulnerabilities, system components, devices, or remnants used or leveraged in an attack (e.g., malware, compromised accounts, open ports, etc.) are removed or otherwise returned to a secure and reliable state, or that plans to address the vulnerabilities are documented. | Yes    | Yes    | Yes    | Yes    | RS.MI-02         |

---

## RECOVER (RC)
RECOVER (RC): Assets and operations affected by an adverse incident are restored

### RECOVER / Incident Recovery Plan Execution (RC.RP)
Incident Recovery Plan Execution (RC.RP): Restoration activities are performed to ensure operational availability of systems and services affected by adverse incidents

#### RECOVER / Incident Recovery Plan Execution / Recovery Plan Execution (RC.RP-01)
RC.RP-01: The recovery portion of the incident response plan is executed once initiated from the incident response process

| Category ID  | Outcome                                                                                                                      | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.RP-01.01  | RC.RP-01.01: The organization executes its recovery plans, including incident recovery, disaster recovery, and business continuity plans, during or after an incident to resume operations.    | Yes    | Yes    | Yes    | Yes    | RC.RP-01         |

#### RECOVER / Incident Recovery Plan Execution / Recovery Action Performance (RC.RP-02)
RC.RP-02: Recovery actions are selected, scoped, prioritized, and performed

| Category ID  | Outcome           | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.RP-02.01  | RC.RP-02.01: The organization's response plans are used as informed guidance to develop and manage task plans, response actions, priorities, and assignments for responding to incidents, but are adapted as necessary to address incident-specific characteristics.               | Yes    | Yes    | Yes    | Yes    | RC.RP-02         |
| RC.RP-02.02  | RC.RP-02.02: Recovery plans are executed by first resuming critical services and core business functions, while minimizing any potential concurrent and widespread interruptions to interconnected entities and critical infrastructure, such as energy and telecommunications. | Yes    | Yes    | Yes    | Yes    | RC.RP-02         |

#### RECOVER / Incident Recovery Plan Execution / Backup & Restoration Asset Integrity (RC.RP-03)
RC.RP-03: The integrity of backups and other restoration assets is verified before using them for restoration

| Category ID  | Outcome                                                                                         | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.RP-03.01  | RC.RP-03.01: Restoration steps include the verification of backups, data replications, system images, and other restoration assets prior to continued use.       | Yes    | Yes    | Yes    | Yes    | RC.RP-03         |

#### RECOVER / Incident Recovery Plan Execution / Post-Incident Operational Norms (RC.RP-04)
RC.RP-04: Critical mission functions and cybersecurity risk management are considered to establish post-incident operational norms

| Category ID  | Outcome                                                                                                                        | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.RP-04.01  | RC.RP-04.01: Restoration steps include the verification of data integrity, transaction positions, system functionality, and the operation of security controls by appropriate organizational stakeholders and system owners.    | Yes    | Yes    | Yes    | Yes    | RC.RP-04         |

#### RECOVER / Incident Recovery Plan Execution / Asset Integrity Restoration (RC.RP-05)
RC.RP-05: The integrity of restored assets is verified, systems and services are restored, and normal operating status is confirmed

| Category ID  | Outcome                                                                                                                  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.RP-05.01  | RC.RP-05.01: The organization maintains documented procedures for sanitizing, testing, authorizing, and returning systems to service following an incident or investigation.              | Yes    | Yes    | No     | No     | RC.RP-05         |
| RC.RP-05.02  | RC.RP-05.02: Business, technology, cybersecurity, and relevant third-party stakeholders confirm that systems, data, and services have been returned to functional and secure states and that a stable operational status has been achieved. | Yes    | Yes    | Yes    | Yes    | RC.RP-05         |

#### RECOVER / Incident Recovery Plan Execution / End-of-Incident Determination (RC.RP-06)
RC.RP-06: The end of incident recovery is declared based on criteria, and incident-related documentation is completed

| Category ID  | Outcome              | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.RP-06.01  | RC.RP-06.01: Incident management activities are closed under defined conditions and documentation to support subsequent post-mortem review, process improvement, and any follow-on activities is collected and verified.                         | Yes    | Yes    | Yes    | Yes    | RC.RP-06         |

### RECOVER / Incident Recovery Communication (RC.CO)
Incident Recovery Communication (RC.CO): Restoration activities are coordinated with internal and external parties

#### RECOVER / Incident Recovery Communication / Recovery Activity Communication (RC.CO-03)
RC.CO-03: Recovery activities and progress in restoring operational capabilities are communicated to designated internal and external stakeholders

| Category ID  | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.CO-03.01  | RC.CO-03.01: The organization timely involves and communicates the recovery activities, procedures, cyber risk management issues to the governing body (e.g., the Board or one of its committees), senior management, incident management support teams, and relevant internal stakeholders. | Yes    | Yes    | Yes    | Yes    | RC.CO-03         |
| RC.CO-03.02  | RC.CO-03.02: The organization promptly communicates the status of recovery activities to regulatory authorities and relevant external stakeholders, as required or appropriate.                             | Yes    | Yes    | Yes    | Yes    | RC.CO-03         |

#### RECOVER / Incident Recovery Communication / Public Information Sharing (RC.CO-04)
RC.CO-04: Public updates on incident recovery are shared using approved methods and messaging

| Category ID  | Outcome    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|--------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|------------------|
| RC.CO-04.01  | RC.CO-04.01: Pre-established communication plans and message templates, and authorized protocols, contacts, media, and communications, are used to notify and inform the public and key external stakeholders about an incident.       | Yes    | Yes    | Yes    | Yes    | RC.CO-04         |

---

# EXTEND (EX)
EXTEND (EX): Extend organizational risk management policy and practices over the life cycle of third- (and nth-) party relationships, products, and services

---

## EXTEND / Procurement Planning and Due Diligence (EX.DD)
Procurement Planning and Due Diligence (EX.DD): Planning and due diligence are performed to reduce risks before entering into a formal third-party relationship

### EXTEND / Procurement Planning and Due Diligence / Procurement Planning (EX.DD-01)
EX.DD-01: Planning is performed for procurements and agreements that involve elevated risk to the organization

| Category ID   | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.DD-01.01   | EX.DD-01.01: Documented procurement plans are developed for initiatives involving elevated business, technical, or cybersecurity risk in order to establish criteria for the evaluation and selection of a supplier, and any special requirements for organizational preparation, supplier due diligence, and contract terms. | Yes    | Yes    | Yes    | No     | GV.SC-06         |
| EX.DD-01.02   | EX.DD-01.02: Procurement plans address the inherent risks of the planned activity, to include the complexity of the endeavor in terms of technology, scope, and novelty, and demonstrate that the potential business and financial benefits outweigh the costs to control the anticipated risks.  | Yes    | Yes    | No     | No     | GV.SC-06         |
| EX.DD-01.03   | EX.DD-01.03: Procurement plans address expected resource requirements and procedures for ongoing management and monitoring of the selected supplier, contingency plans for supplier non-performance, and specific considerations related to contract termination (e.g., return of data).            | Yes    | Yes    | No     | No     | GV.SC-06         |

### EXTEND / Procurement Planning and Due Diligence / Prospective Third Party Due Diligence (EX.DD-02)
EX.DD-02: The organization performs thorough due diligence on prospective third parties, consistent with procurement planning and commensurate with the level of risk, criticality, and complexity of each third-party relationship

| Category ID   | Outcome   | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.DD-02.01   | EX.DD-02.01: The organization implements procedures, and allocates sufficient resources with the requisite knowledge and experience, to conduct third party due diligence and risk assessment consistent with the procurement plan and commensurate with level of risk, criticality, and complexity of each third-party relationship. | Yes    | Yes    | Yes    | Yes    | GV.SC-06         |
| EX.DD-02.02   | EX.DD-02.02: The organization reviews and evaluates the proposed business arrangement, to include the proposed fee structures, incentives, and penalties, proposed staff resources, viability of proposed approaches, and business terms, to ensure that products or services are being obtained at competitive and reasonable costs and terms.      | Yes    | Yes    | Yes    | Yes    | GV.SC-06         |
| EX.DD-02.03   | EX.DD-02.03: The organization reviews and evaluates documentation, such as financial statements, independent audit reports, pooled/shared assessments, control test reports, SEC filings, and past and pending litigation, to the extent required to determine a prospective critical third party's soundness as a business and the quality and sustainability of its internal controls. | Yes    | Yes    | Yes    | Yes    | GV.SC-06         |
| EX.DD-02.04   | EX.DD-02.04: The organization reviews and assesses the prospective third party's controls for managing its suppliers and subcontractors (fourth and nth parties), any proposed role fourth and nth parties will play in delivering the products or services, and any specific fourth- and nth-party controls or alternative arrangements the organization may require to protect its interests. | Yes    | Yes    | Yes    | Yes    | GV.SC-06         |

### EXTEND / Procurement Planning and Due Diligence / Technology & Cybersecurity Risk Assessment (EX.DD-03)
EX.DD-03: The organization assesses the risks and suitability of the technology and cybersecurity capabilities and risk management practices of prospective third parties

| Category ID   | Outcome     | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.DD-03.01   | EX.DD-03.01: The organization reviews, evaluates, and risk assesses a prospective critical third party's cybersecurity program, including its ability to identify, assess, monitor, and mitigate its cyber risks; the completeness of its policies and procedures; the strength of its technical and administrative controls; and the coverage of its internal and independent control testing programs. | Yes    | Yes    | Yes    | Yes    | ID.RA-10         |
| EX.DD-03.02   | EX.DD-03.02: The organization reviews, evaluates, and risk assesses a prospective critical third party's business continuity program, to include business impact analyses, risk assessments, continuity plans, disaster recovery plans, technology resilience architecture, and response and recovery plans, test plans, and test results.  | Yes    | Yes    | Yes    | Yes    | ID.RA-10         |
| EX.DD-03.03   | EX.DD-03.03: The organization reviews, evaluates, and risk assesses a prospective critical third party's incident response program, to include monitoring and alerting capabilities, incident reporting procedures and protocols, and capabilities for event analysis, problem resolution, and forensic investigation.                | Yes    | Yes    | Yes    | Yes    | ID.RA-10         |

### EXTEND / Procurement Planning and Due Diligence / Product & Service Due Diligence (EX.DD-04)
EX.DD-04: Third-party products and services are assessed relative to business, risk management, and cybersecurity requirements

| Category ID   | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.DD-04.01   | EX.DD-04.01: The organization defines and implements procedures for assessing the compatibility, security, integrity, and authenticity of externally-developed or externally-sourced applications, software, software components, and firmware before deployment and upon any major change.                   | Yes    | Yes    | No     | No     | ID.RA-09         |
| EX.DD-04.02   | EX.DD-04.02: The organization reviews and evaluates any technologies or information systems proposed to support a third party's services or activities, to include compatibility with the organization's technology and cybersecurity architectures, interactions and interfaces with existing systems, security controls, operational management and support requirements, and suitability to the task. | Yes    | Yes    | Yes    | Yes    | ID.RA-09         |

---

## EXTEND / Third-Party Contracts and Agreements (EX.CN)
Third-Party Contracts and Agreements (EX.CN): Contracts establish baseline protections to manage risk over the life of the third-party relationship

### EXTEND / Third-Party Contracts and Agreements / Contract General Requirements (EX.CN-01)
EX.CN-01: Contracts clearly specify the rights and responsibilities of each party and establish requirements to address the anticipated risks posed by a third party over the life of the relationship

| Category ID   | Outcome    | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.CN-01.01   | EX.CN-01.01: Contracts with suppliers clearly detail the general terms, nature, and scope of the arrangement, to include the distribution of responsibilities between the parties; costs, compensation, reimbursements, incentives, and penalties; service level agreements, performance measures, and benchmarks; responsibilities for providing, receiving, and retaining information; recourse provisions; and the organization's rights to review, monitor, and audit the supplier's activities. | Yes    | Yes    | Yes    | Yes    | GV.SC-05         |
| EX.CN-01.02   | EX.CN-01.02: Contracts with suppliers address, as relevant to the product or service, the supplier's requirements for managing its own suppliers and partners (fourth parties) and the risks those fourth parties may pose to the third party and to the organization, to include fourth party due diligence, limitations on activities or geography, monitoring, notifications, liability and indemnifications, etc.   | Yes    | Yes    | Yes    | Yes    | GV.SC-05         |
| EX.CN-01.03   | EX.CN-01.03: Contracts with suppliers address, as relevant to the product or service, the implications of foreign-based third or fourth parties, to include the relevance of local laws and regulations, access to facilities and data, limitations on cross-border data transfer, and language and time zone management.                                 | Yes    | Yes    | Yes    | Yes    | GV.SC-05         |

### EXTEND / Third-Party Contracts and Agreements / Contract Cybersecurity-Related Requirements (EX.CN-02)
EX.CN-02: Expected cybersecurity practices for critical third parties that meet the risk management objectives of the organization are identified, documented, and agreed

| Category ID   | Outcome       | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.CN-02.01   | EX.CN-02.01: The organization's contracts require third-parties to implement minimum technology and cybersecurity management requirements, to maintain those practices for the life of the relationship, and to provide evidence of compliance on an ongoing basis.                           | Yes    | Yes    | Yes    | Yes    | GV.SC-05         |
| EX.CN-02.02   | EX.CN-02.02: Minimum cybersecurity requirements for third-parties include requirements for incident and vulnerability notification, to include the types of events requiring notification, notification timeframes, and escalation protocols.| Yes    | Yes    | Yes    | Yes    | GV.SC-05         |
| EX.CN-02.03   | EX.CN-02.03: Contracts with suppliers address, as relevant to the product or service, the supplier's obligation to maintain and regularly test a business continuity program and disaster recovery capability the meets the defined resilience requirements of the organization.                            | Yes    | Yes    | Yes    | Yes    | GV.SC-05         |
| EX.CN-02.04   | EX.CN-02.04: Contracts with suppliers address, as relevant to the product or service, the supplier's obligation to regularly participate in joint and/or bilateral recovery exercises and tests, and to address significant issues identified through recovery testing.     | Yes    | Yes    | Yes    | Yes    | GV.SC-05         |

---

## EXTEND / Monitoring and Managing Suppliers (EX.MM)
Monitoring and Managing Suppliers (EX.MM): The risks posed by a third-party are monitored and managed over the course of the relationship

### EXTEND / Monitoring and Managing Suppliers / Ongoing Third-Party Monitoring (EX.MM-01)
EX.MM-01: Critical suppliers and third parties are monitored to confirm that they continue to satisfy their obligations as required; reviews of audits, test results, or other assessments of third parties are conducted

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.MM-01.01   | EX.MM-01.01: The organization implements procedures, and allocates sufficient resources with the requisite knowledge and experience, to manage and monitor its third-party relationships to a degree and extent commensurate with the risk each third party poses to the organization and the criticality of the third party's products, services, and/or relationship to the organization. | Yes    | Yes    | Yes    | Yes    | GV.SC-07         |
| EX.MM-01.02   | EX.MM-01.02: The organization regularly evaluates its third party relationships to determine if changes in the organization's circumstances, objectives, or third party use warrant a change in a third party's risk rating (e.g., a less critical third-party relationship evolves into being a critical relationship). | Yes    | Yes    | No     | No     | GV.SC-07         |
| EX.MM-01.03   | EX.MM-01.03: The organization monitors for and regularly evaluates changes in a critical third party's business posture that could pose adverse risk to the organization (e.g., financial condition, reputation, adverse news, compliance/regulatory issues, key personnel, business relationships, consumer complaints, etc.)             | Yes    | Yes    | Yes    | Yes    | GV.SC-07         |
| EX.MM-01.04   | EX.MM-01.04: The organization regularly assesses critical third party adherence to service level agreements, product specifications, performance metrics, resource level/skill commitments, and quality expectations; addresses performance issues; and exercises contract penalties or credits as warranted. | Yes    | Yes    | Yes    | Yes    | GV.SC-07         |
| EX.MM-01.05   | EX.MM-01.05: The organization regularly assesses a critical third party's program and ability to manage its own suppliers and partners (fourth and nth parties) and the risks those fourth and nth parties may pose to the third party and to the organization (e.g., cybersecurity supply chain risk, concentration risk, reputation risk, foreign-party risk, etc.)                           | Yes    | Yes    | Yes    | No     | GV.SC-07         |
| EX.MM-01.06   | EX.MM-01.06: The organization regularly reviews the foreign-based operations and activities of a critical third party, or its critical fourth parties, to confirm contract controls are maintained and compliance requirements are managed.                               | Yes    | Yes    | Yes    | Yes    | GV.SC-07         |

### EXTEND / Monitoring and Managing Suppliers / Ongoing Third-Party Management (EX.MM-02)
EX.MM-02: Inter-dependent and coordinated cybersecurity risk management practices with third parties are managed to ensure ongoing effectiveness

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.MM-02.01   | EX.MM-02.01: The organization conducts regular third-party reviews for critical vendors to validate that requisite security and contractual controls are in place and continue to be operating as expected.                             | Yes    | Yes    | Yes    | Yes    | GV.SC-07         |
| EX.MM-02.02   | EX.MM-02.02: A process is in place to confirm that the organization's critical third-party service providers maintain their business continuity programs, conduct regular resiliency testing, and participate in joint and/or bilateral recovery exercises and tests.        | Yes    | Yes    | Yes    | No     | GV.SC-07         |
| EX.MM-02.03   | EX.MM-02.03: The organization collaborates with suppliers to maintain and improve the secure use of products, services, and external connections.                                   | Yes    | Yes    | Yes    | Yes    | GV.SC-07         |

---

## EXTEND / Relationship Termination (EX.TR)
Relationship Termination (EX.TR): Relationship termination is anticipated, planned for, and executed safely

### EXTEND / Relationship Termination / Termination Planning (EX.TR-01)
EX.TR-01: The organization anticipates and plans for the termination of critical relationships under both normal and adverse circumstances

| Category ID   | Outcome  | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.TR-01.01   | EX.TR-01.01: The organization establishes contingencies to address circumstances that might put a vendor out of business or severely impact delivery of services to the organization, sector-critical systems, or the financial sector as a whole. | Yes    | Yes    | No     | No     | GV.SC-10         |
| EX.TR-01.02   | EX.TR-01.02: The organization periodically identifies and tests alternative solutions in case a critical external partner fails to perform as expected.                      | Yes    | Yes    | No     | No     | GV.SC-10         |
| EX.TR-01.03   | EX.TR-01.03: The organization has a documented third-party termination/exit plan, to include procedures for timely removal of the third-party access, return of data and property, personnel disposition, and transition of services and support. | Yes    | Yes    | No     | No     | GV.SC-10         |

### EXTEND / Relationship Termination / Termination Practices (EX.TR-02)
EX.TR-02: Relationship terminations and the return or destruction of assets are performed in a controlled and safe manner

| Category ID   | Outcome | Tier 1 | Tier 2 | Tier 3 | Tier 4 | NIST CSF Mapping |
|---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|--------|--------|--------|-------------------|
| EX.TR-02.01   | EX.TR-02.01: Upon termination of a third-party agreement, the organization ensures that all technical and security matters (access, connections, etc.), business matters (service, support, and ongoing relationship), property matters (data, physical, and intellectual), and legal matters are addressed in a timely manner. | Yes    | Yes    | Yes    | Yes    | GV.SC-10         |
---

**End of Document**
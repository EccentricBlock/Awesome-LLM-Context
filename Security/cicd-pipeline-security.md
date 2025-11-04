# CI/CD Pipeline Security

# Secure Pipeline Design

## High-Level Overview

The following stages outline a high-level secure CI/CD pipeline:


 1. **Code Commit (GitHub):** Developers commit code changes to GitHub repositories.
 2. **Pull Request (PR) + Code Review + Static Analysis:** Code review enforced by mandatory approvals and static code analysis to identify vulnerabilities early.
 3. **Automated Security & Vulnerability Scanning (SAST):** Identify and fix potential security vulnerabilities within the codebases.
 4. **Dependency and Software Composition Analysis (SCA):** Scan for known vulnerabilities in third-party libraries and dependencies.
 5. **Secure Artifact and Container Image Build:** Generate secure, immutable artifacts using containerised ephemeral build environments.
 6. **Container Security Scanning and Integrity Verification:**  Verify container image security against vulnerabilities, misconfigurations, and policy violations.
 7. **Cryptographic Signing of Artifacts:** Digitally sign artifacts and containers to ensure authenticity and integrity.
 8. **Automated Testing & Dynamic Security Analysis (DAST):** Dynamic security scanning for vulnerabilities in deployed staging applications.
 9. **Deployment to Staging (Manual Approval Gate):** Requires manual approval prior to staging deployment to enforce security oversight.
10. **Security/Compliance Approval (Manual & Automated Gates):** Security validation, automated compliance checks, and final human review prior to production.
11. **Deployment to Production (Immutable & Audit-Logged):**  Secure and immutable deployment, fully audit-logged and traceable for accountability.


## Design

The following design prioritizes "shift-left" security by integrating security checks as early in the development lifecycle as possible to reduce risk & cost of remediation. Leveraging automation is also key for scalability and consistency.

### Principles

### Repository Hardening & Governance

* **Branching Strategy:** Implement a robust branching strategy like GitHub Flow. Feature branches should be short-lived and require peer review before merging into development/main branches. This prevents long-running, vulnerable code from being introduced.
* **Protected Branches:** The `main` branch (or equivalent production branch) must be protected. Require pull request reviews, status checks, and potentially designated approvers.
* **Code Owners:** Define Code Owners for specific parts of the codebase to ensure relevant expertise is involved in code review.
* **GitHub Actions/Secrets Management:** Leverage GitHub Secrets securely store sensitive credentials (API keys, database passwords, etc.). Avoid hardcoding these anywhere in the repository. Regularly rotate secrets.

### Build Environment Isolation

* **Ephemeral Build Agents:** Use containerised or VM-based runners that are destroyed after each job to eliminate persistent attack surfaces and secrets leakage.
* **Least Privilege Service Accounts:** Assign scoped GitHub Actions tokens with only the necessary permissions (e.g. read-only for code, write-only for artefacts).

#### Monitoring, Logging & Alerting

* **Audit Logging:** Centralise logs for all pipeline actions (PR merges, build failures, deployments) in a secure SIEM.
* **Anomaly Detection:** Configure alerts for unusual patterns (e.g. deployment outside business hours, new IP addresses triggering builds).

### Commit, Build & Deployment

#### Static Application Security Testing (SAST)

* **Integration:** Integrate SAST tools directly into pull requests and as part of CI builds. Tools like SonarQube, Semgrep, or CodeQL scan code for vulnerabilities (SQL injection, cross-site scripting, etc.).
* **Terraform/CloudFormation Scanning**: If using IaC tools, integrate linters and security scanners (Checkov, tfsec) to detect misconfigurations in infrastructure code before deployment. (e.g., publicly accessible S3 buckets, insecure network settings).
* **Fail the Build:** Configure the pipeline to fail if SAST detects high/critical severity issues. This prevents vulnerable code from being merged.
* **Custom Rules:** Develop custom SAST rules tailored to crypto-specific vulnerabilities (e.g., weaknesses in wallet integration, insecure randomness generation).

#### Dependency and Software Composition Analysis (SCA)

* **Integration**: Utilize tools like Semgrep, Snyk or Dependabot to automatically scan for known vulnerabilities in project dependencies (libraries and frameworks).
* **Automated PRs:** Automatically create pull requests to update vulnerable dependencies to patched versions whenever possible. Updates should be prioritised based on severity.
* **SBOM Generation:** Generate a Software Bill of Materials (SBOM) as part of the build process for better visibility into third-party components and potential supply chain risks.

#### Secure Artifact and Container Image Build

* **Immutable Artefacts:** Publish build outputs (Docker images, binaries) to an immutable registry (e.g. Amazon ECR with immutability enabled).
* **Digital Signing:** Sign container images and packages (e.g. using Notary or Sigstore) so downstream systems accept only verified artefacts.

#### Container Security Scanning and Integrity Verification

* **Image Scanning**: Scan container images during build using tools like Trivy or Clair. This will identify vulnerabilities in base images and application layers.
* **Registry Scanning:** Continuously scan images stored in the container registry for new vulnerabilities even after they are built.
* **Minimal Base Images:** Utilize minimal base images (e.g. Google distroless) to reduce attack surface.

#### Automated Testing & Dynamic Security Analysis (DAST)

* **Integration**: Integrate DAST tools like OWASP ZAP or Burp Suite into the pipeline after the application is built and deployed to a staging environment.
* **Automated Scans:** Perform automated scans against the running application, simulating real-world attacks.
* **Fail the Deployment:** If critical vulnerabilities are identified by DAST, fail the deployment to production.

#### Deployment & Approval Workflow

* **Manual Approval Gates:** Require explicit sign-off in GitHub Actions or an external approval tool (e.g. Jira ticket link) before deploying to production.
* **Role-Based Access Control (RBAC):** Limit "deploy" permissions to a small set of users or service accounts.

## CI/CD Tool Security

### Tool Hardening

* **Version Management:** Regularly upgrade to the latest software release (e.g. ArgoCD) and subscribe to security advisories.
* **Feature Restriction:** Disable unused features where possible to shrink the attack surface.
* **Authentication & Authorization:** Enforce SSO (OIDC/SAML) for all CD users, local local accounts should be disabled and RBAC policies applied for fine-grained ACLs.
* **Centralised Logging:** ##aasdf##

### Hosting CD/Build Server Hardening

* **Network Policies:** Restrict access to the CD's API and web server via firewall rules / secuirty groups.
* **OS Local Account Hygiene:** Remove or disable default accounts; ensure each user has a unique account with an audit trail.
* **OS Hardening:** Apply CIS or equivalent hardening guides to disable unnecessary services, close unused ports and enforce secure configurations.
* **Automated Patch Deployment:** Schedule routine OS and kernel updates via a centralised tool (e.g. Ansible, AWS Systems Manager) with pre-deployment testing.
* **Centralised Log Aggregation:** Forward syslog, auditd and application logs to a SIEM (e.g. Splunk, ELK) for correlation and alerting.
* **Integrity Monitoring:** Implement Tripwire or AIDE for scheduled checksum verification of critical system files.
* **Host IDS/IPS:** Deploy tools like OSSEC, Wazuh or CrowdStrike to detect anomalous file changes, rootkit installs or suspicious processes.

## Key Security Controls & Vulnerability Prevention Measures

### Secure Development and Commit Stage

* **Secure Development Training:** Regular secure coding training for all developers.
* **Protected Branches:** Enforce branch protection rules on GitHub (mandatory reviews, no direct pushes to main branches).
* **Mandatory PR Reviews:** Require code reviews from designated security-trained senior engineers.

### Authentication & Authorization Controls

* **Role-Based Access Control (RBAC):** Strict GitHub permissions to limit write-access and enforce least privilege.
* **Multi-factor Authentication (MFA):** Required for all repository users and contributors.

### Automated Security Analysis

* **Static Application Security Testing (SAST):** SAST should be Integrated into CI pipeline to identify vulnerabilities early. 
* **Automated DAST:** Regularly run dynamic security tests against deployed staging environments. 
* **Dependency & SCA:** Automated vulnerability scanning for software dependencies.

### Secure Build Environment

* **Ephemeral Build Containers:** CI runners use short-lived, ephemeral environments to prevent persistence attacks.
* **Immutable Artifacts:** Generated artifacts and container images are immutable, with cryptographic hashes verified at deployment.
* **Hardened Hosting Systems:** Systems running CD or build agents should be appropriately hardened to industry standards such as CIS benchmarks.

### Monitoring and Alerting

* **Pipeline Monitoring:** Continuous monitoring of pipeline execution for anomalies or suspicious behaviours. 
* **Incident Response Integration:** Rapid rollback capability; integration with security incident response processes.

### Integrity and Provenance

* **Cryptographic Signing:** Leverage digital signatures for commits, builds, and artifacts. 
* **Provenance Tracking:** Track and validate artifact provenance using frameworks like SLSA (Supply-chain Levels for Software Artifacts).

## Preventing Unauthorised Code Deployment

* **Separation of Duties:** No single identity can both merge to main and approve the production deployment.
* **GitHub Access Control:** Strict branch protection rules combined with MFA ensure only authorized users can merge code.
* **Code Review:** Mandatory peer review adds another layer of scrutiny where automated tooling may miss risks.
* **Multi-Factor Approval Workflow:** By combining branch protection with manual gates, no code can reach production without the correct sequence of automated checks and human sign-off.
* **Immutable Infrastructure:** Deployments occur via declarative manifests stored in Git. Changes to infrastructure also require the same PR and approval process, preventing "out-of-band" modifications.
* **Cryptographically signed commits and builds:** This will prevent attackers from injecting malicious code or artifacts unnoticed.
* **Signed Artifacts:** This ensures no tampering post-build and before deployment.

# Secure Deployment Workflow Implementation

Crypto platforms are exceptionally high-value targets. A rapid deployment cadence is crucial for innovation and market responsiveness in this space, however this cannot come at the expense of security. 

## Velocity vs Security

The stages below outline a structured approch to building out a CI/CD pipeline from scratch. The approach taken is risk-based prioritisation. The above pipeline design section focuses more on providing a comprehensive outline, this structured approach adopts a "we need sufficient" security approach, given the limited resources of a startup.

The following principles should be applied:

* **Automate Everything Possible:** Reduce manual effort through automation wherever feasible.
* **Focus on Impact & Likelihood:** Prioritize vulnerabilities based on their potential impact and likelihood of exploitation.
* **Continuous Improvement:** Regularly review and update security controls as the company grows and threats evolve.
* **Clear Communication**: Foster open communication between development, security, and operations teams to ensure that everyone understands the risks and responsibilities.

## Implementation Stages

### **Stage 1: Commit / Code Review**

The objective is to Integrate security directly into the development process, shifting left as much as possible. This will provide the first line of defense.

* **Controls:**
  * **Secure Code Repository:** Multi-factor authentication (MFA) enforced for all developers; granular permissions based on least privilege with mandatory PR reviews. Audit logs monitored for suspicious activity.
  * **Static Application Security Testing (SAST):** Automated code analysis tools integrated into the pull request process. Tools like SonarQube, Semgrep or CodeQL can identify common vulnerabilities (SQL injection, cross-site scripting, etc.). The focus should be on critical and high severity findings, where the objective is to not introduce any new High/Critical's into the environment*.* The builds should be configured to fail based on the severity thresholds.
  * **Dependency Scanning:** Automated tools (like Dependabot or Snyk) check for vulnerable dependencies during commit. Automatic PRs generated to upgrade vulnerable libraries. Critical & High vulnerabilities require immediate attention.
  * **Secret Management Integration:** Prevent secrets (API keys, passwords) from being committed to the repository. Use tools like HashiCorp Vault, AWS Secrets Manager, or GitHub Secrets integrated with the CI/CD system and development workflows.
  * **Code Owners**: Implement code owners for critical areas of the codebase that require review by a specialist before merging.
* **Reasoning:** This is the cheapest and most effective way to prevent vulnerabilities from entering the pipeline. Automating these checks provides immediate feedback to developers, reducing remediation costs later on.

### Stage 2: Build Stage 

Once the first stage objectives have been met, the next step is to verify that build artifacts haven't been tampered with, and apply basic security hardening; ensuring integrity.

* **Controls:**
  * **Immutable Infrastructure:** Use containerization for both reproducible builds and build agents. This ensures consistent deployments across environments.
  * **Build Artifact Signing**: Digitally sign build artifacts to verify their integrity. Any modification will invalidate the signature, alerting you to potential tampering. (Use tools like Sigstore).
  * **Base Image Scanning:** Scan base images for vulnerabilities before building container images. Use vulnerability scanners integrated into the CI/CD pipeline (like Trivy or Clair.)
  * **Software Bill of Materials (SBOM)**: Generate SBOMs as part of the build process to track dependencies, making it easier to assess risk and respond to supply chain attacks.
* **Reasoning:** Immutable infrastructure reduces configuration drift and simplifies rollback procedures. Artifact signing protects against malicious modifications during the build process.

### **Stage 3: Testing Stage**

Upon implementation of the first two stages, the next step is rigorous testing.  However, to keep development velocity high, there needs to be a focus on automation.

* **Controls:**
  * **Dynamic Application Security Testing (DAST):** Automated vulnerability scans of running applications in a test environment. Tools like OWASP ZAP or Burp Suite can identify vulnerabilities that SAST might miss. Again, the focus should be on high-impact flaws. 
  * **Integration Tests with Security Scenarios:** Include integration tests specifically designed to validate security controls (e.g., authorization checks, input validation).
  * **Fuzz Testing**: Automated testing technique injecting invalid/random data into the application to discover crashes and vulnerabilities. This is particularly relevant for a trading platform that processes large amounts of real-time data.
  * **API Security Testing:** Specific tests focusing on API endpoints, authentication, authorization, rate limiting etc.
* **Reasoning:** DAST validates security in a runtime environment, providing a more realistic assessment of vulnerabilities. Integration tests ensure that security controls are functioning correctly within the application's overall architecture.


### **Stage 4: Pre-Production (Staging) – Controlled Release & Human Review**

This stage is where targeted human review is introduced and final checks are executed before releasing to production.

* **Controls:**
  * **Automated Infrastructure as Code (IaC) Scanning**: Scan IaC templates (Terraform, CloudFormation) for misconfigurations using tools like Checkov or Terrascan. Prevent deployments with insecure configurations.
  * **Penetration Testing (Periodic):** Conduct regular penetration tests of the staging environment by qualified security professionals. *Frequency based on risk profile and release cadence*.
  * **Deployment Approval Workflow:** Where possible a Tired approval workflow system should be used:
    * **Tier 1 (Minor Changes - Automated):** Automated deployment after passing all automated checks. Limited scope changes only (e.g., bug fixes, configuration updates).
    * **Tier 2 (Significant Changes – Security Review Required):** Requires explicit approval from a designated security engineer andthe development lead. This is triggered by:
      * Changes to critical code components (trading engine, wallet management).
      * Introduction of new dependencies.
      * Infrastructure changes that affect security controls.
      * Findings from SAST/DAST that require mitigation.
    * **Tier 3 (Critical Changes – CISO Approval):** Reserved for major releases, significant architectural changes, or responses to critical vulnerabilities. Requires CISO approval *and* a sign-off from the development and infrastructure teams.
* **Reasoning:** Human review is essential for complex changes and risk assessments that automated tools can't handle effectively. The tiered approval system balances security requirements with deployment velocity by focusing human effort on high-risk deployments.

### **Stage 5: Production – Monitoring & Incident Response**

One the first four stages have been completes, the next focus should be on continuous monitoring, logging, and incident response capabilities; these are paramount in a live trading/crypto environment.

* **Controls:**
  * **Real-time Security Monitoring (SIEM):** Implement a SIEM solution to collect security logs from all systems and detect suspicious activity.
  * **Intrusion Detection/Prevention System (IDS/IPS)**: Monitor network traffic for malicious patterns.
  * **Automated Incident Response:** Develop playbooks for responding to common security incidents. Automate as much of the response process as possible (e.g., isolating compromised systems, blocking malicious IP addresses).
  * **Regular Security Audits**: Periodic audits of production systems and processes to identify vulnerabilities and improve security posture.

# Secret Management Strategy

## Foundational Principles

The following foundational principles should act as a base upon which to build a sucessful strategy:

* **Least Privilege:** Each service/application should only have access to the secrets it absolutely *needs*.
* **Rotation:** Secrets should be rotated on a regular basis (ideally automated) to minimize the impact of potential compromise.
* **Centralized Management:** A single source of truth for all secrets, reducing sprawl and improving auditability (AWS Secrets Manager). Leveraging tools such as AWS Secrets manager can provide some rotation functionality.
* **Automation:** Wherever possible, secret management should be automated through infrastructure-as-code and CI/CD processes.
* **Encrypt-Everywhere:** Secrets should be encrypted with KMS/HSM where possible and use TLS (v1.3) during communication
* **Auditing & Monitoring:** Comprehnsive logging and alerting around secret access and update attempts.


## GitHub Secrets Management

### Management

It is possible to create both repository and organisational level secrets:

* **Repository:** Click on repo settings → secrets tab
* **Environment Based:**  Click on repo settings → Click "Environments" → Add Secret
  * Org based environment secrets require org admin permissions
* **Org Based:** Navigate to org home page → settings → secrets & variables → actions → secrets tab

### Scanning

* **Pre-Commit Secrets Detection:** Implement pre-commit hooks using tools like GuitGuardian:
  * Create a secret `GITGUARDIAN_API_KEY` within the repository settings → secrets tab
  * Create a file `.github/workflows/gitguardian.yml` with the following contents:

```none
name: GitGuardian Secrets Scan
on:
  pull_request:
    branches:
      - main
jobs:
  scanning:
    name: GitGuardian Secrets Scan
    runs-on: ubuntu-22.04
    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0 # fetch all history so multiple commits can be scanned
      - name: GitGuardian Secrets Scan
        id: gitguardian
        continue-on-error: true
        uses: GitGuardian/ggshield-action@v1
        env:
          GITHUB_PUSH_BEFORE_SHA: ${{ github.event.before }}
          GITHUB_PUSH_BASE_SHA: ${{ github.event.base }}
          GITHUB_DEFAULT_BRANCH: ${{ github.event.repository.default_branch }}
          GITGUARDIAN_API_KEY: ${{ secrets.GITGUARDIAN_API_KEY }}
        with:
          args: -v
```

* **Repository Scanning (GitHub Advanced Security):** Enable GitHub Advanced Security features (if available) which includes secret scanning across the entire repository history. This provides a retrospective safeguard against secrets accidentally committed in the past.
* **.gitignore Best Practices:** Ensure .gitignore files are comprehensive and prevent accidental committing of sensitive configuration files (e.g., .env, database connection strings).


## AWS Secrets Manager

It is possible to leverage AWS secrets manager as a centralised resource and leverage GitHub OIDC to assume IAM roles securely.

To perform this, a trust policy for GitHub must be setup as an OIDC identify provider within IAM:

```none
## Create OIDC Provider PoC (CLI)
aws iam create-open-id-connect-provider ‐‐url 
"https://token.actions.githubusercontent.com" ‐‐thumbprint-list 
"6938fd4d98bab03faadb97b34396831e3780aea1" ‐‐client-id-list 
'sts.amazonaws.com

# 6938fd4d98bab03faadb97b34396831e3780aea1 is the GitHub OIDC Thumbprint

## Create IAM Role & Assign Scope/Trust Policy Here
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "Federated": "<arn:aws:iam::<IAM ARN>:oidc-provider/token.actions.githubusercontent.com>"
            },
            "Action": "sts:AssumeRoleWithWebIdentity",
            "Condition": {
                "StringEquals": {
                    "token.actions.githubusercontent.com:sub": "repo: <EXAMPLEREPO>:ref:refs/heads/<ExampleBranch>",
                    "token.actions.githubusercontent.com:aud": "sts.amazonaws.com"
                }
            }
        }
    ]
}
```


Create a file `.github/workflows/aws-secrets-action.yml` with the following contents:

```none
# This is a basic workflow to help you get started with Actions
name:Connect to an AWS role from a GitHub repository

# Controls when the action will run. Invokes the workflow on push events but only for the main branch
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

env:
  
  AWS_REGION : <"us-east-1"> #Change to reflect your Region

# Permission can be added at job level or workflow level    
permissions:
      id-token: write   # This is required for requesting the JWT
      contents: read    # This is required for actions/checkout
jobs:
  AssumeRoleAndCallIdentity:
    runs-on: ubuntu-latest
    steps:
      - name: Git clone the repository
        uses: actions/checkout@v3
      - name: configure aws credentials
        uses: aws-actions/configure-aws-credentials@v4
        with:
          role-to-assume: <ROLE_HERE>
          role-session-name: GitHub_to_AWS_via_FederatedOIDC
          aws-region: ${{ env.AWS_REGION }}
      - name: Fetch Secrets
        uses: aws-actions/aws-secretsmanager-get-secrets@v1
        with:
          secret-ids: |
            <SECRETS_PATH>
```

### Secure Reccomendations

* **Secret Versioning:** Secrets Manager's versioning feature is critical. Every secret change creates a new version, allowing rollback in case of issues and providing an audit trail.
* **IAM Policies:** Strictly control access to Secrets Manager resources through IAM roles and policies: 
  * *__Principle of Least Privilege:__* Each service/application gets only the permissions it needs to retrieve specific secrets, not list all secrets or perform administrative actions. 
  * *__Tagging:__* Use tags on secrets for easier management, cost allocation, and policy enforcement (e.g., environment: production, owner: trading-service).
* **Monitoring & Auditing:** Enable CloudTrail logging on Secrets Manager to track all API calls (access attempts, creation, deletion). Integrate these logs into a SIEM system for alerting on suspicious activity.
* **Automated Rotation:** Implement Lambda functions triggered by CloudWatch Events to rotate secrets automatically using the Secrets Manager rotation functionality. This needs to be customized for each secret type (e.g., database credentials will have different rotation logic than API keys). Rotation schedules should be based on risk; where high-value secrets rotated more frequently.


\

\
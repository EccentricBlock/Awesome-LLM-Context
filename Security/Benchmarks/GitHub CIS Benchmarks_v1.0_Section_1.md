# Table of Contents
 - [1.1 Code Changes](#1.1-code-changes)
   - [1.1.1 Ensure any changes to code are tracked in a version control platform (Manual)](#1.1.1-ensure-any-changes-to-code-are-tracked-in-a-version-control-platform-(manual))
   - [1.1.2 Ensure any change to code can be traced back to its associated task (Manual)](#1.1.2-ensure-any-change-to-code-can-be-traced-back-to-its-associated-task-(manual))
   - [1.1.3 Ensure any change to code receives approval of two strongly authenticated users (Automated)](#1.1.3-ensure-any-change-to-code-receives-approval-of-two-strongly-authenticated-users-(automated))
   - [1.1.4 Ensure previous approvals are dismissed when updates are introduced to a code change proposal (Manual)](#1.1.4-ensure-previous-approvals-are-dismissed-when-updates-are-introduced-to-a-code-change-proposal-(manual))
   - [1.1.5 Ensure there are restrictions on who can dismiss code change reviews (Manual)](#1.1.5-ensure-there-are-restrictions-on-who-can-dismiss-code-change-reviews-(manual))
   - [1.1.6 Ensure code owners are set for extra sensitive code or configuration (Manual)](#1.1.6-ensure-code-owners-are-set-for-extra-sensitive-code-or-configuration-(manual))
   - [1.1.7 Ensure code owner's review is required when a change affects owned code (Manual)](#1.1.7-ensure-code-owners-review-is-required-when-a-change-affects-owned-code-(manual))
   - [1.1.8 Ensure inactive branches are periodically reviewed and removed (Manual)](#1.1.8-ensure-inactive-branches-are-periodically-reviewed-and-removed-(manual))
   - [1.1.9 Ensure all checks have passed before merging new code (Manual)](#1.1.9-ensure-all-checks-have-passed-before-merging-new-code-(manual))
   - [1.1.10 Ensure open Git branches are up to date before they can be merged into code base (Manual)](#1.1.10-ensure-open-git-branches-are-up-to-date-before-they-can-be-merged-into-code-base-(manual))
   - [1.1.11 Ensure all open comments are resolved before allowing code change merging (Manual)](#1.1.11-ensure-all-open-comments-are-resolved-before-allowing-code-change-merging-(manual))
   - [1.1.12 Ensure automatic code reviews with every code change (Automated)](#1.1.12-ensure-automatic-code-reviews-with-every-code-change-(automated))
   - [1.1.13 Ensure relevant code reviewers receive notifications on review requests (Manual)](#1.1.13-ensure-relevant-code-reviewers-receive-notifications-on-review-requests-(manual))
   - [1.1.14 Ensure only strongly authenticated users can push code to remote repositories (Automated)](#1.1.14-ensure-only-strongly-authenticated-users-can-push-code-to-remote-repositories-(automated))
   - [1.1.15 Ensure no local code repository can override approval processes (Manual)](#1.1.15-ensure-no-local-code-repository-can-override-approval-processes-(manual))
   - [1.1.16 Ensure code dependencies are regularly updated and security patches are applied (Manual)](#1.1.16-ensure-code-dependencies-are-regularly-updated-and-security-patches-are-applied-(manual))
   - [1.1.17 Ensure a secure code review process is in place (Manual)](#1.1.17-ensure-a-secure-code-review-process-is-in-place-(manual))
   - [1.1.18 Ensure automated tests are conducted for new code changes (Automated)](#1.1.18-ensure-automated-tests-are-conducted-for-new-code-changes-(automated))
   - [1.1.19 Ensure code is regularly scanned for security vulnerabilities (Automated)](#1.1.19-ensure-code-is-regularly-scanned-for-security-vulnerabilities-(automated))
   - [1.1.20 Ensure secure coding practices are followed and enforced (Manual)](#1.1.20-ensure-secure-coding-practices-are-followed-and-enforced-(manual))

- [1.2 GitHub Configuration](#1.2-github-configuration)
   - [1.2.1 Ensure GitHub configuration and settings are documented (Manual)](#1.2.1-ensure-github-configuration-and-settings-are-documented-(manual))
   - [1.2.2 Ensure branch protection is enabled on all active repositories (Manual)](#1.2.2-ensure-branch-protection-is-enabled-on-all-active-repositories-(manual))
   - [1.2.3 Ensure code review assignment is enabled for the main branch (Manual)](#1.2.3-ensure-code-review-assignment-is-enabled-for-the-main-branch-(manual))
   - [1.2.4 Ensure signed commits are required (Manual)](#1.2.4-ensure-signed-commits-are-required-(manual))
   - [1.2.5 Ensure there are restrictions on who can force push to any branch (Manual)](#1.2.5-ensure-there-are-restrictions-on-who-can-force-push-to-any-branch-(manual))
   - [1.2.6 Ensure repository templates are used for new repositories (Manual)](#1.2.6-ensure-repository-templates-are-used-for-new-repositories-(manual))
   - [1.2.7 Ensure repository topics are used for better discoverability (Manual)](#1.2.7-ensure-repository-topics-are-used-for-better-discoverability-(manual))

- [1.3 GitHub Security](#1.3-github-security)
   - [1.3.1 Ensure repository access is limited to the least privilege needed (Manual)](#1.3.1-ensure-repository-access-is-limited-to-the-least-privilege-needed-(manual))
   - [1.3.2 Ensure only strongly authenticated users can access repositories (Manual)](#1.3.2-ensure-only-strongly-authenticated-users-can-access-repositories-(manual))
   - [1.3.3 Ensure OAuth app and GitHub App access is restricted (Manual)](#1.3.3-ensure-oauth-app-and-github-app-access-is-restricted-(manual))
   - [1.3.4 Ensure repository access is reviewed periodically (Manual)](#1.3.4-ensure-repository-access-is-reviewed-periodically-(manual))
   - [1.3.5 Ensure repository access is revoked when no longer needed (Manual)](#1.3.5-ensure-repository-access-is-revoked-when-no-longer-needed-(manual))
   - [1.3.6 Ensure Personal Access Tokens (PATs) are not used for repository access (Manual)](#1.3.6-ensure-personal-access-tokens-(pats)-are-not-used-for-repository-access-(manual))
   - [1.3.7 Ensure SSH keys are not used for repository access (Manual)](#1.3.7-ensure-ssh-keys-are-not-used-for-repository-access-(manual))
   - [1.3.8 Ensure SSH certificates are used for repository access (Manual)](#1.3.8-ensure-ssh-certificates-are-used-for-repository-access-(manual))
   - [1.3.9 Ensure all repository actions are logged (Manual)](#1.3.9-ensure-all-repository-actions-are-logged-(manual))
   - [1.3.10 Ensure repositories are monitored for security vulnerabilities (Automated)](#1.3.10-ensure-repositories-are-monitored-for-security-vulnerabilities-(automated))
   - [1.3.11 Ensure anomalous repository activity is tracked (Manual)](#1.3.11-ensure-anomalous-repository-activity-is-tracked-(manual))
   - [1.3.12 Ensure Git access is limited based on IP addresses (Manual)](#1.3.12-ensure-git-access-is-limited-based-on-ip-addresses-(manual))
   - [1.3.13 Ensure anomalous code behavior is tracked (Manual)](#1.3.13-ensure-anomalous-code-behavior-is-tracked-(manual))
- [1.4 Third-Party](#1.4-third-party)
  - [1.4.1 Ensure administrator approval is required for every installed application (Manual)](#1.4.1-ensure-administrator-approval-is-required-for-every-installed-application-(manual))
  - [1.4.2 Ensure stale applications are reviewed and inactive ones are removed (Manual)](#1.4.2-ensure-stale-applications-are-reviewed-and-inactive-ones-are-removed-(manual))
  - [1.4.3 Ensure the access granted to each installed application is limited to the least privilege needed (Manual)](#1.4.3-ensure-the-access-granted-to-each-installed-application-is-limited-to-the-least-privilege-needed-(manual))
  - [1.4.4 Ensure only secured webhooks are used (Manual)](#1.4.4-ensure-only-secured-webhooks-are-used-(manual))
- [1.5 Code Risks](#1.5-code-risks)
  - [1.5.1 Ensure scanners are in place to identify and prevent sensitive data in code (Manual)](#1.5.1-ensure-scanners-are-in-place-to-identify-and-prevent-sensitive-data-in-code-(manual))
  - [1.5.2 Ensure scanners are in place to secure Continuous Integration (CI) pipeline instructions (Manual)](#1.5.2-ensure-scanners-are-in-place-to-secure-continuous-integration-(ci)-pipeline-instructions-(manual))
  - [1.5.3 Ensure scanners are in place to secure Infrastructure as Code (IaC) instructions (Manual)](#1.5.3-ensure-scanners-are-in-place-to-secure-infrastructure-as-code-(iac)-instructions-(manual))
  - [1.5.4 Ensure scanners are in place for code vulnerabilities (Manual)](#1.5.4-ensure-scanners-are-in-place-for-code-vulnerabilities-(manual))
  - [1.5.5 Ensure scanners are in place for open-source vulnerabilities in used packages (Manual)](#1.5.5-ensure-scanners-are-in-place-for-open-source-vulnerabilities-in-used-packages-(manual))



# 1 Source Code
## 1.1 Code Changes

### 1.1.1 Ensure any changes to code are tracked in a version control platform (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Manage all code projects in a version control platform.

**Rationale:**
Version control platforms keep track of every modification to code. They represent the cornerstone of code security, as well as allowing for better code collaboration within engineering teams. With granular access management, change tracking, and key signing of code edits, version control platforms are the first step in securing the software supply chain.

**Audit:**
Ensure that all code activity is managed through Github repository for every micro-service or application developed by an organization.

**Remediation:**
Upload existing code projects to a dedicated Github organization and repositories and create an identity for each active team member who might contribute or need access to it.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 2.4 Utilize Automated Software Inventory Tools | Utilize software inventory tools, when possible, throughout the enterprise to automate the discovery and documentation of installed software. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 2.4 Track Software Inventory Information | The software inventory system should track the name, version, publisher, and install date for all software, including operating systems authorized by the organization. | ● | ● |   |

---

### 1.1.2 Ensure any change to code can be traced back to its associated task (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Use a task management system to trace any code back to its associated task.

**Rationale:**
The ability to trace each piece of code back to its associated task simplifies the Agile and DevOps process by enabling transparency of any code changes. This allows faster remediation of bugs and security issues, while also making it harder to push unauthorized code changes to sensitive projects. Additionally, using a task management system simplifies achieving compliance, as it is easier to track each regulation.

**Audit:**
Ensure every code change can be traced back to its origin task in a task management system.

**Remediation:**
Use a task management system to manage tasks as the starting point for each code change. Whether it is a new feature, bug fix, or security fix - all should originate from a dedicated task (ticket) in your organization's task management system. These tasks should also be linked to the code changes themselves in a way that is easy to follow: from code to task, and from task back to code.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 16.1 Establish and Maintain a Secure Application Development Process | Establish and maintain a secure application development process. In the process, address such items as: secure application design standards, secure coding practices, developer training, vulnerability management, security of third-party code, and application security testing procedures. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 18.1 Establish Secure Coding Practices | Establish secure coding practices appropriate to the programming language and development environment being used. | ● | ● |   |

---
### 1.1.3 Ensure any change to code receives approval of two strongly authenticated users (Automated)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that every code change is reviewed and approved by two authorized contributors who are both strongly authenticated - using Multi-Factor Authentication (MFA), from the team relevant to the code change.

**Rationale:**
To prevent malicious or unauthorized code changes, the first layer of protection is the process of code review. This process involves engineer teammates reviewing each other's code for errors, optimizations, and general knowledge-sharing. With proper peer reviews in place, an organization can detect unwanted code changes very early in the process of release. In order to help facilitate code review, companies should employ automation to verify that every code change has been reviewed and approved by at least two team members before it is pushed into the code base. These team members should be from the team that is related to the code change, so it will be a meaningful review.

**Impact:**
To enforce a code review requirement, verification for a minimum of two reviewers must be put into place. This will ensure new code will not be able to be pushed to the code base before it has received two independent approvals.

**Audit:**
For every code repository in use, perform the next steps to verify that two approvals from the specific code repository team are required to push new code to the code base:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require a pull request before merging and Require approvals are checked, and verify that Required number of approvals before merging is set to 2.

**Remediation:**
For every code repository in use, perform the next steps to require two approvals from the specific code repository team in order to push new code to the code base:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you added the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Check Require a pull request before merging and Require approvals, and set Required number of approvals before merging to 2.
7. Click Create or Save changes.

**Default Value:**
0

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 16.12 Implement Code-Level Security Checks | Apply static and dynamic analysis tools within the application life cycle to verify that secure coding practices are being followed. |   | ● |   |
| **v7**            |                 |      |      |      |
| 18.8 Establish a Process to Accept and Address Reports of Software Vulnerabilities | Establish a process to accept and address reports of software vulnerabilities, including providing a means for external entities to contact your security group. | ● | ● |   |

---

### 1.1.4 Ensure previous approvals are dismissed when updates are introduced to a code change proposal (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that when a proposed code change is updated, previous approvals are declined, and new approvals are required.

**Rationale:**
An approval process is necessary when code changes are suggested. Through this approval process, however, changes can still be made to the original proposal even after some approvals have already been given. This means malicious code can find its way into the code base even if the organization has enforced a review policy. To ensure this is not possible, outdated approvals must be declined when changes to the suggestion are introduced.

**Impact:**
If new code changes are pushed to a specific proposal, all previously accepted code change proposals must be declined.

**Audit:**
For each code repository in use, perform the next steps to verify that each updated code suggestion declines the previously received approvals:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require a pull request before merging is checked, and verify that Dismiss stale pull request approvals when new commits are pushed is checked.

**Remediation:**
For each code repository in use, perform the next steps to enforce dismissal of given approvals to code change suggestions if those suggestions were updated:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you added the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require pull request reviews before merging and then Dismiss stale pull request approvals when new commits are pushed.
7. Click Create or Save changes.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------

|------|------|
| **v8**            |                 |      |      |      |
| 16.1 Establish and Maintain a Secure Application Development Process | Establish and maintain a secure application development process. In the process, address such items as: secure application design standards, secure coding practices, developer training, vulnerability management, security of third-party code, and application security testing procedures. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 18.1 Establish Secure Coding Practices | Establish secure coding practices appropriate to the programming language and development environment being used. | ● | ● |   |


---
### 1.1.5 Ensure there are restrictions on who can dismiss code change reviews (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Only trusted users should be allowed to dismiss code change reviews.

**Rationale:**
Dismissing a code change review permits users to merge new suggested code changes without going through the standard process of approvals. Controlling who can perform this action will prevent malicious actors from simply dismissing the required reviews to code changes and merging malicious or dysfunctional code into the code base.

**Impact:**
In cases where a code change proposal has been updated since it was last reviewed and the person who reviewed it isn't available for approval, a general collaborator would not be able to merge their code changes until a user with "dismiss review" abilities could dismiss the open review.

Users who are not allowed to dismiss code change reviews will not be permitted to do so, and thus are unable to waive the standard flow of approvals.

**Audit:**
For each code repository in use, perform the next steps to verify that only trusted users are allowed to dismiss code change reviews:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Verify that Require a pull request before merging and Restrict who can dismiss pull request reviews is checked.
6. Verify that no users and teams are specified except for organization and repository admins. If it is obligatory, verify that the users or teams specified were carefully selected to be trusted with the ability to dismiss code change reviews.

**Remediation:**
For each code repository in use, perform the next steps to restrict dismissal of code changes reviews unless it is necessary:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you added the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require pull request reviews before merging and Restrict who can dismiss pull request reviews.
7. Do not add any user or team unless it is obligatory. If it is obligatory, carefully select the users or teams whom you trust with the ability to dismiss code change reviews.
8. Click Create or Save changes.

**Default Value:**
By default, all users who have write access to the code repository are able to dismiss code change reviews.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | Restrict administrator privileges to dedicated administrator accounts on enterprise assets. Conduct general computing activities, such as internet browsing, email, and productivity suite use, from the user’s primary, non-privileged account. | ● | ● | ● |
| **v7**            |                 |      |      |      |
| 14.7 Enforce Access Control to Data through Automated Tools | Use an automated tool, such as host-based Data Loss Prevention, to enforce access controls to data even when data is copied off a system. |   | ● |   |

---
### 1.1.6 Ensure code owners are set for extra sensitive code or configuration (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Code owners are trusted users that are responsible for reviewing and managing an important piece of code or configuration. An organization is advised to set code owners for every extremely sensitive code or configuration.

**Rationale:**
Configuring code owners protects data by verifying that trusted users will notice and review every edit, thus preventing unwanted or malicious changes from potentially compromising sensitive code or configurations.

**Impact:**
Code owner users will receive notifications for every change that occurs to the code and subsequently added as reviewers of pull requests automatically.

**Audit:**
In every code repository, verify that a file named CODEOWNERS exists in the root, docs/, or .github/ directory of the repository. In the CODEOWNERS file, verify that the users specified are users you trust.

**Remediation:**
In every code repository create a CODEOWNERS file in the root, docs/, or .github/ directory of the repository. In the file, specify codeowners for the .github/workflows/ directory atleast. Specify organization members you trust. For example:
```plaintext
.github/workflows/ @user1 @user2
```

**Default Value:**
None

**References:**
1. [GitHub Documentation on Code Owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners)

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 6.8 Define and Maintain Role-Based Access Control | Define and maintain role-based access control, through determining and documenting the access rights necessary for each role within the enterprise to successfully carry out its assigned duties. Perform access control reviews of enterprise assets to validate that all privileges are authorized, on a recurring schedule at a minimum annually, or more frequently. |   | ● |   |
| **v7**            |                 |      |      |      |
| 14.6 Protect Information through Access Control Lists | Protect all information stored on systems with file system, network share, claims, application, or database specific access control lists. These controls will enforce the principle that only authorized individuals should have access to the information based on their need to access the information as a part of their responsibilities. | ● | ● | ● |

---
### 1.1.7 Ensure code owner's review is required when a change affects owned code (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure trusted code owners are required to review and approve any code change proposal made to their respective owned areas in the code base.

**Rationale:**
Configuring code owners ensures that no code, especially code which could prove malicious, will slip into the source code or configuration files of a repository. This allows an organization to mark areas in the code base that are especially sensitive or more prone to an attack. It can also enforce review by specific individuals who are designated as owners to those areas so that they may filter out unauthorized or unwanted changes beforehand.

**Impact:**
If an organization enforces code owner-based reviews, some code change proposals would not be able to be merged to the codebase before specific, trusted individuals approve them.

**Audit:**
For every code repository in use, perform the following steps to verify that code owners are required to review all code change proposals relevant to areas they own before code merge:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require a pull request before merging and Require review from Code Owners are checked.

**Remediation:**
For every code repository in use, perform the following steps to require code owners' approvals for each change proposal related to code they own:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require pull request reviews before merging and Require review from Code Owners.
7. Click Create or Save changes.

**Default Value:**
Code owners are not required to review changes by default.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 16.9 Train Developers in Application Security Concepts and Secure Coding | Ensure that all software development personnel receive training in writing secure code for their specific development environment and responsibilities. Training can include general security principles and application security standard practices. Conduct training at least annually and design in a way to promote security within the development team, and build a culture of security among the developers. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 18.1 Establish Secure Coding Practices | Establish secure coding practices appropriate to the programming language and development environment being used. | ● | ● |   |

---
### 1.1.8 Ensure inactive branches are periodically reviewed and removed (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Keep track of code branches that are inactive for a lengthy period of time and periodically remove them.

**Rationale:**
Git branches that have been inactive (i.e., no new changes introduced) for a long period of time are enlarging the surface of attack for malicious code injection, sensitive data leaks, and CI pipeline exploitation. They potentially contain outdated dependencies which may leave them highly vulnerable. They are more likely to be improperly managed, and could possibly be accessed by a large number of members of the organization.

**Impact:**
Removing inactive Git branches means that any code changes they contain would be removed along with them, thus work done in the past might not be accessible after auditing for inactivity.

**Audit:**
For each code repository in use, verify that all existing Git branches are active or have yet to be checked for inactivity by performing the next steps:

1. On GitHub.com, navigate to the main page of the repository.
2. Above the list of files, click Branches.
3. Use the navigation at the top of the page to view the Stale branches. The Stale view shows all branches that no one has committed to in the last three months, ordered by the branches with the oldest commits first.
4. If the list is empty, you are compliant. If the list is not empty, but there is a valid reason the branches listed are not deleted, you are compliant.

**Remediation:**
For each code repository in use, review existing Git branches and remove those which have not been active for a period of time by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Above the list of files, click Branches.
3. Use the navigation at the top of the page to view the Stale branches. The Stale view shows all branches that no one has committed to in the last three months, ordered by the branches with the oldest commits first.
4. For each branch listed, either delete it by clicking the trash bin icon, or find the valid reason it still exists.

You can perform the next steps to prevent pull request branches from becoming stale branches:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. Under "Pull Requests", select Automatically delete head branches.

**Default Value:**
By default, newly opened Git branches would never be removed, regardless of activity or inactivity.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 16.11 Leverage Vetted Modules or Services for Application Security Components | Leverage vetted modules or services for application security components, such as identity management, encryption, and auditing and logging. Using platform features in critical security functions will reduce developers’ workload and minimize the likelihood of design or implementation errors. Modern operating systems provide effective mechanisms for identification, authentication, and authorization and make those mechanisms available to applications. Use only standardized, currently accepted, and extensively reviewed encryption algorithms. Operating systems also provide mechanisms to create and maintain secure audit logs. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 18.2 Ensure Explicit Error Checking is Performed for All In-house Developed Software | For in-house developed software, ensure that explicit error checking is performed and documented for all input, including for size, data type, and acceptable ranges or formats. | ● | ● |   |

---
### 1.1.9 Ensure all checks have passed before merging new code (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Before a code change request can be merged to the code base, all predefined checks must successfully pass.

**Rationale:**
On top of manual reviews of code changes, a code protect should contain a set of prescriptive checks which validate each change. Organizations should enforce those status checks so that changes can only be introduced if all checks have successfully passed. This set of checks should serve as the absolute quality, stability, and security conditions which must be met in order to merge new code to a project.

**Impact:**
Code changes in which all checks do not pass successfully would not be able to be pushed into the code base of the specific code repository.

**Audit:**
For each code repository in use, verify that status checks are required to pass before allowing any code change proposal merge by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require status checks to pass before merging is checked.

**Remediation:**
For each code repository in use, require all status checks to pass before permitting a merge of new code by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", check if there is a rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require status checks to pass before merging.
7. Click Create or Save changes.

**Default Value:**
By default, no checks are defined per project, and thus no enforcement of checks is made.

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 16.1 Establish and Maintain a Secure Application Development Process | Establish and maintain a secure application development process. In the process, address such items as: secure application design standards, secure coding practices, developer training, vulnerability management, security of third-party code, and application security testing procedures. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 18.1 Establish Secure Coding Practices | Establish secure coding practices appropriate to the programming language and development environment being used. | ● | ● |   |

---
### 1.1.10 Ensure open Git branches are up to date before they can be merged into code base (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Organizations should make sure each suggested code change is in full sync with the existing state of its origin code repository before allowing merging.

**Rationale:**
Git branches can easily become outdated since the origin code repository is constantly being edited. This means engineers working on separate code branches can accidentally include outdated code with potential security issues which might have already been fixed, overriding the potential solutions for those security issues when merging their own changes.

**Impact:**
If enforced, outdated branches would not be able to be merged into their origin repository without first being updated to contain any recent changes.

**Audit:**
For each code repository in use, verify that open branches must be updated before merging is permitted by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require status checks to pass before merging and Require branches to be up to date before merging are checked.

**Remediation:**
For each code repository in use, enforce a policy to only allow merging open branches if they are current with the latest change from their original repository by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require status checks to pass before merging and Require branches to be up to date before merging.
7. Click Create or Save changes.

**Default Value:**
By default, there is no requirement to update a branch before merging it.

**References:**
1. [GitHub Blog on Keeping Pull Request Branches Up to Date](https://github.blog/changelog/2022-02-03-more

-ways-to-keep-your-pull-request-branch-up-to-date/)

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 16.1 Establish and Maintain a Secure Application Development Process | Establish and maintain a secure application development process. In the process, address such items as: secure application design standards, secure coding practices, developer training, vulnerability management, security of third-party code, and application security testing procedures. Review and update documentation annually, or when significant enterprise changes occur that could impact this Safeguard. | ● | ● |   |
| **v7**            |                 |      |      |      |
| 18.1 Establish Secure Coding Practices | Establish secure coding practices appropriate to the programming language and development environment being used. | ● | ● |   |


---
### 1.1.11 Ensure all open comments are resolved before allowing code change merging (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Organizations should enforce a "no open comments" policy before allowing code change merging.

**Rationale:**
In an open code change proposal, reviewers can leave comments containing their questions and suggestions. These comments can also include potential bugs and security issues. Requiring all comments on a code change proposal to be resolved before it can be merged ensures that every concern is properly addressed or acknowledged before the new code changes are introduced to the code base.

**Impact:**
Code change proposals containing open comments would not be able to be merged into the code base.

**Audit:**
For every code repository in use, verify that each merged code change does not contain open, unattended comments by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require conversation resolution before merging is checked.

**Remediation:**
For each code repository in use, require open comments to be resolved before the relevant code change can be merged by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require conversation resolution before merging.
7. Click Create or Save changes.

**Default Value:**
By default, code changes with open comments on them are able to be merged into the code base.

---

### 1.1.12 Ensure verification of signed commits for new changes before merging (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Ensure every commit in a pull request is signed and verified before merging.

**Rationale:**
Signing commits, or requiring to sign commits, gives other users confidence about the origin of a specific code change. It ensures that the author of the change is not hidden and is verified by the version control system, thus the change comes from a trusted source.

**Impact:**
Pull requests with unsigned commits cannot be merged.

**Audit:**
Ensure only signed commits can be merged for every branch, especially the main branch, via branch protection rules by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require signed commits is checked.

**Remediation:**
For each repository in use, enforce the branch protection rule of requiring signed commits, and make sure only signed commits are capable of merging by performing the following:

1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require signed commits.
7. Click Create or Save changes.

**References:**
1. [GitHub Documentation on Signing Commits](https://docs.github.com/en/authentication/managing-commit-signature-verification/signing-commits)

---

### 1.1.13 Ensure linear history is required (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Linear history is the name for Git history where all commits are listed in chronological order, one after another. Such history exists if a pull request is merged either by rebase merge (re-order the commits history) or squash merge (squashes all commits to one). Ensure that linear history is required by requiring the use of rebase or squash merge when merging a pull request.

**Rationale:**
Enforcing linear history produces a clear record of activity, and as such it offers specific advantages: it is easier to follow, easier to revert a change, and bugs can be found more easily.

**Impact:**
Pull request cannot be merged except squash or rebase merge.

**Audit:**
For every code repository in use, perform the following steps to verify that linear history is required and/or that only squash merge and rebase merge are allowed:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Require linear history is checked.

**Remediation:**
For every code repository in use, perform the following steps to require linear history and/or allow only rebase merge and squash merge:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Require linear history.
7. Click Create or Save changes.

---

### 1.1.14 Ensure branch protection rules are enforced for administrators (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure administrators are subject to branch protection rules.

**Rationale:**
Administrators by default are excluded from any branch protection rules. This means these privileged users (both on the repository and organization levels) are not subject to protections meant to prevent untrusted code insertion, including malicious code. This is extremely important since administrator accounts are often targeted for account hijacking due to their privileged role.

**Impact:**
Administrator users won't be able to push code directly to the protected branch without being compliant with listed branch protection rules.

**Audit:**
For every code repository in use, validate branch protection rules also apply to administrator accounts by performing the next steps:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Do not allow bypassing the above settings is checked.

**Remediation:**
For every code repository in use, enforce branch protection rules on administrators as well, by performing the following:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Do not allow bypassing the above settings.
7. Click Create or Save changes.

**Default Value:**
Administrator accounts are not subject to branch protection rules by default.

**References:**
1. [GitHub Documentation on Managing Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/managing-a-branch-protection-rule)

---

### 1.1.15 Ensure pushing or merging of new code is restricted to specific individuals or teams (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Ensure that only trusted users can push or merge new code to protected branches.

**Rationale:**
Requiring that only trusted users may push or merge new changes reduces the risk of unverified code, especially malicious code, to a protected branch by reducing the number of trusted users who are capable of doing such.

**Impact:**
Only administrators and trusted users can push or merge to the protected branch.

**Audit:**
For every code repository in use, ensure only trusted and responsible users can push or merge new code by performing the following:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation

" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Restrict who can push to matching branches is checked and that only trusted and responsible users and teams are selected.

**Remediation:**
For every code repository in use, allow only trusted and responsible users to push or merge new code by performing the following:

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Select Restrict who can push to matching branches and choose trusted and responsible users and teams who will have the permission to do so.
7. Click Create or Save changes.

**References:**
1. [GitHub Documentation on Managing Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/managing-a-branch-protection-rule)

**CIS Controls:**

| Controls          | Version Control | IG 1 | IG 2 | IG 3 |
|-------------------|-----------------|------|------|------|
| **v8**            |                 |      |      |      |
| 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | Restrict administrator privileges to dedicated administrator accounts on enterprise assets. Conduct general computing activities, such as internet browsing, email, and productivity suite use, from the user’s primary, non-privileged account. | ● | ● | ● |


### 1.1.16 Ensure force push code to branches is denied (Manual)

**Profile Applicability:**
- Level 1

**Description:**
The "Force Push" option allows users with "Push" permissions to force their changes directly to the branch without a pull request, and thus should be disabled.

**Rationale:**
The "Force Push" option allows users to override the existing code with their own code. This can lead to both intentional and unintentional data loss, as well as data infection with malicious code. Disabling the "Force Push" option prohibits users from forcing their changes to the master branch, which ultimately prevents malicious code from entering source code.

**Impact:**
Users cannot force push to protected branches.

**Audit:**
For every code repository in use, validate that no one can force push code by performing the following:
1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Allow force pushes is not checked.

**Remediation:**
For each repository in use, block the option to "Force Push" code by performing the following:
1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Uncheck Allow force pushes.
7. Click Create or Save changes.

**References:**
1. [GitHub Documentation on Managing Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/managing-a-branch-protection-rule)

**CIS Controls:**

| Controls | Version Control | IG 1 | IG 2 | IG 3 |
|----------|-----------------|------|------|------|
| **v8**   | 16.1 Establish and Maintain a Secure Application Development Process | ● | ● | ● |

---

### 1.1.17 Ensure branch deletions are denied (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that users with only push access are incapable of deleting a protected branch.

**Rationale:**
When enabling deletion of a protected branch, any user with at least push access to the repository can delete a branch. This can be potentially dangerous, as a simple human mistake or a hacked account can lead to data loss if a branch is deleted. It is therefore crucial to prevent such incidents by denying protected branch deletion.

**Impact:**
Protected branches cannot be deleted.

**Audit:**
For each repository that is being used, verify that protected branches cannot be deleted by performing the following:
1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, you are not compliant.
5. Ensure that Allow deletions is not checked.

**Remediation:**
For each repository that is being used, block the option to delete protected branches by performing the following:
1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", verify that there is at least one rule for your main branch. If there is, click Edit to its right. If there isn't, click Add rule.
5. If you add the rule, under "Branch name pattern", type the branch name or pattern you want to protect.
6. Uncheck Allow deletions.
7. Click Create or Save changes.

**References:**
1. [GitHub Documentation on Managing Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/managing-a-branch-protection-rule)

**CIS Controls:**

| Controls | Version Control | IG 1 | IG 2 | IG 3 |
|----------|-----------------|------|------|------|
| **v8**   | 3.4 Enforce Data Retention | ● | ● | ● |

---

### 1.1.18 Ensure any merging of code is automatically scanned for risks (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that every pull request is required to be scanned for risks.

**Rationale:**
Scanning pull requests to detect risks allows for early detection of vulnerable code and/or dependencies and helps mitigate potentially malicious code.

**Audit:**
For each repository in use, ensure that every pull request must be scanned for risks by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Actions.
3. Ensure that at least one workflow is configured to run like that:
   ```yaml
   on:
     push:
       branches: [ "main" ]
     pull_request:
       branches: [ "main" ]
   ```
   and that it has a step that runs code scanning on the code.

**Remediation:**
For every repository in use, enforce risk scanning on every pull request by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Actions.
3. If the repository already has at least one workflow set up and running, click New workflow and go to step 5. If there are currently no workflows configured for the repository, go to the next step.
4. Scroll down to the "Security" category and click Configure under the workflow you want to configure or click View all to see all available security workflows.
5. On the right pane of the workflow page, click Documentation and follow the on-screen instructions to tailor the workflow to your needs.

**CIS Controls:**

| Controls | Version Control | IG 1 | IG 2 | IG 3 |
|----------|-----------------|------|------|------|
| **v8**   | 7.5 Perform Automated Vulnerability Scans of Internal Enterprise Assets | ● | ● | ● |
| **v8**   | 7.6 Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets | ● | ● | ● |
| **v7**   | 3.1 Run Automated Vulnerability Scanning Tools | ● | ● | ● |

---

### 1.1.19 Ensure any changes to branch protection rules are audited (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that changes in the branch protection rules are audited.

**Rationale:**
Branch protection rules should be configured on every repository. The only users who may change such rules are administrators. In a case of an attack on an administrator account or of human error on the part of an administrator, protection rules could be disabled, and thus decrease source code confidentiality as a result. It is important to track and audit such changes to prevent potential incidents as soon as possible.

**Audit:**
Ensure changes in branch protection rules are audited by performing the following regularly:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Archives" section of the sidebar, click Logs, then click Audit log.
4. Use the action qualifier in your query and look for protected_branch category. Ensure every action is reasonable and secure and is investigated if not.

**Remediation:**
Use the audit log to audit changes in branch protection rules by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Archives" section of the sidebar, click Logs, then click Audit log.
4. Use the action qualifier in your query and look for protected_branch category. Ensure every action is reasonable and secure and investigate if not.

**References:**
1. [GitHub Documentation on Managing Branch Protection Rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/defining-the-mergeability-of-pull-requests/about-protected-branches)

**CIS Controls:**

| Controls | Version Control | IG 1 | IG 2 | IG 3 |
|----------|-----------------|------|------|------|
| **v8**   | 8.5 Collect Detailed Audit Logs | ● | ● | ● |
| **v7**   | 6.2 Activate audit logging | ● | ● | ● |

---

### 1.1.20 Ensure branch protection is enforced on the default branch (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Enforce branch protection on the default and main branch.

**Rationale:**


The default or main branch of repositories is considered very important, as it is eventually gets deployed to the production. Therefore it needs protection. By enforcing branch protection rules on this branch, it is secured from unwanted or unauthorized changes. It can also be protected from untested and unreviewed changes and more.

**Audit:**
Perform the following to ensure branch protection is enforced on the main branch:
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Under Branch protection rules, verify that there is a rule applied to the "main" or default branch.

**Remediation:**
Perform the following to enforce branch protection on the main branch:
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Code and automation" section of the sidebar, click Branches.
4. Next to "Branch protection rules", click Add rule.
5. Under "Branch name pattern", type the branch name or pattern you want to protect. Ensure it applies to the main branch name.
6. Configure policies you want.
7. Click Create.

**CIS Controls:**

| Controls | Version Control | IG 1 | IG 2 | IG 3 |
|----------|-----------------|------|------|------|
| **v8**   | 16.7 Use Standard Hardening Configuration Templates for Application Infrastructure | ● | ● | ● |

Here are sections 1.2 - 1.2.7 from the CIS GitHub Benchmark v1.0.0 converted to Markdown format, with the CIS Controls section provided as a table:

---

## 1.2 Repository Management

### 1.2.1 Ensure all public repositories contain a SECURITY.md file (Manual)

**Profile Applicability:**
- Level 1

**Description:**
A SECURITY.md file is a security policy file that offers instruction on reporting security vulnerabilities in a project. When someone creates an issue within a specific project, a link to the SECURITY.md file will subsequently be shown.

**Rationale:**
A SECURITY.md file provides users with crucial security information. It can also serve an important role in project maintenance, encouraging users to think ahead about how to properly handle potential security issues, updates, and general security practices.

**Audit:**
Verify that each public repository has a SECURITY.md file by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under the repository name, click Security.
3. Verify that Security policy is enabled.

**Remediation:**
Enforce that each public repository has a SECURITY.md file by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under the repository name, click Security.
3. In the left sidebar, click Security policy.
4. Click Start setup.
5. In the new SECURITY.md file, add information about supported versions of your project and how to report a vulnerability.
6. At the bottom of the page, type a commit message.
7. Below the commit message fields, choose to create a new branch for your commit and then create a pull request.
8. Click Propose file change.

**CIS Controls:**

| Version | Controls                                                                 | IG1 | IG2 | IG3 |
|---------|--------------------------------------------------------------------------|-----|-----|-----|
| v8      | 16.2 Establish and Maintain a Process to Accept and Address Software Vulnerabilities | ●   |     |     |

---

### 1.2.2 Ensure repository creation is limited to specific members (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Limit the ability to create repositories to trusted users and teams.

**Rationale:**
Restricting repository creation to trusted users and teams is recommended to keep the organization properly structured, prevent impersonation, and avoid overloading the version-control system. It simplifies source code tracking, making it easier to detect malicious acts and reduces the risk of unintentional public sharing of sensitive data.

**Impact:**
Specific users will not be permitted to create repositories.

**Audit:**
Verify that only trusted users and teams can create repositories by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Repository creation", ensure that Public and Private are not checked. This means only owners are able to create repositories.

**Remediation:**
Restrict repository creation to trusted users and teams only by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Repository creation", unselect both options - Public and Private.
5. Click Save.

**CIS Controls:**

| Version | Controls                                                           | IG1 | IG2 | IG3 |
|---------|--------------------------------------------------------------------|-----|-----|-----|
| v8      | 4.6 Securely Manage Enterprise Assets and Software                 | ●   |     |     |

---

### 1.2.3 Ensure repository deletion is limited to specific users (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Limit the ability to delete repositories to trusted users.

**Rationale:**
Restricting repository deletion to trusted users prevents accidental or malicious deletion of valuable repositories. It ensures that only authorized personnel can perform such critical actions, maintaining the integrity and availability of the source code.

**Impact:**
Only specific, trusted users can delete repositories.

**Audit:**
Verify that only trusted users can delete repositories by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Repository deletion", ensure that the appropriate restrictions are in place.

**Remediation:**
Restrict repository deletion to trusted users by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Repository deletion", set the appropriate restrictions.
5. Click Save.

**CIS Controls:**

| Version | Controls                                                               | IG1 | IG2 | IG3 |
|---------|------------------------------------------------------------------------|-----|-----|-----|
| v8      | 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | ●   | ●   | ●   |

---

### 1.2.4 Ensure issue deletion is limited to specific users (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Limit the ability to delete issues to trusted users.

**Rationale:**
Restricting issue deletion to trusted users ensures that valuable information, discussions, and tracking are not lost due to accidental or malicious deletion. This maintains the integrity and continuity of project management.

**Impact:**
Only specific, trusted users can delete issues.

**Audit:**
Verify that only trusted users can delete issues by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Issue deletion", ensure that the appropriate restrictions are in place.

**Remediation:**
Restrict issue deletion to trusted users by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Issue deletion", set the appropriate restrictions.
5. Click Save.

**CIS Controls:**

| Version | Controls                                                              | IG1 | IG2 | IG3 |
|---------|-----------------------------------------------------------------------|-----|-----|-----|
| v8      | 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | ●   | ●   | ●   |

---

### 1.2.5 Ensure all copies (forks) of code are tracked and accounted for (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that all forks of the repositories are tracked and reviewed regularly.

**Rationale:**
Tracking forks ensures that all copies of the source code are accounted for, which helps in monitoring and managing code distribution, detecting potential unauthorized changes, and ensuring compliance with organizational policies.

**Impact:**
Forks are tracked and monitored, reducing the risk of unauthorized changes and distribution.

**Audit:**
Verify that all forks of the repositories are tracked by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Insights.
3. In the left sidebar, click Forks.
4. Review the list of forks and ensure they are tracked and monitored.

**Remediation:**
Track and account for all forks of repositories by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Insights.
3. In the left sidebar, click Forks.
4. Regularly review and monitor the list of forks.

**CIS Controls:**

| Version | Controls                                                              | IG1 | IG2 | IG3 |
|---------|-----------------------------------------------------------------------|-----|-----|-----|
| v8      | 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | ●   | ●   | ●   |

---

### 1.2.6 Ensure all code projects are tracked for changes in visibility status (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Track any changes in the visibility status of code projects to ensure they are properly monitored.

**Rationale:**
Tracking changes in the visibility status of code projects ensures that any changes from private to public (or vice versa) are accounted for and that the appropriate security measures are maintained. This helps in preventing unauthorized access and protecting sensitive information.

**Impact:**
Changes in visibility status are tracked, reducing the risk of unauthorized access to sensitive information.

**Audit:**
Verify that changes in visibility status are tracked by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Audit log.
4. Use the visibility qualifier in your query to review changes in visibility status.

**Remediation:**
Track changes in visibility status by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Audit log.
4. Use the visibility qualifier in your query to monitor changes in visibility status.

**CIS Controls:**

| Version | Controls                                | IG1 | IG2 | IG3 |
|---------|-----------------------------------------|-----|-----|-----|
| v8      | 8.5 Collect Detailed Audit Logs          | ●   | ●   | ●   |

---

### 1.2.7 Ensure inactive repositories are reviewed and archived (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that inactive repositories are regularly reviewed and archived.

**Rationale:**
Regular review and archiving of inactive repositories help in maintaining the organization’s repository structure, reducing clutter, and ensuring that only active, maintained projects are readily accessible. This can help in managing resources and improving the security posture by reducing the attack surface.

**Impact:**
Inactive repositories are regularly reviewed and archived, reducing clutter and improving security.

**Audit:**
Verify that inactive repositories are reviewed and archived by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Audit log.
4. Use the repository qualifier in your query to review inactive repositories.

**Remediation:**
Review and archive inactive repositories by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Audit log.
4. Use the repository qualifier in your query to identify inactive repositories and take appropriate action to archive them.

**CIS Controls:**

| Version | Controls                                | IG1 | IG2 | IG3 |
|---------|-----------------------------------------|-----|-----|-----|
| v8      | 3.4 Enforce Data Retention              | ●   |     |     |

---

Here are sections 1.3.1 - 1.3.13 from the CIS GitHub Benchmark v1.0.0 converted to Markdown format, with the CIS Controls section provided as a table:

---

## 1.3 Contribution Access

### 1.3.1 Ensure inactive users are reviewed and removed periodically (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Track inactive user accounts and periodically remove them.

**Rationale:**
User accounts that have been inactive for a long period of time are enlarging the surface of attack. Inactive users with high-level privileges are of particular concern, as these accounts are more likely to be targets for attackers. This could potentially allow access to large portions of an organization should such an attack prove successful. It is recommended to remove them as soon as possible in order to prevent this.

**Audit:**
If you have GitHub AE, verify that all user accounts are active by performing the following:
1. From an administrative account on GitHub AE, in the upper-right corner of any page, click the rocket icon.
2. If you're not already on the "Site admin" page, in the upper-left corner, click Site admin.
3. In the left sidebar, click Dormant users.
4. Verify that the list is empty.

If you have GitHub Enterprise Cloud, perform the following:
1. In the top-right corner of GitHub.com, click your profile photo, then click Your enterprises.
2. In the list of enterprises, click the enterprise you want to view.
3. In the enterprise account sidebar, click Compliance.
4. To download your Dormant Users (beta) report as a CSV file, under "Other", click Download.
5. Verify that there are no users listed.

**Remediation:**
If you have GitHub AE, perform the following to review inactive user accounts and remove them:
1. From an administrative account on GitHub AE, in the upper-right corner of any page, click the rocket icon.
2. If you're not already on the "Site admin" page, in the upper-left corner, click Site admin.
3. In the left sidebar, click Dormant users.
4. Find the users listed there under Your organizations > your organization > People and select them.
5. Click Remove from organization and Remove members.

If you have GitHub Enterprise Cloud, perform the following:
1. In the top-right corner of GitHub.com, click your profile photo, then click Your enterprises.
2. In the list of enterprises, click the enterprise you want to view.
3. In the enterprise account sidebar, click Compliance.
4. To download your Dormant Users (beta) report as a CSV file, under "Other", click Download.
5. Find the users listed in the file under Your organizations > your organization > People and select them.
6. Click Remove from organization and Remove members.

**CIS Controls:**

| Version | Controls | IG1 | IG2 | IG3 |
|---------|----------|-----|-----|-----|
| v8 | 5.3 Disable Dormant Accounts | ● | ● | ● |
| v7 | 16.9 Disable Dormant Accounts | ● | ● | ● |

---

### 1.3.2 Ensure team creation is limited to specific members (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Limit ability to create teams to trusted and specific users.

**Rationale:**
The ability to create new teams should be restricted to specific members in order to keep the organization orderly and ensure users have access to only the lowest privilege level necessary. Teams typically inherit permissions from their parent team, thus if base permissions are less restricted and any user has the ability to create a team, a permission leverage could occur in which certain data is made available to users who should not have access to it. Such a situation could potentially lead to the creation of shadow teams by an attacker. Restricting team creation will also reduce additional clutter in the organizational structure, and as a result will make it easier to track changes and anomalies.

**Impact:**
Only specific users will be able to create new teams.

**Audit:**
For every organization, ensure that team creation is limited to specific, trusted users by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Team creation rules", verify that Allow members to create teams is not selected.

**Remediation:**
For every organization, limit team creation to specific, trusted users by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Team creation rules", deselect Allow members to create teams.
5. Click Save.

**CIS Controls:**

| Version | Controls | IG1 | IG2 | IG3 |
|---------|----------|-----|-----|-----|
| v8 | 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | ● | ● | ● |
| v7 | 4.3 Ensure the Use of Dedicated Administrative Accounts | ● | ● | ● |

---

### 1.3.3 Ensure minimum number of administrators are set for the organization (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure the organization has a minimum number of administrators.

**Rationale:**
Organization administrators have the highest level of permissions, including the ability to add/remove collaborators, create or delete repositories, change branch protection policy, and convert to a publicly-accessible repository. Due to the permissive access granted to an organization administrator, it is highly recommended to keep the number of administrator accounts as minimal as possible.

**Audit:**
Verify the minimum number of administrators in your organization by performing the following:
1. In the top right corner of GitHub, click your profile photo, then click Your profile.
2. On the left side of your profile page, under "Organizations", click the icon for your organization.
3. Under your organization name, click People.
4. In the Role drop-down, choose Owners.
5. If there are minimum number of members in the list, you are compliant.

**Remediation:**
Set the minimum number of administrators in your organization by performing the following:
1. In the top right corner of GitHub, click your profile photo, then click Your profile.
2. On the left side of your profile page, under "Organizations", click the icon for your organization.
3. Under your organization name, click People.
4. In the Role drop-down, choose Owners.
5. If there are more than the minimum number of members, remove excess members from the list.

**CIS Controls:**

| Version | Controls | IG1 | IG2 | IG3 |
|---------|----------|-----|-----|-----|
| v8 | 5.4 Restrict Administrator Privileges to Dedicated Administrator Accounts | ● | ● | ● |
| v7 | 4.1 Maintain Inventory of Administrative Accounts | ● | ● | ● |

---

### 1.3.4 Ensure removal of access rights for inactive users (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure that access rights for inactive users are removed.

**Rationale:**
Inactive user accounts are a significant security risk because they provide potential attackers with an entry point into an organization's systems. By regularly reviewing and removing access rights for inactive users, organizations can reduce the risk of unauthorized access.

**Impact:**
Inactive user accounts will be deactivated, reducing the risk of unauthorized access.

**Audit:**
Verify that access rights for inactive users are removed by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Dormant users.
4. Verify that the list is empty.

**Remediation:**
Remove access rights for inactive users by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Dormant users.
4. Find the users listed there and remove their access.

**CIS Controls:**

| Version | Controls | IG1 | IG2 | IG3 |
|---------|----------|-----|-----|-----|
| v8 | 5.3 Disable Dormant Accounts | ● | ● | ● |
| v7 | 16.9 Disable Dormant Accounts | ● | ● | ● |

---

### 1.3.5 Ensure the organization is requiring members to use Multi-Factor Authentication (MFA) (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Require members of the organization to use Multi-Factor Authentication (MFA) in addition to a standard username and password when authenticating to the source code management platform.

**Rationale:**
By default, every user authenticates within the system by password only. If the password of a user is compromised, however, the user account and every repository to which they have access are in danger of data loss, malicious code commits, and data theft. It is therefore recommended that each user has Multi-Factor Authentication enabled. This adds an additional layer of protection to ensure the account remains secure even if the user's password is compromised.

**Impact:**
Members will be removed from the organization if they don't have Multi-Factor Authentication already enabled. If this is the case, it is recommended that an invitation be sent to reinstate the user's access and former privileges. They must enable Multi-Factor Authentication to accept the invitation.

**Audit:**
For every organization that exists in your GitHub platform, verify that Multi-Factor Authentication is enforced and is the only way to authenticate, by doing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Security" section of the sidebar, click Authentication security.
4. Under "Authentication", check if Require two-factor authentication for everyone in your organization is checked. If so, you are compliant.

**Remediation:**
For every organization that exists in your GitHub platform, enforce Multi-Factor Authentication and define it as the only way to authenticate, by doing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Security" section of the sidebar, click Authentication security.
4. Under "Authentication", select Require two-factor authentication for everyone in your organization, then click Save.
5. If prompted, read the information about members and outside collaborators who will be removed from the organization. Type your organization's name to confirm the change, then click Remove members & require two-factor authentication.

**CIS Controls:**

| Version | Controls | IG1 | IG2 | IG3 |
|---------|----------|-----|-----|-----|
| v8      | 6.3 Require MFA for Externally-Exposed Applications | ●   | ●   |     |
| v8      | 6.4 Require MFA for Remote Network Access             | ●   | ●   | ●   |
| v8      | 6.5 Require MFA for Administrative Access             | ●   | ●   | ●   |
| v7      | 16.3 Require Multi-factor Authentication              | ●   | ●   |     |

---

### 1.3.6 Ensure new members are required to be invited using company-approved email (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Existing members of an organization can invite new members to join, however, new members must only be invited with their company-approved email.

**Rationale:**
Ensuring new members of an organization have company-approved email prevents existing members of the organization from inviting arbitrary new users to join. Without this verification, they can invite anyone who is using the organization's version control system or has an active email account, thus allowing outside users (and potential threat actors) to easily gain access to company private code and resources. This practice will subsequently reduce the chance of human error or typos when inviting a new member.

**Impact:**
Existing members would not be able to invite new users who do not have a company-approved email address.

**Audit:**
For each organization in use, verify for every invitation that the invited email address is company-approved by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Click the name of your organization and under your organization name, click People.
3. On the People tab, click Invitations. Verify that each invitation email is company approved by your company.

**Remediation:**
For each organization, allow only users with company-approved email to be invited. If a user was invited without company-approved email, perform the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Click the name of your organization and under your organization name, click People.
3. On the People tab, click Invitations. Next to the username or email address of the person whose invitation you'd like to cancel, click Edit invitation.
4. To cancel the user's invitation to join your organization, click Cancel invitation.

**CIS Controls:**

| Version | Controls                              | IG1 | IG2 | IG3 |
|---------|---------------------------------------|-----|-----|-----|
| v8      | 6.1 Establish an Access Granting Process | ●   | ●   | ●   |
| v7      | 14.7 Enforce Access Control to Data through Automated Tools |     | ●   |     |

---

### 1.3.7 Ensure two administrators are set for each repository (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Ensure every repository has two users with administrative permissions.

**Rationale:**
Repository administrators have the highest permissions to said repository. These include the ability to add/remove collaborators, change branch protection policy, and convert to a publicly-accessible repository. Due to the liberal access granted to a repository administrator, it is highly recommended that only two contributors occupy this role.

**Impact:**
Removing administrative users from a repository would result in them losing high-level access to that repository.

**Audit:**
For every repository in use, verify there are two administrators by performing the following:
1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Access" section of the sidebar, click Collaborators & teams.
4. Under Manage access, verify that there are only 2 members with Admin permission.

**Remediation:**
For every repository in use, set two administrators by performing the following:
1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Access" section of the sidebar, click Collaborators & teams.
4. Under Manage access, find the team or person whose you'd like to revoke admin permissions, then select the Role drop-down and click a new role.

**CIS Controls:**

| Version | Controls                            | IG1 | IG2 | IG3 |
|---------|-------------------------------------|-----|-----|-----|
| v8      | 6.7 Centralize Access Control       | ●   | ●   |     |
| v7      | 14 Controlled Access Based on the Need to Know |     | ●   |     |

---

### 1.3.8 Ensure strict base permissions are set for repositories (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Base permissions define the permission level automatically granted to all organization members. Define strict base access permissions for all of the repositories in the organization, including new ones.

**Rationale:**
Defining strict base permissions is the best practice in every role-based access control (RBAC) system. If the base permission is high — for example, "write" permission — every member of the organization will have "write" permission to every repository in the organization. This will apply regardless of the specific permissions a user might need, which generally differ between organization repositories. The higher the permission, the higher the risk for incidents such as bad code commit or data breach. It is therefore recommended to set the base permissions to the strictest level possible.

**Impact:**
Users might not be able to access organization repositories or perform some acts as commits. These specific permissions should be granted individually for each user or team, as needed.

**Audit:**
Verify that strict base permissions are set for the organization repositories by doing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Base permissions", verify that it is set to "Read" or "None". If it does, you are compliant.

**Remediation:**
Set strict base permissions for the organization repositories with the next steps:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Access" section of the sidebar, click Member privileges.
4. Under "Base permissions", select the strictest level, such as "Read" or "None".
5. Click Save.

**CIS Controls:**

| Version | Controls                                          | IG1 | IG2 | IG3 |
|---------|---------------------------------------------------|-----|-----|-----|
| v8      | 6.7 Centralize Access Control                     | ●   | ●   |     |
| v7      | 14 Controlled Access Based on the Need to Know    |     | ●   |     |


---

### 1.3.9 Ensure an organization’s identity is confirmed with a “Verified” badge (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Confirm the domains an organization owns with a "Verified" badge.

**Rationale:**
Verifying the organization's domain gives developers assurance that a given domain is truly the official home for a public organization. Attackers can pretend to be an organization and steal information via a faked/spoof domain, therefore the use of a "Verified" badge instills more confidence and trust between developers and the open-source community.

**Audit:**
Only if you have an enterprise account, view the enterprise organization profile page and ensure it has a "Verified" badge in it.

**Remediation:**
Only if you have an enterprise account, verify the organization's domains and secure a "Verified" badge next to its name by performing the following:
1. In the top-right corner of GitHub.com, click your profile photo, then click Your enterprises.
2. In the list of enterprises, click the enterprise you want to view. Then in the enterprise account sidebar, click Settings.
3. Under "Settings", click Verified & approved domains.
4. Click Add a domain.
5. In the domain field, type the domain you'd like to verify, then click Add domain.
6. Follow the instructions under Add a DNS TXT record to create a DNS TXT record with your domain hosting service. Wait for your DNS configuration to change, which may take up to 72 hours. You can confirm your DNS configuration has changed by running the dig command on the command line, replacing ENTERPRISE-ACCOUNT with the name of your enterprise account, and example.com with the domain you'd like to verify. You should see your new TXT record listed in the command output.
   ```sh
   dig _github-challenge-ENTERPRISE-ACCOUNT.DOMAIN-NAME +nostats +nocomments +nocmd TXT
   ```
7. After confirming your TXT record is added to your DNS, follow steps one through three above to navigate to your enterprise account's approved and verified domains.
8. To the right of the domain that's pending verification, click the 3-dots, then click Continue verifying. Click Verify.
9. Optionally, after the "Verified" badge is visible on your organizations' profiles, delete the TXT entry from the DNS record at your domain hosting service.

**CIS Controls:**

| Version | Controls                                                           | IG1 | IG2 | IG3 |
|---------|--------------------------------------------------------------------|-----|-----|-----|
| v8      | 6.1 Establish an Access Granting Process                           | ●   | ●   | ●   |
| v8      | 14.7 Enforce Access Control to Data through Automated Tools        |     | ●   |     |
| v8      | 18.3 Verify and Test Control Effectiveness                         |     | ●   |     |

---

### 1.3.10 Ensure Source Code Management (SCM) email notifications are restricted to verified domains (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Restrict Source Code Management email notifications to approved or verified domains.

**Rationale:**
Restricting email notifications to approved or verified domains ensures that only members with approved email addresses receive Source Code Management notifications, which reduces the risk of information leakage to untrusted domains.

**Impact:**
Only members with approved email would be able to receive Source Code Management notifications.

**Audit:**
Only if you have an enterprise account, ensure Source Code Management email notifications are restricted to approved domains only by performing the following:
1. In the top-right corner of GitHub.com, click your profile photo, then click Your enterprises.
2. In the list of enterprises, click the enterprise you want to view. Then in the enterprise account sidebar, click Settings.
3. Under "Settings", click Verified & approved domains.
4. Under "Notification preferences", verify that Restrict email notifications to only approved or verified domains is selected.

**Remediation:**
Only if you have an enterprise account, restrict Source Code Management email notifications to approved domains only by performing the following:
1. In the top-right corner of GitHub.com, click your profile photo, then click Your enterprises.
2. In the list of enterprises, click the enterprise you want to view. Then in the enterprise account sidebar, click Settings.
3. Under "Settings", click Verified & approved domains.
4. Under "Notification preferences", select Restrict email notifications to only approved or verified domains.
5. Click Save.

**CIS Controls:**

| Version | Controls                                           | IG1 | IG2 | IG3 |
|---------|----------------------------------------------------|-----|-----|-----|
| v8      | 13.11 Tune Security Event Alerting Thresholds      | ●   |     |     |
| v7      | 5.2 Use Automated Tools to Inventory Data Flows    |     | ●   | ●   |
| v7      | 14.2 Implement Application Layer Security Controls |     |     | ●   |

---

### 1.3.11 Ensure an organization provides SSH certificates (Manual)

**Profile Applicability:**
- Level 2

**Description:**
As an organization, become an SSH Certificate Authority and provide SSH keys for accessing repositories.

**Rationale:**
SSH authentication is better in terms of security; key creation and distribution must be done in a secure manner. This can be accomplished by implementing SSH certificates, which are used to validate the server's identity. This ensures that only verified developers can access organization repositories, as their SSH key will be the only one signed by the CA certificate.

**Impact:**
Members with unverified keys will not be able to clone organization repositories. Signing, certification, and verification might also slow down the development process.

**Audit:**
Only if you have an enterprise account, verify that the enterprise organization has an SSH Certificate Authority server and provides an SSH certificate with which to sign keys by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Security" section of the sidebar, click Authentication security.
4. Verify that there's an SSH certificate authority listed there.

**Remediation:**
Only if you have an enterprise account, deploy an SSH Certificate Authority server and configure it to provide an SSH certificate with which to sign keys by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Security" section of the sidebar, click Authentication security.
4. To the right of "SSH Certificate Authorities", click New CA.
5. Under "Key," paste your public SSH key.
6. Click Add CA.
7. Click Save.

**CIS Controls:**

| Version | Controls                                                            | IG1 | IG2 | IG3 |
|---------|---------------------------------------------------------------------|-----|-----|-----|
| v8      | 12.5 Centralize Network Authentication, Authorization, and Auditing (AAA) | ●   | ●   |     |
| v8      | 12.7 Ensure Remote Devices Utilize a VPN and are Connecting to an Enterprise’s AAA Infrastructure | ●   | ●   |     |
| v7      | 1.8 Utilize Client Certificates to Authenticate Hardware Assets     |     | ●   |     |

---

### 1.3.12 Ensure Git access is limited based on IP addresses (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Limit Git access based on IP addresses by having an allowlist of IP addresses from which connection is possible.

**Rationale:**
Allowing access to Git repositories (source code) only from specific IP addresses adds yet another layer of restriction and reduces the risk of unauthorized connection to the organization's assets. This will prevent attackers from accessing Source Code Management (SCM), as they would first need to know the allowed IP addresses to gain access to them.

**Impact:**
Only members with allowlisted IP addresses will be able to access the organization's Git repositories.

**Audit:**
Only if you have an enterprise account, verify that access to the organization's Git repositories is restricted to allowlisted IP addresses by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Security" section of the sidebar, click Authentication security.
4. Under "IP allowlists", verify that the allowlist is configured correctly.

**Remediation:**
Only if you have an enterprise account, configure IP address restrictions to allowlist specific IP addresses for accessing Git repositories by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings.
3. In the "Security" section of the sidebar, click Authentication security.
4. Under "IP allowlists", click New IP allowlist entry.
5. Enter the IP address or range you want to allow, and then click Add.
6. Click Save.

**CIS Controls:**

| Version | Controls                                | IG1 | IG2 | IG3 |
|---------|-----------------------------------------|-----|-----|-----|
| v8      | 14.4 Segment Network Based on Sensitivity | ●   | ●   | ●   |
| v7      | 19.2 Operate and Manage Network Based on Sensitivity | ●   | ●   | ●   |

---

### 1.3.13 Ensure anomalous code behavior is tracked (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Track code anomalies.

**Rationale:**
Carefully analyze any code anomalies within the organization. For example, a code anomaly could be a push made outside of working hours. Such a code push has a higher likelihood of being the result of an attack, as most, if not all, members of the organization would likely be outside the office. Another example is an activity that exceeds the average activity of a particular user. Tracking and auditing such behaviors create additional layers of security and can aid in early detection of potential attacks.

**Audit:**
For every repository in use, ensure code anomalies relevant to the organization are promptly investigated.

**Remediation:**
For every repository in use, track and investigate anomalous code behavior and activity.

**CIS Controls:**

| Version | Controls                                                      | IG1 | IG2 | IG3 |
|---------|---------------------------------------------------------------|-----|-----|-----|
| v8      | 16.12 Implement Code-Level Security Checks                    |     | ●   |     |
| v7      | 18.7 Apply Static and Dynamic Code Analysis Tools             | ●   | ●   |     |

---
# 1.4 Third-Party
## 1.4.1 Ensure administrator approval is required for every installed application (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure an administrator approval is required when installing applications.

**Rationale:**
Applications are typically automated integrations that improve the workflow of an organization. They are written by third-party developers, and therefore should be validated before use in case they are malicious or not trustable. Because administrators are expected to be the most qualified and trusted members of the organization, they should review the applications being installed and decide whether they are both trusted and necessary.

**Impact:**
Applications will not be installed without administrator approval.

**Audit:**
Verify that applications are installed only after receiving administrator approval:
a. For GitHub Apps, you are compliant by default. That is because by default only organization owners and administrators can install them.
b. For OAuth Apps, perform the following:
  1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
  2. Next to the organization, click Settings.
  3. In the "Third-party Access" section of the sidebar, click OAuth application policy.
  4. Under "Third-party application access policy" verify that the policy status is Access restricted.

**Remediation:**
Require an administrator approval for every installed application:
a. For GitHub Apps, you are compliant by default. That is because by default only organization owners and administrators can install them.
b. For OAuth Apps, perform the following:
  1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
  2. Next to the organization, click Settings.
  3. In the "Third-party Access" section of the sidebar, click OAuth application policy.
  4. Under "Third-party application access policy", click Setup application access restrictions.
  5. After you review the information about third-party access restrictions, click Restrict third-party application access.

**Default Value:**
Maintainers are organization owners.

**CIS Controls:**

| Version | Controls                                     | IG1 | IG2 | IG3 |
| ------- | -------------------------------------------- | --- | --- | --- |
| v8      | 2.5 Allowlist Authorized Software             | ●   | ●   |     |
| v8      | 2.6 Allowlist Authorized Libraries            | ●   | ●   |     |
| v7      | 2.7 Utilize Application Whitelisting          |     | ●   |     |

## 1.4.2 Ensure stale applications are reviewed and inactive ones are removed (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure stale (inactive) applications are reviewed and removed if no longer in use.

**Rationale:**
Applications that have been inactive for a long period of time are enlarging the surface of attack for data leaks. They are more likely to be improperly managed, and could possibly be accessed by third-party developers as a tool for collecting internal data of the organization or repository in which they are installed. It is important to remove these inactive applications as soon as possible.

**Audit:**
Verify that all the applications in the organization are actively used, and remove those that are no longer in use.

**Remediation:**
Review all stale applications and periodically remove them.

**CIS Controls:**

| Version | Controls                                           | IG1 | IG2 | IG3 |
| ------- | -------------------------------------------------- | --- | --- | --- |
| v8      | 2.2 Ensure Authorized Software is Currently Supported | ●   | ●   | ●   |
| v8      | 2.4 Utilize Automated Software Inventory Tools     | ●   | ●   |     |
| v7      | 13.2 Remove Sensitive Data or Systems Not Regularly Accessed by Organization | ●   | ●   | ●   |

## 1.4.3 Ensure the access granted to each installed application is limited to the least privilege needed (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Ensure installed application permissions are limited to the lowest privilege level required.

**Rationale:**
Applications are typically automated integrations that can improve the workflow of an organization. They are written by third-party developers, and therefore should be reviewed carefully before use. It is recommended to use the "least privilege" principle, granting applications the lowest level of permissions required. This may prevent harm from a potentially malicious application with unnecessarily high-level permissions leaking data or modifying source code.

**Audit:**
Verify that each installed application has the least privilege needed:
a. For GitHub Apps, perform the following:
  1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
  2. Next to the organization, click Settings.
  3. In the "Integrations" section of the sidebar, click GitHub Apps.
  4. Next to every GitHub App, click Configure.
  5. Review the GitHub App's permissions and repository access. Verify that the App permissions are the least possible and that it can access only necessary repositories.

**Remediation:**
Grant permissions to applications by the "least privilege" principle, meaning the lowest possible permission necessary:
a. For GitHub Apps, perform the following:
  1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
  2. Next to the organization, click Settings.
  3. In the "Integrations" section of the sidebar, click GitHub Apps.
  4. Next to every GitHub App, click Configure.
  5. Review the GitHub App's permissions and repository access. Edit the permissions granted to the least possible. For example, restrict the number of repositories the App can access.
  6. Click Save.

**CIS Controls:**

| Version | Controls                                                     | IG1 | IG2 | IG3 |
| ------- | ------------------------------------------------------------ | --- | --- | --- |
| v8      | 6.8 Define and Maintain Role-Based Access Control            |     | ●   |     |
| v7      | 14.6 Protect Information through Access Control Lists        | ●   | ●   | ●   |

## 1.4.4 Ensure only secured webhooks are used (Manual)

**Profile Applicability:**
- Level 1

**Description:**
Use only secured webhooks in the source code management platform.

**Rationale:**
A webhook is an event listener, attached to critical and sensitive parts of the software delivery process. It is triggered by a list of events (such as a new code being committed), and when triggered, the webhook sends out a notification with some payload to specific internet endpoints. Since the payload of the webhook contains sensitive organization data, it's important all webhooks are directed to an endpoint (URL) protected by SSL verification (HTTPS). This helps ensure that the data sent is delivered securely without any man-in-the-middle, who could easily access and even alter the payload of the request.

**Impact:**
Perform the following to ensure all webhooks used are secured (HTTPS):
1. Navigate to your organization or repository and select Settings.
2. Select Webhooks on the side menu.
3. Verify that each webhook URL starts with 'https'.

**Audit:**
Perform the following to secure all webhooks used (over HTTPS):
1. Navigate to your organization or repository and select Settings.
2. Select Webhooks on the side menu.
3. Ensure all webhooks start with 'https'.

**Remediation:**
Perform the following to secure all webhooks used (over HTTPS):
1. Navigate to your organization or repository and select Settings.
2. Select Webhooks on the side menu.
3. Find the webhooks that start with 'http' and not 'https'.
4. Ensure the endpoint (URL) of the webhook listens to a secured port (443) and uses a certificate.
5. Click Edit.
6. Change the payload URL to https and ensure Enable SSL verification is checked.
7. Click Update webhook.

**CIS Controls:**

| Version | Controls                                          | IG1 | IG2 | IG3 |
| ------- | ------------------------------------------------- | --- | --- | --- |
| v8      | 2.7 Allowlist Authorized Scripts                  |     | ●   |     |
| v7      | 2.9 Implement Application Whitelisting of Scripts |     | ●   |     |

---

# 1.5 Code Risks


## 1.5.1 Ensure scanners are in place to identify and prevent sensitive data in code (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Detect and prevent sensitive data in code, such as confidential ID numbers, passwords, etc.

**Rationale:**
Having sensitive data in the source code makes it easier for attackers to maliciously use such information. In order to avoid this, designate scanners to identify and prevent the existence of sensitive data in the code.

**Audit:**
For every repository in use, verify that scanners are set to identify and prevent the existence of sensitive data in code by performing the following (enterprise only):
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Security" section of the sidebar, click Code security and analysis.
4. Scroll down to the bottom of the page. If you see a Disable button, it means that secret scanning is already enabled for the repository.

**Remediation:**
For every repository in use, designate scanners to identify and prevent sensitive data in code by performing the following (enterprise only):
1. On GitHub.com, navigate to the main page of the repository.
2. Under your repository name, click Settings.
3. In the "Security" section of the sidebar, click Code security and analysis.
4. Scroll down to the bottom of the page and click Enable for secret scanning.

**Additional Information:**
By January 2023, this feature is supposed to be open to all plans. Until then it is only for enterprise users.

**CIS Controls:**

| Version | Controls                                                     | IG1 | IG2 | IG3 |
| ------- | ------------------------------------------------------------ | --- | --- | --- |
| v8      | 7.5 Perform Automated Vulnerability Scans of Internal Enterprise Assets | ●   | ●   |     |
| v8      | 7.6 Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets | ●   | ●   |     |
| v7      | 3.1 Run Automated Vulnerability Scanning Tools               | ●   | ●   |     |

---
## 1.5.2 Ensure scanners are in place to secure Continuous Integration (CI) pipeline instructions (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Detect and prevent misconfigurations and insecure instructions in CI pipelines.

**Rationale:**
Detecting and fixing misconfigurations or insecure instructions in CI pipelines decreases the risk for a successful attack through or on the CI pipeline. The more secure the pipeline, the less risk there is for potential exposure of sensitive data, a deployment being compromised, or external access mistakenly being granted to the CI infrastructure or the source code.

**Audit:**
Verify that a CI instructions scanning tool is set to identify and prevent misconfigurations and insecure instructions and that it scans all CI pipelines.

**Remediation:**
Set a CI instructions scanning tool to identify and prevent misconfigurations and insecure instructions and scans all CI pipelines.

**CIS Controls:**

| Version | Controls                                                     | IG1 | IG2 | IG3 |
| ------- | ------------------------------------------------------------ | --- | --- | --- |
| v8      | 7.5 Perform Automated Vulnerability Scans of Internal Enterprise Assets | ●   | ●   |     |
| v8      | 7.6 Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets | ●   | ●   |     |
| v7      | 3.1 Run Automated Vulnerability Scanning Tools               | ●   | ●   |     |

---
## 1.5.3 Ensure scanners are in place to secure Infrastructure as Code (IaC) instructions (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Detect and prevent misconfigurations or insecure instructions in Infrastructure as Code (IaC) files, such as Terraform files.

**Rationale:**
Detecting and fixing misconfigurations and/or insecure instructions in IaC (Infrastructure as Code) files decreases the risk for data leak or data theft. It is important to secure IaC instructions in order to prevent further problems of deployment, exposed assets, or improper configurations, which can ultimately lead to easier ways to attack and steal organization data.

**Audit:**
For every repository that holds IaC instructions files, verify that a scanning tool is set to identify and prevent misconfigurations and insecure instructions.

**Remediation:**
For every repository that holds IaC instructions files, set a scanning tool to identify and prevent misconfigurations and insecure instructions.

**CIS Controls:**

| Version | Controls                                                     | IG1 | IG2 | IG3 |
| ------- | ------------------------------------------------------------ | --- | --- | --- |
| v8      | 7.5 Perform Automated Vulnerability Scans of Internal Enterprise Assets | ●   | ●   |     |
| v8      | 7.6 Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets | ●   | ●   |     |
| v7      | 3.1 Run Automated Vulnerability Scanning Tools               | ●   | ●   |     |

---
## 1.5.4 Ensure scanners are in place for code vulnerabilities (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Detect and prevent known open-source vulnerabilities in the code.

**Rationale:**
Open-source code blocks are used a lot in developed software. This has its own advantages, but it also has risks. Because the code is open for everyone, it means that attackers can publish or add malicious code to these open-source code blocks, or use their knowledge to find vulnerabilities in an existing code. Detecting and fixing such code vulnerabilities, by SCA (Software Composition Analysis) prevents insecure flaws from reaching production. It gives another opportunity for developers to secure the source code before it is deployed in production, where it is far more exposed and vulnerable to attacks.

**Audit:**
For every repository that is in use, verify that a scanning tool is set to identify and prevent code vulnerabilities by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under the repository name, click Security.
3. Verify that "Code scanning alerts" is Enabled or that there is a workflow that scans your code.

**Remediation:**
For every repository that is in use, set a scanning tool to identify and prevent code vulnerabilities by performing the following:
1. On GitHub.com, navigate to the main page of the repository.
2. Under the repository name, click Security.
3. To the right of "Code scanning alerts", click Set up code scanning.
4. Under "Get started with code scanning", click Set up this workflow on a workflow of your choice.
5. To customize how code scanning scans your code, edit the workflow.
6. Use the Start commit drop-down and type a commit message.
7. Choose whether you'd like to commit directly to the default branch or create a new branch and start a pull request.
8. Click Commit new file or Propose new file.

**Additional Information:**
All public repositories in all plans can use code scanning in GitHub. In private repositories, only GitHub Enterprise can use code scanning.

**CIS Controls:**

| Version | Controls                                                     | IG1 | IG2 | IG3 |
| ------- | ------------------------------------------------------------ | --- | --- | --- |
| v8      | 16.12 Implement Code-Level Security Checks                   | ●   |     |     |
| v8      | 16.13 Conduct Application Penetration Testing                | ●   |     |     |
| v7      | 20.6 Use Vulnerability Scanning and Penetration Testing Tools in Concert | ●   | ●   |     |

---
## 1.5.5 Ensure scanners are in place for open-source vulnerabilities in used packages (Manual)

**Profile Applicability:**
- Level 2

**Description:**
Detect, prevent, and monitor known open-source vulnerabilities in packages that are being used.

**Rationale:**
Open-source vulnerabilities might exist before one starts to use a package, but they are also discovered over time. New attacks and vulnerabilities are announced frequently. It is important to keep track of these and to monitor whether the dependencies used are affected by the recent vulnerability. Detecting and fixing those packages' vulnerabilities decreases the attack surface within deployed and running applications that use such packages. It prevents security flaws from reaching the production environment which could eventually lead to a security breach.

**Audit:**
Verify that scanners are set to monitor, identify, and prevent open-source vulnerabilities in packages by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings. In the "Security" section of the sidebar, click Code security and analysis.
3. Verify that Dependabot alerts is enabled and that Enable by default for new repositories is checked.

It is also recommended to verify that you're using another additional solution for package scanning because GitHub doesn't always recognize the vulnerabilities.

**Remediation:**
Set scanners that will monitor, identify, and prevent open-source vulnerabilities in packages by performing the following:
1. In the top right corner of GitHub.com, click your profile photo, then click Your organizations.
2. Next to the organization, click Settings. In the "Security" section of the sidebar, click Code security and analysis.
3. Under "Code security and analysis", to the right of Dependabot alerts, click Disable all or Enable all.
4. Check the Enable by default for new repositories option and then click Enable Dependabot alerts.

It is also recommended to use another additional solution for package scanning because GitHub doesn't always recognize the vulnerabilities.

**CIS Controls:**

| Version | Controls                                             | IG1 | IG2 | IG3 |
| ------- | ---------------------------------------------------- | --- | --- | --- |
| v8      | 7.5 Perform Automated Vulnerability Scans of Internal Enterprise Assets | ●   | ●   |     |
| v8      | 7.6 Perform Automated Vulnerability Scans of Externally-Exposed Enterprise Assets | ●   | ●   |     |
| v7      | 3.1 Run Automated Vulnerability Scanning Tools        | ●   | ●   |     |



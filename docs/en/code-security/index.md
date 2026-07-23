---
source_path: "/en/code-security"
title: "Security and code quality documentation"
intro: "Build security and code quality into your GitHub workflow with integrated tooling."
product: "Security and code quality"
document_type: "product"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
---

# Security and code quality documentation

Build security and code quality into your GitHub workflow with integrated tooling.

## Recommended

* [Quickstart for securing your repository](/en/code-security/getting-started/quickstart-for-securing-your-repository)

  Manage access to your code. Find and fix vulnerable code and dependencies automatically.

* [GitHub security features](/en/code-security/getting-started/github-security-features)

  An overview of GitHub's security features.

* [Planning a trial of GitHub Advanced Security](/en/code-security/tutorials/trialing-github-advanced-security/planning-a-trial-of-ghas)

  Learn how to prepare for a successful trial of Advanced Security.

* [Secret scanning](/en/code-security/concepts/secret-security/secret-scanning)

  Prevent fraudulent use of your secrets by automatically detecting exposed credentials before they can be exploited.

* [Code scanning](/en/code-security/concepts/code-scanning/code-scanning)

  You can use code scanning to find security vulnerabilities and errors in the code for your project on GitHub.

* [Dependabot quickstart guide](/en/code-security/tutorials/secure-your-dependencies/dependabot-quickstart)

  Find and fix vulnerable dependencies you rely on with Dependabot.

* [GitHub Code Quality](/en/code-security/concepts/code-quality/code-quality)

  GitHub Code Quality catches quality issues before merge, delivers one-click Copilot-powered fixes inline, and checks your code coverage.

* [Best practices for preventing data leaks in your organization](/en/code-security/tutorials/secure-your-organization/prevent-data-leaks)

  Learn guidance and recommendations to help you avoid private or sensitive data present in your organization from being exposed.

* [Best practices for maintaining dependencies](/en/code-security/concepts/supply-chain-security/best-practices-for-maintaining-dependencies)

  Guidance and recommendations for maintaining the dependencies you use, including GitHub's security products that can help.

## Articles

* [GitHub security features](/en/code-security/getting-started/github-security-features)

  An overview of GitHub's security features.

* [Quickstart for securing your repository](/en/code-security/getting-started/quickstart-for-securing-your-repository)

  Manage access to your code. Find and fix vulnerable code and dependencies automatically.

* [Secret leakage risks](/en/code-security/concepts/secret-security/secret-leakage-risks)

  Secrets like API keys, passwords, and tokens committed to repositories can be exploited by unauthorized users, creating security, compliance, and financial risk to your organization.

* [Secret scanning](/en/code-security/concepts/secret-security/secret-scanning)

  Prevent fraudulent use of your secrets by automatically detecting exposed credentials before they can be exploited.

* [Public monitoring for secret scanning](/en/code-security/concepts/secret-security/public-monitoring)

  Public monitoring detects credentials leaked by your enterprise members in public repositories across GitHub, giving you visibility into secret exposure beyond your enterprise's boundaries.

* [Push protection](/en/code-security/concepts/secret-security/push-protection)

  Secure your secrets by stopping them from ever reaching your repository with push protection.

* [Secret security with GitHub](/en/code-security/concepts/secret-security/secret-security-with-github)

  Learn how GitHub's security tools can help you identify, remediate, and prevent secret leaks.

* [About secret scanning alerts](/en/code-security/concepts/secret-security/about-alerts)

  Learn about the different types of secret scanning alerts.

* [Custom patterns](/en/code-security/concepts/secret-security/custom-patterns)

  Detect secret types specific to your organization with custom patterns.

* [Validity checks](/en/code-security/concepts/secret-security/validity-checks)

  Validity checks and extended metadata checks help you prioritize remediation of exposed credentials that pose immediate security risks.

* [Delegated bypass for push protection](/en/code-security/concepts/secret-security/delegated-bypass)

  Maintain your secret security while unblocking trusted actors with delegated bypass for push protection.

* [Bypass requests for push protection](/en/code-security/concepts/secret-security/bypass-requests)

  Learn how bypass requests work when push protection blocks commits containing secrets.

* [Secret scanning for partners](/en/code-security/concepts/secret-security/secret-scanning-for-partners)

  When secret scanning detects authentication details for a service provider in a public repository on GitHub, an alert is sent directly to the provider. This allows service providers who are GitHub partners to promptly take action to secure their systems.

* [GitHub secret types](/en/code-security/concepts/secret-security/secret-types)

  Learn about the different types of secrets used by GitHub.

* [Secret scanning push protection metrics](/en/code-security/concepts/secret-security/push-protection-metrics)

  Understand push protection's performance across your organizations.

* [Push protection from the command line](/en/code-security/concepts/secret-security/command-line-push-protection)

  Understand how GitHub uses push protection to prevent secret leaks from the command line.

* [Working with push protection and the GitHub MCP server](/en/code-security/concepts/secret-security/push-protection-and-the-github-mcp-server)

  Learn how you are protected from leaking secrets during interactions with the GitHub MCP server, and how to bypass a push protection block if you need to.

* [Working with push protection from the REST API](/en/code-security/concepts/secret-security/push-protection-from-the-rest-api)

  Learn your options for unblocking your push to GitHub using the REST API if secret scanning detects a secret in the content of your API request.

* [Code scanning](/en/code-security/concepts/code-scanning/code-scanning)

  You can use code scanning to find security vulnerabilities and errors in the code for your project on GitHub.

* [Code scanning alerts](/en/code-security/concepts/code-scanning/code-scanning-alerts)

  Learn about the different types of code scanning alerts and the information that helps you understand the problem each alert highlights.

* [Code security risk assessment](/en/code-security/concepts/code-scanning/risk-assessment)

  Generate a free code security risk assessment to understand your organization's exposure to vulnerabilities.

* [About autofix for code scanning](/en/code-security/concepts/code-scanning/autofix-for-code-scanning)

  Autofix provides targeted recommendations to help you fix code scanning alerts and avoid introducing new security vulnerabilities.

* [AI-powered security detections in pull requests](/en/code-security/concepts/code-scanning/ai-powered-security-detections)

  AI-powered security detections use an AI-based scanning engine to find security vulnerabilities in pull requests for languages and frameworks not covered by CodeQL.

* [About setup types for code scanning](/en/code-security/concepts/code-scanning/setup-types)

  Depending on your needs, GitHub offers a default or advanced setup for code scanning.

* [Integration with code scanning](/en/code-security/concepts/code-scanning/integration-with-code-scanning)

  You can perform code scanning externally and then display the results in GitHub, or configure webhooks that listen to code scanning activity in your repository.

* [About SARIF files for code scanning](/en/code-security/concepts/code-scanning/sarif-files)

  SARIF files convert third-party analyses into alerts on GitHub.

* [Code scanning alert tracking using issues](/en/code-security/concepts/code-scanning/alert-tracking-with-issues)

  Connect security findings to your team's workflow by linking code scanning alerts to issues for tracking and collaboration.

* [Code scanning merge protection](/en/code-security/concepts/code-scanning/merge-protection)

  Code scanning rules prevent pull requests with potential vulnerabilities from being merged.

* [Multi-repository variant analysis](/en/code-security/concepts/code-scanning/multi-repository-variant-analysis)

  MRVA lets you test a query in Visual Studio Code by running it against a large number of repositories.

* [Code scanning with CodeQL](/en/code-security/concepts/code-scanning/codeql/codeql-code-scanning)

  You can use CodeQL to identify vulnerabilities and errors in your code. The results are shown as code scanning alerts in GitHub.

* [CodeQL code scanning for compiled languages](/en/code-security/concepts/code-scanning/codeql/codeql-for-compiled-languages)

  Understand how CodeQL analyzes compiled languages, the build options available, and learn how you can customize the database generation process if you need to.

* [CodeQL query suites](/en/code-security/concepts/code-scanning/codeql/codeql-query-suites)

  You can choose from different built-in CodeQL query suites to use in your CodeQL code scanning setup.

* [Custom CodeQL queries](/en/code-security/concepts/code-scanning/codeql/custom-queries)

  Custom queries extend CodeQL's built-in security analysis to detect vulnerabilities and enforce coding standards specific to your codebase.

* [CodeQL CLI](/en/code-security/concepts/code-scanning/codeql/codeql-cli)

  You can use the CodeQL CLI to run CodeQL processes locally on software projects or to generate code scanning results for upload to GitHub.

* [CodeQL for VS Code](/en/code-security/concepts/code-scanning/codeql/codeql-for-vs-code)

  You can write, run, and test CodeQL queries inside Visual Studio Code with the CodeQL extension.

* [CodeQL workspaces](/en/code-security/concepts/code-scanning/codeql/codeql-workspaces)

  CodeQL workspaces let you develop and maintain multiple related CodeQL packs together, resolving dependencies between them directly from source.

* [Query reference files](/en/code-security/concepts/code-scanning/codeql/query-reference-files)

  You can use query reference files to define the location of a query you want to run in tests.

* [CodeQL query packs](/en/code-security/concepts/code-scanning/codeql/query-packs)

  You can choose from different built-in CodeQL query suites to use in your CodeQL code scanning setup.

* [About the tool status page](/en/code-security/concepts/code-scanning/tool-status-page)

  The tool status page provides visibility into the health and performance of code scanning tools in your repository.

* [CodeQL pull request alert metrics](/en/code-security/concepts/code-scanning/pull-request-alert-metrics)

  Understand CodeQL's performance in pull requests across your organizations.

* [Repository properties for code scanning](/en/code-security/concepts/code-scanning/repository-properties)

  You can use repository properties to adjust code scanning to suit your needs.

* [Supply chain security](/en/code-security/concepts/supply-chain-security/supply-chain-security)

  GitHub helps you secure your supply chain, from understanding the dependencies in your environment, to knowing about vulnerabilities in those dependencies, and patching them.

* [About open source license compliance](/en/code-security/concepts/supply-chain-security/open-source-license-compliance)

  Define and enforce license policy for dependencies in your repositories with open source license compliance.

* [Best practices for maintaining dependencies](/en/code-security/concepts/supply-chain-security/best-practices-for-maintaining-dependencies)

  Guidance and recommendations for maintaining the dependencies you use, including GitHub's security products that can help.

* [Dependency graph](/en/code-security/concepts/supply-chain-security/dependency-graph)

  You can use the dependency graph to identify all your project's dependencies. The dependency graph supports a range of popular package ecosystems.

* [How the dependency graph recognizes dependencies](/en/code-security/concepts/supply-chain-security/dependency-graph-data)

  The dependency graph automatically analyzes manifest files. You can submit data for dependencies that cannot be detected automatically.

* [Dependency review](/en/code-security/concepts/supply-chain-security/dependency-review)

  Dependency review lets you catch insecure dependencies before you introduce them to your environment, and provides information on license, dependents, and age of dependencies.

* [Dependabot alerts](/en/code-security/concepts/supply-chain-security/dependabot-alerts)

  Dependabot alerts help you find and fix vulnerable dependencies before they become security risks.

* [Dependabot malware alerts](/en/code-security/concepts/supply-chain-security/malware-alerts)

  Dependabot malware alerts help you identify malware in your dependencies to protect your project and its users.

* [Metrics for Dependabot alerts](/en/code-security/concepts/supply-chain-security/dependabot-alert-metrics)

  Use metrics to track and prioritize Dependabot alerts across your organization.

* [Dependabot security updates](/en/code-security/concepts/supply-chain-security/dependabot-security-updates)

  Dependabot can fix vulnerable dependencies for you by raising pull requests with security updates.

* [Dependabot version updates](/en/code-security/concepts/supply-chain-security/dependabot-version-updates)

  You can use Dependabot to keep the packages you use updated to the latest versions.

* [Dependabot pull requests](/en/code-security/concepts/supply-chain-security/dependabot-pull-requests)

  Understand the frequency and customization options of pull requests for version and security updates.

* [Multi-ecosystem updates](/en/code-security/concepts/supply-chain-security/multi-ecosystem-updates)

  Multi-ecosystem updates combine dependency updates across multiple package ecosystems into a single pull request, reducing review overhead and simplifying your update workflow.

* [About the dependabot.yml file](/en/code-security/concepts/supply-chain-security/about-the-dependabot-yml-file)

  The `dependabot.yml` controls automated dependency updates in your repository.

* [Automatic Dependabot access to GitHub-hosted registries](/en/code-security/concepts/supply-chain-security/automatic-dependabot-access-to-github-registries)

  Keep your private dependencies up to date reliably by granting Dependabot automatic access to GitHub Packages and Container registry, so you never need to create or rotate credentials for these registries.

* [Dependabot auto-triage rules](/en/code-security/concepts/supply-chain-security/dependabot-auto-triage-rules)

  Control how Dependabot handles security alerts, including filtering, ignoring, snoozing, or triggering security updates.

* [Dependabot on GitHub Actions runners](/en/code-security/concepts/supply-chain-security/dependabot-on-actions)

  GitHub automatically runs the jobs that generate Dependabot pull requests on GitHub Actions if you have GitHub Actions enabled for the repository. When Dependabot is enabled, these jobs will run by bypassing Actions policy checks and disablement at the repository or organization level.

* [Dependabot job logs](/en/code-security/concepts/supply-chain-security/dependabot-job-logs)

  GitHub logs every update job run by Dependabot, giving you visibility into version updates, security patches, and automated rebases across your dependencies.

* [Immutable releases](/en/code-security/concepts/supply-chain-security/immutable-releases)

  Learn about immutable releases and how they can help you maintain the integrity of your software supply chain.

* [About linked artifacts](/en/code-security/concepts/supply-chain-security/linked-artifacts)

  The linked artifacts page helps you audit and prioritize your organization's builds on GitHub, regardless of where the artifacts are stored.

* [GitHub Code Quality](/en/code-security/concepts/code-quality/code-quality)

  GitHub Code Quality catches quality issues before merge, delivers one-click Copilot-powered fixes inline, and checks your code coverage.

* [Code Quality enablement across organizations and enterprises](/en/code-security/concepts/code-quality/enablement-at-scale)

  GitHub Code Quality can cover one repository or thousands from a single control point, giving every team the same quality baseline and giving you the guardrails to keep it there.

* [GitHub Advisory database](/en/code-security/concepts/vulnerability-reporting-and-management/github-advisory-database)

  Research known security vulnerabilities and malware in open source packages, so you can understand and remediate the risks in your dependencies.

* [Innersource advisories](/en/code-security/concepts/vulnerability-reporting-and-management/innersource-advisories)

  Enterprises can alert their internal repositories to vulnerabilities and ship automated fixes with Dependabot, using advisories that stay private to a single enterprise.

* [Repository security advisories](/en/code-security/concepts/vulnerability-reporting-and-management/repository-security-advisories)

  You can use repository security advisories to privately discuss, fix, and publish information about security vulnerabilities in your public repository.

* [Global security advisories](/en/code-security/concepts/vulnerability-reporting-and-management/global-security-advisories)

  Global security advisories are CVEs and GitHub-originated advisories affecting the open source world, located in the GitHub Advisory Database.

* [Coordinated disclosure of security vulnerabilities](/en/code-security/concepts/vulnerability-reporting-and-management/coordinated-disclosure)

  Vulnerability disclosure is a coordinated effort between security reporters and repository maintainers.

* [Exposure to vulnerabilities in your code and in dependencies](/en/code-security/concepts/vulnerability-reporting-and-management/vulnerability-exposure)

  Understand how vulnerabilities in your own code and in third-party dependencies contribute to your organization's overall security exposure, and how to measure and reduce that risk.

* [Best practices for selecting pilot repositories](/en/code-security/concepts/security-at-scale/select-pilot-repositories)

  The right pilot repositories demonstrate value quickly and prepare your organization for broader enablement of GitHub Secret Protection.

* [Enabling security features at scale](/en/code-security/concepts/security-at-scale/organization-security)

  You can quickly secure your organization at scale with security configurations and global settings.

* [Security overview](/en/code-security/concepts/security-at-scale/security-overview)

  You can gain insights into the overall security landscape of your organization or enterprise and identify repositories that require intervention using security overview.

* [About security campaigns](/en/code-security/concepts/security-at-scale/about-security-campaigns)

  You can fix security alerts at scale by creating security campaigns and collaborating with developers to burn down your security backlog.

* [Auditing security alerts](/en/code-security/concepts/security-at-scale/audit-security-alerts)

  GitHub provides a variety of tools you can use to audit and monitor actions taken in response to security alerts.

* [Delegated alert dismissal](/en/code-security/concepts/security-at-scale/delegated-alert-dismissal)

  Increase your governance over security alerts with delegated alert dismissal.

* [Supply chain security for your enterprise](/en/supply-chain-security)

  You can enable enterprise-level features that help your developers understand and update the dependencies their code relies on.

* [Establish complete coverage](/en/establish-complete-coverage)

  Learn how to establish comprehensive, enterprise-wide security coverage by enabling GitHub Advanced Security, applying recommended or custom security configurations, and configuring additional secret scanning settings across your enterprise.

* [Editing a custom security configuration](/en/edit-custom-configuration)

  Change the enablement settings in your custom security configuration to better meet the security needs of your repositories.

* [Deleting a custom security configuration](/en/delete-custom-configuration)

  You can delete unnecessary custom security configurations in your enterprise.

* [Enabling public monitoring for your enterprise](/en/code-security/how-tos/secure-at-scale/configure-enterprise-security/manage-your-coverage/enabling-public-monitoring-for-your-enterprise)

  Start detecting secrets your enterprise members leak in public repositories outside your enterprise's boundaries.

* [Enabling the dependency graph for your enterprise](/en/enable-dependency-graph)

  You can allow users to identify their projects' dependencies by enabling the dependency graph.

* [Allowing use of GitHub Code Quality in your enterprise](/en/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/allow-github-code-quality-in-enterprise)

  Control Code Quality enablement for your repositories by defining policies.

* [](/en/configuring-code-scanning-for-your-appliance)

  You can enable, configure, and disable code scanning for your enterprise. Code scanning allows users to scan code for vulnerabilities and errors.

* [Configuring dependency review for your appliance](/en/configure-dependency-review)

  To help users understand dependency changes when reviewing pull requests, you can enable, configure, and disable dependency review for GitHub Enterprise Server.

* [Configuring secret scanning for your appliance](/en/configure-secret-scanning)

  You can enable, configure, and disable secret scanning for GitHub Enterprise Server. Secret scanning allows users to scan code for accidentally committed secrets.

* [Viewing the vulnerability data for your enterprise](/en/view-vulnerability-data)

  You can view vulnerability data from the GitHub Advisory Database on GitHub Enterprise Server.

* [Configuring Dependabot to work with limited internet access](/en/configure-limited-internet-access)

  You can configure Dependabot to generate pull requests for version and security updates using private registries when GitHub Enterprise Server has limited, or no, internet access.

* [Setting up Dependabot to run on github-hosted action runners using the Azure Private Network](/en/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/setting-dependabot-to-run-on-github-hosted-runners-using-vnet)

  You can configure an Azure Virtual Network (VNET) to run Dependabot on GitHub-hosted runners.

* [Creating a custom security configuration](/en/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/create-custom-configuration)

  Build a custom security configuration to meet the specific security needs of repositories in your organization.

* [Applying a custom security configuration](/en/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/apply-custom-configuration)

  You can apply your custom security configuration to repositories in your organization to meet the specific security needs of those repositories.

* [Configuring global security settings for your organization](/en/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/configure-global-settings)

  Customize Advanced Security features for your organization by defining global settings that ensure consistent security standards and safeguard all your repositories.

* [Editing a custom security configuration](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-your-coverage/edit-custom-configuration)

  Meet the security needs of your repositories by editing your custom security configuration.

* [Filtering repositories in your organization using the repository table](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-your-coverage/filter-repositories)

  You can filter the repository table for your organization to better manage the security settings of specific repositories.

* [Detaching repositories from their security configurations](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-your-coverage/detach-security-configuration)

  Go back to managing a repository's security settings on an individual basis.

* [Deleting a custom security configuration](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-your-coverage/delete-custom-configuration)

  You can delete unnecessary custom security configurations in your organization.

* [Running the secret risk assessment for your organization](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/assess-your-secret-risk)

  Determine your organization's exposure to leaked secrets by generating a secret risk assessment report.

* [Running the code security risk assessment for your organization](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/assess-your-vulnerability-risk)

  Determine your organization's exposure to vulnerabilities by generating a code security risk assessment report.

* [Viewing your security risk assessment reports](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/viewing-your-security-risk-assessment-reports)

  Understand your organization's exposure to leaked secrets and code vulnerabilities by viewing your most recent security risk assessment reports.

* [Estimating the price of Secret Protection](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/estimate-price)

  Learn how to use the pricing calculator to estimate the monthly cost of GitHub Secret Protection for your repositories.

* [Pricing and enabling GitHub Secret Protection](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/protect-your-secrets)

  Secure your organization's secrets within your budget by enabling GitHub Secret Protection.

* [Configuring default setup for code scanning at scale](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/code-scanning-at-scale)

  You can quickly configure code scanning for repositories across your organization using default setup.

* [Configuring advanced setup for code scanning with CodeQL at scale](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/configuring-advanced-setup-for-code-scanning-with-codeql-at-scale)

  Establish a highly customizable code scanning setup at scale with a script.

* [Enforcing dependency review across an organization](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/enforce-dependency-review)

  Dependency review lets you catch insecure dependencies before you introduce them to your environment. You can enforce the use of the dependency review action across your organization.

* [Giving security features access to private registries](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries)

  If your organization uses private registries, you can improve the results of code scanning analysis and enable Dependabot to maintain more dependencies by setting up access to these registries.

* [Managing your paid use of Advanced Security](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/managing-your-github-advanced-security-license-usage)

  Control the costs of GitHub Secret Protection and GitHub Code Security in your organization.

* [Enabling secret scanning for your repository](/en/code-security/how-tos/secure-your-secrets/detect-secret-leaks/enable-secret-scanning)

  You can configure how GitHub scans your repositories for leaked secrets and generates alerts.

* [Enabling secret scanning for generic patterns](/en/code-security/how-tos/secure-your-secrets/detect-secret-leaks/enabling-secret-scanning-for-generic-patterns)

  You can enable secret scanning to detect additional potential secrets at the repository and organization levels.

* [Enabling generic secret detection for AI-detected secrets](/en/code-security/how-tos/secure-your-secrets/detect-secret-leaks/enabling-secret-scanning-for-ai-detected-secrets)

  You can enable generic secret detection for your repository or organization. Alerts for generic secrets, such as passwords, are displayed in a separate list on the secret scanning alerts page.

* [Defining custom patterns for secret scanning](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/define-custom-patterns)

  Protect your unique secret types by defining custom patterns with regular expressions.

* [Generating regular expressions for custom patterns with AI](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/generating-regular-expressions-for-custom-patterns-with-ai)

  You can use the AI-powered regular expression generator to write regular expressions for custom patterns. The generator uses an AI model to generate expressions that match your input, and optionally example strings.

* [Managing custom patterns](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/manage-custom-patterns)

  You can view, edit, and remove custom patterns, as well as enable push protection for custom patterns.

* [Excluding folders and files from secret scanning](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/exclude-folders-and-files)

  You can customize secret scanning to automatically close alerts for secrets found in specific directories or files by configuring a `secret_scanning.yml` file in your repository.

* [Enabling validity checks for your repository](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/enable-validity-checks)

  Enabling validity checks on your repository helps you prioritize the remediation of alerts as it tells you if a secret is active or inactive.

* [Enabling extended metadata checks for your repository](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/enable-metadata-checks)

  Learn how to enable extended metadata checks for detected secrets so alerts detected by secret scanning include additional information that help you assess and remediate leaks faster.

* [Enabling push protection for your repository](/en/code-security/how-tos/secure-your-secrets/prevent-future-leaks/enable-push-protection)

  With push protection, secret scanning blocks contributors from pushing secrets to a repository and generates an alert whenever a contributor bypasses the block.

* [Managing push protection for users](/en/code-security/how-tos/secure-your-secrets/prevent-future-leaks/manage-user-push-protection)

  You can control GitHub's ability to block your pushes that may contain secrets.

* [Working with push protection from the command line](/en/code-security/how-tos/secure-your-secrets/work-with-leak-prevention/push-protection-on-the-command-line)

  Learn your options for unblocking your push from the command line to GitHub if secret scanning detects a secret in your changes.

* [Working with push protection in the GitHub UI](/en/code-security/how-tos/secure-your-secrets/work-with-leak-prevention/push-protection-in-the-github-ui)

  Learn your options for unblocking your commit when secret scanning detects a secret in your changes.

* [Enabling delegated bypass for push protection](/en/code-security/how-tos/secure-your-secrets/manage-bypass-requests/enable-delegated-bypass)

  Control who can push code containing secrets by requiring bypass approval from designated reviewers.

* [Exempting trusted actors from push protection](/en/code-security/how-tos/secure-your-secrets/manage-bypass-requests/grant-exemptions)

  Reduce friction for trusted automation by granting exemptions from push protection.

* [Managing requests to bypass push protection](/en/code-security/how-tos/secure-your-secrets/manage-bypass-requests/manage-bypass-requests)

  As a member of the bypass list for an organization or repository, you can review bypass requests from other members of the organization or repository.

* [Reviewing requests to bypass push protection](/en/code-security/how-tos/secure-your-secrets/manage-bypass-requests/review-bypass-requests)

  Approve or deny requests from contributors who need to push commits containing secrets to your organization's repositories.

* [Configuring default setup for code scanning](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configure-code-scanning)

  Quickly set up code scanning to find vulnerable code automatically.

* [Configuring advanced setup for code scanning](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configuring-advanced-setup-for-code-scanning)

  You can configure advanced setup for a repository to find security vulnerabilities in your code using a highly customizable code scanning configuration.

* [Editing your configuration of default setup](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/edit-default-setup)

  You can edit your existing configuration of default setup for code scanning to better meet your needs.

* [Use the tool status page for code scanning](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning)

  View real-time tool status, identify configuration problems, and download reports to keep your code scanning analysis running smoothly.

* [Set code scanning merge protection](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/set-merge-protection)

  Secure your codebase by blocking pull requests that fail code scanning checks.

* [Configuring larger runners for default setup](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/configure-larger-runners)

  Run code scanning default setup more quickly on bigger codebases using larger runners.

* [CodeQL code scanning for compiled languages](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/codeql-for-compiled-languages)

  Understand how CodeQL analyzes compiled languages, the build options available, and learn how you can customize the database generation process if you need to.

* [Setting up the CodeQL CLI](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/set-up-codeql-cli)

  To get started with the CodeQL CLI, you need to download and set up the CLI so that it can access the tools and libraries required to create and analyze databases.

* [Writing custom queries for the CodeQL CLI](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/write-custom-queries)

  You can write your own CodeQL queries to find specific vulnerabilities and errors.

* [Publishing and using CodeQL packs](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/publish-and-use-packs)

  Share or download a CodeQL pack, then analyze your CodeQL database.

* [Testing custom queries](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/test-custom-queries)

  Verify your custom CodeQL queries and catch breaking changes before they affect your code scanning results following new releases of the CodeQL CLI.

* [Testing query help files](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/test-query-help-files)

  Ensure your CodeQL query help files are valid by previewing them as Markdown.

* [Downloading CodeQL databases from GitHub](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/download-databases)

  Expand the coverage of the CodeQL CLI by adding ready-made databases.

* [Checking out the CodeQL CLI source code](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/check-out-source-code)

  Set up the CodeQL CLI directly from the source code.

* [Using incremental analysis with the CodeQL CLI](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/incremental-analysis)

  Get faster CodeQL results on pull requests by analyzing only what changed. Incremental analysis can reduce scan times by up to 10x when you run the CodeQL CLI in your own CI/CD system.

* [Specifying command options in a CodeQL configuration file](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/specify-command-options)

  Save time by adding your frequently used command options and custom CodeQL packs to a CodeQL configuration file.

* [Creating CodeQL CLI database bundles](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/create-database-bundles)

  Create a database bundle with CodeQL troubleshooting information.

* [Installing CodeQL for Visual Studio Code](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/install-codeql-for-vs-code)

  To get started with CodeQL for Visual Studio Code, you need to install and set up the extension.

* [Managing CodeQL databases](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/manage-codeql-databases)

  You can work with CodeQL databases using the extension.

* [Running CodeQL queries](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/running-codeql-queries)

  You can run queries on CodeQL databases and view the results in Visual Studio Code.

* [Exploring data flow with path queries](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/explore-data-flow)

  Detect potential vulnerabilities by running path queries and analyzing your data flow.

* [Running CodeQL queries at scale with multi-repository variant analysis](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/run-queries-at-scale)

  You can run CodeQL queries on a large number of repositories on GitHub from Visual Studio Code.

* [Using the CodeQL model editor](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/use-the-model-editor)

  You can view, write, and edit CodeQL model packs in Visual Studio Code.

* [Creating a custom query](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/create-custom-query)

  You can work from a template to write your own code to create a custom query to analyze a specific language.

* [Managing CodeQL query packs and library packs](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/managing-codeql-packs)

  Download and install dependencies for your CodeQL query and library packs in Visual Studio Code using the CodeQL extension.

* [Exploring the structure of your source code](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/explore-code-structure)

  Visualize how your code maps to CodeQL classes in VS Code.

* [Testing CodeQL queries in Visual Studio Code](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/testing-codeql-queries-in-vs-code)

  You can run unit tests for CodeQL queries using the Visual Studio Code extension.

* [Customizing settings](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/customize-settings)

  You can edit the settings for the CodeQL for Visual Studio Code extension to suit your needs.

* [Setting up a CodeQL workspace](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/set-up-codeql-workspace)

  When you're working with CodeQL, you need access to the standard libraries and queries.

* [Managing the CodeQL CLI in the VS Code extension](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/manage-codeql-cli)

  The CodeQL for Visual Studio Code extension uses the CodeQL CLI to compile and run queries.

* [Accessing logs for CodeQL in Visual Studio Code](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/accessing-logs)

  If you need to troubleshoot problems with CodeQL for Visual Studio Code, there are several logs you can access.

* [Using code scanning with your existing CI system](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/integrate-with-existing-tools/use-with-existing-ci-system)

  You can analyze your code with the CodeQL CLI or another tool in a third-party continuous integration system and upload the results to GitHub. The resulting code scanning alerts are shown alongside any alerts generated within GitHub.

* [Uploading a SARIF file to GitHub](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/integrate-with-existing-tools/upload-sarif-file)

  You can upload SARIF files generated outside GitHub and see code scanning alerts from third-party tools in your repository.

* [Configuring Dependabot alerts](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-dependabot-alerts)

  Enable Dependabot alerts to be generated when a new vulnerable dependency is found in one of your repositories.

* [Configuring Dependabot malware alerts](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-malware-alerts)

  Prevent malware attacks by identifying and remediating malicious dependencies.

* [Configuring Dependabot security updates](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-security-updates)

  You can use Dependabot security updates or manual pull requests to easily update vulnerable dependencies.

* [Configuring Dependabot version updates](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configure-version-updates)

  You can configure your repository so that Dependabot automatically updates the packages you use.

* [Managing innersource advisories](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/manage-innersource-advisories)

  Create, distribute, and withdraw enterprise-scoped advisories to alert your internal repositories to vulnerabilities and ship fixes automatically.

* [Keeping your actions up to date with Dependabot](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/auto-update-actions)

  You can use Dependabot to keep the actions you use updated to the latest versions.

* [Configuring multi-ecosystem updates for Dependabot](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/configuring-multi-ecosystem-updates)

  Reduce the number of Dependabot pull requests you receive by grouping updates across multiple ecosystems into a single, consolidated pull request.

* [Enabling the dependency graph](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/enable-dependency-graph)

  You can allow users to identify their projects' dependencies by enabling the dependency graph.

* [Exploring the dependencies of a repository](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/explore-dependencies)

  You can use the dependency graph to see the packages your project depends on. In addition, you can see any vulnerabilities detected in its dependencies.

* [Configuring automatic dependency submission for your repository](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/submit-dependencies-automatically)

  You can use automatic dependency submission to submit transitive dependency data in your repository. This enables you to analyze these transitive dependencies using the dependency graph.

* [Using the dependency submission API](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/use-dependency-submission-api)

  You can use the dependency submission API to submit dependencies for projects, such as the dependencies resolved when a project is built or compiled.

* [Verifying the integrity of a release](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/verify-release-integrity)

  You can avoid tampering and accidental changes by ensuring the releases you use have not been modified after publication.

* [Configuring open source license policies](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-license-policies)

  Create and enforce open source license policies to control which licenses your dependencies are allowed to use.

* [Customizing auto-triage rules to prioritize Dependabot alerts](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/auto-triage-dependabot-alerts)

  You can create your own auto-triage rules to control which alerts are dismissed or snoozed, and which alerts you want Dependabot to open pull requests for.

* [Using GitHub preset rules to prioritize Dependabot alerts](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/prioritize-with-preset-rules)

  Focus on alerts that matter by auto-dismissing low impact development alerts for npm dependencies.

* [Customizing pull requests for Dependabot security updates](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/customizing-dependabot-security-prs)

  Learn how to customize Dependabot pull requests for security updates to align with your project's security priorities and workflows.

* [Controlling which dependencies are updated by Dependabot](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/controlling-dependencies-updated)

  Learn how to configure your `dependabot.yml` file so that Dependabot automatically updates the packages you specify, in the way you define.

* [Configuring the dependency review action](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-dependency-review-action)

  You can use the dependency review action to catch vulnerabilities before they are added to your project.

* [Configuring notifications for Dependabot alerts](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-dependabot-notifications)

  Optimize how you receive notifications about Dependabot alerts.

* [Configuring access to private registries for Dependabot](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-access-to-private-registries)

  You can configure Dependabot to access dependencies stored in private registries. You can store authentication information, like passwords and access tokens, as encrypted secrets and then reference these in the Dependabot configuration file. If you have registries on private networks, you can also configure Dependabot access when running Dependabot on self-hosted runners.

* [Removing Dependabot access to public registries](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/remove-access-to-public-registries)

  Examples of how you can configure Dependabot to only access private registries by removing calls to public registries.

* [Managing pull requests for dependency updates](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/manage-dependabot-prs)

  You manage pull requests raised by Dependabot in much the same way as other pull requests, but there are some extra options.

* [Configuring Dependabot on GitHub-hosted runners](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-on-github-hosted-runners)

  Enable Dependabot on GitHub-hosted runners to more easily identify Dependabot job errors and manually detect and troubleshoot failed runs.

* [Configuring Dependabot on self-hosted runners](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-on-self-hosted-runners)

  You can configure self-hosted runners that Dependabot uses to access your private registries and internal network resources.

* [Re-running Dependabot jobs on GitHub Actions](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/re-run-dependabot-jobs)

  Resolve run failures and manually update your dependencies by re-running Dependabot jobs.

* [Listing dependencies configured for version updates](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/list-configured-dependencies)

  You can view the dependencies that Dependabot monitors for updates.

* [Guidance for the configuration of private registries for Dependabot](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-private-registries)

  This article contains detailed information about configuring private registries, as well as commands you can run from the command line to configure your package managers locally.

* [Preventing changes to your releases](/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/prevent-release-changes)

  You can enforce immutable releases for a repository or organization to prevent potential vulnerabilities.

* [Exporting a software bill of materials for your repository](/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/export-dependencies-as-sbom)

  You can export a software bill of materials or SBOM for your repository from the dependency graph. SBOMs allow transparency into your open source usage and help expose supply chain vulnerabilities, reducing supply chain risks.

* [Uploading storage and deployment data to the linked artifacts page](/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/upload-linked-artifacts)

  Associate packages and builds in your organization with storage and deployment data.

* [Auditing your organization's builds on the linked artifacts page](/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/view-linked-artifacts)

  View or export metadata for build runs, storage details, and deployment context.

* [Removing artifacts from the linked artifacts page](/en/code-security/how-tos/secure-your-supply-chain/establish-provenance-and-integrity/remove-linked-artifacts)

  Set the storage and deployment status of artifacts to reflect that they are no longer in use.

* [Filtering alerts in security overview](/en/code-security/how-tos/manage-security-alerts/remediate-alerts-at-scale/filtering-alerts-in-security-overview)

  Find the security alerts that matter most by filtering your security overview data.

* [Creating and managing security campaigns](/en/code-security/how-tos/manage-security-alerts/remediate-alerts-at-scale/creating-managing-security-campaigns)

  You can manage security campaigns directly from the security overview for your organization.

* [Tracking security campaigns](/en/code-security/how-tos/manage-security-alerts/remediate-alerts-at-scale/tracking-security-campaigns)

  Use the campaign tracking views to monitor remediation progress, identify stalled work, and measure campaign impact across your organization.

* [Fixing alerts in a security campaign](/en/code-security/how-tos/manage-security-alerts/remediate-alerts-at-scale/fixing-alerts-in-security-campaign)

  Learn how to find and fix alerts in a security campaign.

* [Reviewing alert dismissal requests](/en/code-security/how-tos/manage-security-alerts/remediate-alerts-at-scale/review-alert-dismissal-requests)

  Triage and resolve security alerts in your organization or enterprise by regularly reviewing alert dismissal requests.

* [Monitoring alerts from secret scanning](/en/code-security/how-tos/manage-security-alerts/manage-secret-scanning-alerts/monitoring-alerts)

  You can configure how  secret scanning notifies you about secret scanning alerts, and audit how your team responds to these alerts.

* [Viewing and filtering alerts from secret scanning](/en/code-security/how-tos/manage-security-alerts/manage-secret-scanning-alerts/viewing-alerts)

  Learn how to find and filter secret scanning alerts for your repository.

* [Resolving alerts from secret scanning](/en/code-security/how-tos/manage-security-alerts/manage-secret-scanning-alerts/resolving-alerts)

  After reviewing the details of a secret scanning alert, you should fix and then close the alert.

* [Enabling delegated alert dismissal for secret scanning](/en/code-security/how-tos/manage-security-alerts/manage-secret-scanning-alerts/enable-delegated-dismissal)

  You can use delegated alert dismissal to control who can dismiss an alert found by secret scanning.

* [Assessing code scanning alerts for your repository](/en/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/assess-alerts)

  From the security view, you can explore and evaluate alerts for potential vulnerabilities or errors in your project's code.

* [Triaging code scanning alerts in pull requests](/en/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/triage-alerts-in-pull-requests)

  When code scanning identifies a problem in a pull request, you can review the highlighted code and resolve the alert.

* [Linking code scanning alerts to GitHub issues](/en/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/track-alerts-in-issues)

  Create or connect GitHub issues to code scanning alerts to track security fixes in your team's workflow.

* [Resolving code scanning alerts](/en/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/resolve-alerts)

  From the security view, you can view, fix, or dismiss alerts for potential vulnerabilities or errors in your project's code.

* [Enabling delegated alert dismissal for code scanning](/en/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/enable-delegated-alert-dismissal)

  You can use delegated alert dismissal to control who can dismiss an alert found by code scanning.

* [Disabling autofix for code scanning security alerts](/en/code-security/how-tos/manage-security-alerts/manage-code-scanning-alerts/disabling-autofix-for-code-scanning)

  You can disable Copilot Autofix, which also blocks agentic autofix, for an enterprise, organization, or repository.

* [Viewing and updating Dependabot alerts](/en/code-security/how-tos/manage-security-alerts/manage-dependabot-alerts/view-dependabot-alerts)

  If GitHub discovers insecure dependencies in your project, you can view alert details on the Dependabot tab of your repository. Then, you can update your project to resolve or dismiss the alert.

* [Managing Dependabot malware alerts](/en/code-security/how-tos/manage-security-alerts/manage-dependabot-alerts/manage-malware-alerts)

  Find and triage malicious dependencies in your project with Dependabot malware alerts.

* [Managing alerts that have been automatically dismissed by a Dependabot auto-triage rule](/en/code-security/how-tos/manage-security-alerts/manage-dependabot-alerts/managing-automatically-dismissed-alerts)

  You can filter to see which alerts have been auto-dismissed by a rule, and you can reopen dismissed alerts.

* [Enabling delegated alert dismissal for Dependabot](/en/code-security/how-tos/manage-security-alerts/manage-dependabot-alerts/enable-delegated-alert-dismissal)

  Increase your governance over your Dependabot alerts with delegated alert dismissal.

* [Enabling GitHub Code Quality](/en/code-security/how-tos/maintain-quality-code/enable-code-quality)

  Turn on Code Quality to give your teams a consistent quality baseline: automatically catching, fixing, and reporting code quality issues in pull requests and on your default branch.

* [Disabling GitHub Code Quality](/en/code-security/how-tos/maintain-quality-code/disable-code-quality)

  Stop Code Quality scans on a repository or across your organization, and know what happens to billing and your existing data before you do.

* [Rolling out GitHub Code Quality at scale](/en/code-security/how-tos/maintain-quality-code/roll-out-at-scale)

  Bring Code Quality to every team with confidence by piloting on a small group first, then expanding once your quality thresholds are tuned.

* [Setting code quality thresholds for pull requests](/en/code-security/how-tos/maintain-quality-code/set-pr-thresholds)

  Enforce your code quality standards automatically by blocking pull requests that fall below the thresholds you set, at the repository or organization level.

* [Setting up code coverage for your repository](/en/code-security/how-tos/maintain-quality-code/set-up-code-coverage)

  Give your teams visibility into code coverage directly on pull requests, without paying for or maintaining a separate third-party coverage service.

* [Setting code coverage thresholds for pull requests](/en/code-security/how-tos/maintain-quality-code/restrict-code-coverage)

  Protect your code coverage by automatically blocking pull requests that fall below the coverage levels your team requires.

* [Fixing code quality findings on a pull request](/en/code-security/how-tos/maintain-quality-code/fix-findings-on-a-pr)

  Keep quality issues out of your default branch by applying autofixes, delegating remediation work to Copilot, or dismissing irrelevant findings.

* [Resolving a block on your pull request](/en/code-security/how-tos/maintain-quality-code/unblock-your-pr)

  Identify and resolve a code quality or coverage threshold block on your pull request so you can merge your changes.

* [Viewing code coverage on pull requests](/en/code-security/how-tos/maintain-quality-code/view-coverage-on-prs)

  Review the coverage summary posted on your pull requests to identify files with low or declining code coverage.

* [Fixing code quality findings in your repository backlog](/en/code-security/how-tos/maintain-quality-code/fix-backlog-findings)

  Generate autofixes for findings on the default branch of your repository, or dismiss findings that aren't relevant.

* [Fixing code quality findings in recently merged files](/en/code-security/how-tos/maintain-quality-code/fix-findings-in-recent-merges)

  Apply autofixes or delegate remediation work to Copilot for quality issues detected by AI-powered analysis of recently merged code.

* [Interpreting the code quality results for your repository](/en/code-security/how-tos/maintain-quality-code/interpret-results)

  Understand the maintainability and reliability of your codebase so you can prioritize where your teams focus remediation effort.

* [Exploring GitHub Code Quality results in your organization](/en/code-security/how-tos/maintain-quality-code/explore-code-quality)

  Understand your organization's code health at a glance with the organization-level dashboard for Code Quality.

* [Viewing and managing GitHub Code Quality costs](/en/code-security/how-tos/maintain-quality-code/view-and-manage-cost)

  Keep your Code Quality spend predictable by seeing exactly where charges come from and using the levers that bring them down.

* [Adding a security policy to your repository](/en/code-security/how-tos/report-and-fix-vulnerabilities/configure-vulnerability-reporting/add-security-policy)

  You can give instructions for how to report a security vulnerability in your project by adding a security policy to your repository.

* [Configuring private vulnerability reporting for a repository](/en/code-security/how-tos/report-and-fix-vulnerabilities/configure-vulnerability-reporting/configure-for-a-repository)

  Owners and administrators of public repositories can allow security researchers to report vulnerabilities securely in the repository by enabling private vulnerability reporting.

* [Privately reporting a security vulnerability](/en/code-security/how-tos/report-and-fix-vulnerabilities/report-privately)

  Some public repositories configure security advisories so that anyone can report security vulnerabilities directly and privately to the maintainers.

* [Managing privately reported security vulnerabilities](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/manage-vulnerability-reports)

  Repository maintainers can manage security vulnerabilities that have been privately reported to them by security researchers for repositories where private vulnerability reporting is enabled.

* [Creating a repository security advisory](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/create-repository-advisory)

  You can create a draft security advisory to privately discuss and fix a security vulnerability in your open source project.

* [Publishing a repository security advisory](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/publish-repository-advisory)

  You can publish a security advisory to alert your community about a security vulnerability in your project.

* [Adding a collaborator to a repository security advisory](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/add-collaborators)

  Add other users or teams to collaborate on a security advisory with you.

* [Removing a collaborator from a repository security advisory](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/remove-collaborators)

  When you remove a collaborator from a repository security advisory, they lose read and write access to the security advisory's discussion and metadata.

* [Editing a repository security advisory](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/edit-repository-advisories)

  You can edit the metadata and description for a repository security advisory if you need to update details or correct errors.

* [Deleting a repository security advisory](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/delete-repository-advisories)

  You can delete a repository security advisory that you've published by contacting Support.

* [Browsing security advisories in the GitHub Advisory Database](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/browse-advisory-database)

  You can browse the GitHub Advisory Database to find CVEs and GitHub-originated advisories affecting the open source world.

* [Editing security advisories in the GitHub Advisory Database](/en/code-security/how-tos/report-and-fix-vulnerabilities/fix-reported-vulnerabilities/edit-advisory-database)

  Improve advisories published in the GitHub Advisory Database by making community contributions.

* [Scanning for secrets with the GitHub MCP server](/en/code-security/how-tos/use-ghas-with-ai-coding-agents/scan-for-secrets-with-github-mcp-server)

  Detect exposed secrets in real time from your AI coding agent, before they ever reach your repository.

* [Assessing the security risk of your code](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/assessing-code-security-risk)

  You can use security overview to see which teams and repositories are affected by security alerts, and identify repositories for urgent remedial action.

* [Assessing adoption of security features](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/assessing-adoption-code-security)

  See which teams and repositories have already enabled features for secure coding, and identify any that are not yet protected.

* [Finding repositories with security alerts using security overview](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/find-insecure-repositories)

  Monitor and prioritize security alerts with security overview.

* [Exporting data from security overview](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/export-data)

  From security overview, you can export CSV files of the data used for your organization or enterprise's overview, risk, coverage, and CodeQL pull request insights pages.

* [Viewing security insights](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-security-insights)

  Monitor your organization security posture, identify high-risk repositories, and track alert remediation progress using the overview dashboard in security overview.

* [Viewing metrics for pull request alerts](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-metrics-for-pull-request-alerts)

  Monitor CodeQL's performance in pull requests across your organizations to identify repositories where you may need to take action.

* [Viewing metrics for secret scanning push protection](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-metrics-for-secret-scanning-push-protection)

  Monitor push protection's performance across your organization to identify repositories where you may need to take action.

* [Viewing public monitoring alerts](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-public-monitoring-alerts)

  Find out which credentials your enterprise members have exposed in public repositories across GitHub.

* [Viewing metrics for Dependabot alerts](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-metrics-for-dependabot-alerts)

  You can use security overview to see how many Dependabot alerts are in repositories across your organization, to prioritize the most critical alerts to fix, and to identify repositories where you may need to take action.

* [Exporting the secret risk assessment report to CSV](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/export-risk-report-csv)

  Export the secret risk assessment report to a CSV file for detailed investigation and stakeholder sharing.

* [Viewing code scanning logs from GitHub Actions](/en/code-security/how-tos/view-and-interpret-data/view-code-scanning-logs)

  View the output from a code scanning analysis in GitHub Actions.

* [Viewing Dependabot job logs](/en/code-security/how-tos/view-and-interpret-data/view-dependabot-logs)

  Access job logs to troubleshoot failed Dependabot updates and understand what is happening.

* [Viewing metrics for custom patterns](/en/code-security/how-tos/view-and-interpret-data/view-custom-pattern-metrics)

  Find out how many alerts are being raised and addressed for a custom pattern.

* [Changing the "used by" data for a repository](/en/code-security/how-tos/view-and-interpret-data/change-used-by-data)

  Display your repository's dependents for a different package.

* [Security overview dashboard metrics](/en/code-security/reference/security-at-scale/overview-dashboard-metrics)

  Detailed explanations of metrics, calculations, and data visualizations on the overview page of your security overview.

* [Available filters for security overview](/en/code-security/reference/security-at-scale/overview-dashboard-filters)

  Reference for all available filters you can use to narrow security overview data.

* [Security configuration enforcement](/en/code-security/reference/security-at-scale/configuration-enforcement)

  Understand the complexities of enforcing security configurations.

* [Security configuration statuses](/en/code-security/reference/security-at-scale/configuration-statuses)

  Each repository that has a security configuration applied to it has a configuration status that reflects the current state of the relationship between the repository and the configuration.

* [A repository is using advanced setup for code scanning](/en/code-security/reference/security-at-scale/troubleshoot-security-configurations/a-repository-is-using-advanced-setup-for-code-scanning)

  You see an error when you try to attach a security configuration with default code scanning enabled to repositories that use advanced setup for code scanning.

* [A feature has disappeared from a security configuration](/en/feature-disappears)

  Changes to your GitHub Enterprise Server instance's installation settings by a site administrator may affect which security features are available to your configuration.

* [Default setup for code scanning overrides advanced setup](/en/code-security/reference/security-at-scale/troubleshoot-security-configurations/unexpected-default-setup)

  You apply a security configuration with "Enabled with advanced setup allowed" and the existing advanced setup for code scanning is ignored in some repositories.

* [Diagnosing security configuration issues](/en/code-security/reference/security-at-scale/troubleshoot-security-configurations/configuration-issue-diagnosis)

  Identify repositories where the security configuration could not be attached, or where the configuration relationship has changed, and follow guidance to remediate the problem.

* [Not enough GitHub Advanced Security licenses](/en/code-security/reference/security-at-scale/troubleshoot-security-configurations/not-enough-ghas-licenses)

  If you are on a subscription-based billing model for GHAS, you need available GHAS licenses to enable GHAS features on a private repository.

* [Understanding GitHub secret types](/en/code-security/reference/secret-security/secret-types)

  Learn about the usage, scope, and access permissions for GitHub secrets.

* [Supported secret scanning patterns](/en/code-security/reference/secret-security/supported-secret-scanning-patterns)

  Lists of supported secrets and the partners that GitHub works with to prevent fraudulent use of secrets that were committed accidentally.

* [Secret scanning detection scope](/en/code-security/reference/secret-security/secret-scanning-scope)

  Secret scanning uses pattern matching and validation to detect secrets. Detection varies based on pattern pairs, token types, and push protection settings.

* [Custom patterns reference](/en/code-security/reference/secret-security/custom-patterns)

  Use specific regular expression syntax to define accurate custom patterns for secret scanning.

* [Contents of the secret risk assessment report CSV](/en/code-security/reference/secret-security/risk-report-csv-contents)

  Understand the data included in the CSV export of the secret risk assessment report.

* [Secret scanning pattern configuration data](/en/code-security/reference/secret-security/secret-pattern-data)

  Understand the data displayed in the secret scanning pattern configuration page to make informed decisions about push protection settings.

* [Workflow configuration options for code scanning](/en/code-security/reference/code-scanning/workflow-configuration-options)

  Edit your workflow file to configure how advanced setup scans the code in your project for vulnerabilities and errors.

* [SARIF support for code scanning](/en/code-security/reference/code-scanning/sarif-files/sarif-support)

  Ensure your SARIF files from third-party tools comply with GitHub's standards.

* [GitHub token is required to upload SARIF results](/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/missing-token)

  You need to provide an authentication method for the upload process to use to access the repository.

* [SARIF file is invalid](/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/sarif-invalid)

  Code scanning can only process syntactically valid SARIF files. Invalid files are rejected.

* [SARIF results exceed one or more limits](/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/results-exceed-limit)

  Learn how to resolve problems when a SARIF file is rejected by code scanning because one or more limits is exceeded.

* [SARIF results file is too large](/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/file-too-large)

  You cannot upload a SARIF results file larger than 10 MB to code scanning. Explore ways to generate a smaller file containing the highest impact results.

* [Upload fails because GitHub Code Security is disabled](/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/ghas-required)

  You can only upload SARIF results to repositories where GitHub Code Security is enabled.

* [Upload was rejected because CodeQL default setup is enabled for code scanning](/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/default-setup-enabled)

  You cannot upload SARIF results generated by the CodeQL action or CodeQL CLI when default setup for code scanning is enabled. Check your configuration and decide whether to keep default setup or unblock SARIF upload.

* [Recommended hardware resources for running CodeQL](/en/code-security/reference/code-scanning/codeql/hardware-resources-for-codeql)

  Recommended specifications (RAM, CPU cores, and disk) for running CodeQL analysis on self-hosted machines, based on the size of your codebase.

* [CodeQL build options and steps for compiled languages](/en/code-security/reference/code-scanning/codeql/build-options-for-compiled-languages)

  Learn how CodeQL builds compiled languages, including available build modes and language-specific autobuild behavior for C/C++, C#, Go, Java, Kotlin, Rust, and Swift.

* [About built-in CodeQL queries](/en/code-security/reference/code-scanning/codeql/codeql-queries/built-in-queries)

  Learn about the CodeQL queries that code scanning uses to analyze code.

* [GitHub Actions queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/actions-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in GitHub Actions workflow files when you select the `default` or the `security-extended` query suite.

* [C and C++ queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/c-cpp-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in C or C++ when you select the `default` or the `security-extended` query suite.

* [C# queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/csharp-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in C# when you select the `default` or the `security-extended` query suite.

* [Go queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/go-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in Go (Golang) when you select the `default` or the `security-extended` query suite.

* [Java and Kotlin queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/java-kotlin-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in Java or Kotlin when you select the `default` or the `security-extended` query suite.

* [JavaScript and TypeScript queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/javascript-typescript-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in JavaScript or TypeScript when you select the `default` or the `security-extended` query suite.

* [Python queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/python-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in Python when you select the `default` or the `security-extended` query suite.

* [Ruby queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/ruby-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in Ruby when you select the `default` or the `security-extended` query suite.

* [Rust queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/rust-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in Rust when you select the `default` or the `security-extended` query suite.

* [Swift queries for CodeQL analysis](/en/code-security/reference/code-scanning/codeql/codeql-queries/swift-built-in-queries)

  Explore the queries that CodeQL uses to analyze code written in Swift when you select the `default` or the `security-extended` query suite.

* [CodeQL CLI SARIF output](/en/code-security/reference/code-scanning/codeql/codeql-cli/sarif-output)

  You can output SARIF from the CodeQL CLI and share static analysis results with other systems.

* [CodeQL CLI CSV output](/en/code-security/reference/code-scanning/codeql/codeql-cli/csv-output)

  Understand CSV results from the CodeQL CLI.

* [CodeQL query packs reference](/en/code-security/reference/code-scanning/codeql/codeql-cli/codeql-query-packs)

  Understand the compatibility, contents, and structure of CodeQL packs.

* [Extractor options](/en/code-security/reference/code-scanning/codeql/codeql-cli/extractor-options)

  Control how the CodeQL CLI builds databases for analysis with extractor options.

* [Exit codes](/en/code-security/reference/code-scanning/codeql/codeql-cli/exit-codes)

  Exit codes signify the status of a command after the CodeQL CLI runs it.

* [bqrs decode](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-decode)

  Convert result data from BQRS into other forms.

* [bqrs diff](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-diff)

  Compute the difference between two result sets.

* [bqrs hash](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-hash)

  \[Plumbing] Compute a stable hash of a BQRS file.

* [bqrs info](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-info)

  Display metadata for a BQRS file.

* [bqrs interpret](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-interpret)

  \[Plumbing] Interpret data in a single BQRS.

* [database add-diagnostic](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-add-diagnostic)

  \[Experimental] Add a piece of diagnostic information to a database.

* [database analyze](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-analyze)

  Analyze a database, producing meaningful results in the context of the
  source code.

* [database bundle](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-bundle)

  Create a relocatable archive of a CodeQL database.

* [database cleanup](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-cleanup)

  Compact a CodeQL database on disk.

* [database create](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-create)

  Create a CodeQL database for a source tree that can be analyzed using
  one of the CodeQL products.

* [database export-diagnostics](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-export-diagnostics)

  \[Experimental] Export diagnostic information from a database for a
  failed analysis.

* [database finalize](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-finalize)

  \[Plumbing] Final steps in database creation.

* [database import](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-import)

  \[Advanced] \[Plumbing] Import unfinalized database(s) into another
  unfinalized database.

* [database index-files](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-index-files)

  \[Plumbing] Index standalone files with a given CodeQL extractor.

* [database init](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-init)

  \[Plumbing] Create an empty CodeQL database.

* [database interpret-results](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-interpret-results)

  \[Plumbing] Interpret computed query results into meaningful formats
  such as SARIF or CSV.

* [database print-baseline](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-print-baseline)

  \[Plumbing] Print a summary of the baseline lines of code seen.

* [database run-queries](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-run-queries)

  \[Plumbing] Run a set of queries together.

* [database trace-command](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-trace-command)

  \[Plumbing] Run a single command as part of a traced build.

* [database unbundle](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-unbundle)

  Extracts a CodeQL database archive.

* [database upgrade](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-upgrade)

  Upgrade a database so it is usable by the current tools.

* [dataset check](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-check)

  \[Plumbing] Check a particular dataset for internal consistency.

* [dataset cleanup](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-cleanup)

  \[Plumbing] Clean up temporary files from a dataset.

* [dataset import](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-import)

  \[Plumbing] Import a set of TRAP files to a raw dataset.

* [dataset measure](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-measure)

  \[Plumbing] Collect statistics about the relations in a particular
  dataset.

* [dataset upgrade](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-upgrade)

  \[Plumbing] Upgrade a dataset so it is usable by the current tools.

* [diagnostic add](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/diagnostic-add)

  \[Experimental] \[Plumbing] Add a piece of diagnostic information.

* [diagnostic export](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/diagnostic-export)

  \[Experimental] Export diagnostic information for a failed analysis.

* [execute cli-server](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-cli-server)

  \[Deep plumbing] Server for running multiple commands while avoiding
  repeated JVM initialization.

* [execute language-server](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-language-server)

  \[Plumbing] On-line support for the QL language in IDEs.

* [execute queries](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-queries)

  \[Plumbing] Run one or more queries against a dataset.

* [execute query-server](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-query-server)

  \[Plumbing] Support for running queries from IDEs.

* [execute query-server2](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-query-server2)

  \[Plumbing] Support for running queries from IDEs.

* [execute upgrades](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-upgrades)

  \[Plumbing] Run upgrade scripts on an existing raw QL dataset.

* [generate extensible-predicate-metadata](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-extensible-predicate-metadata)

  \[Experimental] \[Deep plumbing] Report the extensible predicates
  found in the given pack.

* [generate log-summary](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-log-summary)

  \[Advanced] Create a summary of a structured log file.

* [generate overlay-changes](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-overlay-changes)

  \[Plumbing] Generate a file that can be used for the

* [generate query-help](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-query-help)

  Generate end-user query help from .qhelp files.

* [github merge-results](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/github-merge-results)

  \[Deep plumbing] Merges multiple SARIF files into a single SARIF file.

* [github upload-results](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/github-upload-results)

  Uploads a SARIF file to GitHub code scanning.

* [pack add](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-add)

  Adds a list of QL library packs with optional version
  ranges as dependencies of the current package, and then installs them.

* [pack bundle](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-bundle)

  \[Plumbing] Bundle a QL library pack.

* [pack ci](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-ci)

  Install dependencies for this pack, verifying that the
  existing lock file is up to date.

* [pack create](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-create)

  \[Plumbing] Builds the contents of a QL package from
  source code.

* [pack download](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-download)

  Download the set of qlpacks referenced by the query
  spec of the command line from the registry. Packs can be provided by
  name or implicitly inside of a query suite (.qls) file.

* [pack init](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-init)

  Initializes a qlpack in the specified directory.

* [pack install](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-install)

  Install dependencies for this pack.

* [pack ls](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-ls)

  \[Deep plumbing] List the CodeQL packages rooted at
  this directory. This directory must contain a qlpack.yml or
  .codeqlmanifest.json file.

* [pack packlist](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-packlist)

  \[Plumbing] Compute the set of files to be included in
  a QL query pack or library pack.

* [pack publish](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-publish)

  Publishes a QL library pack to a package registry.

* [pack resolve-dependencies](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-resolve-dependencies)

  \[Plumbing] Compute the set of required dependencies
  for this QL pack.

* [pack upgrade](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-upgrade)

  Update the dependencies for this pack to the latest
  available versions.

* [query compile](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-compile)

  Compile or check QL code.

* [query decompile](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-decompile)

  \[Plumbing] Read an intermediate representation of a compiled query
  from a .qlo file.

* [query format](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-format)

  Autoformat QL source code.

* [query run](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-run)

  Run a single query.

* [resolve database](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-database)

  \[Deep plumbing] Report metadata about the database.

* [resolve extensions](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-extensions)

  \[Experimental] \[Deep plumbing] Determine accessible extensions. This
  includes machine learning models and data extensions.

* [resolve extensions-by-pack](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-extensions-by-pack)

  \[Experimental] \[Deep plumbing] Determine accessible extensions for
  the given paths to pack roots. This includes machine learning models and
  data extensions.

* [resolve extractor](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-extractor)

  \[Deep plumbing] Determine the extractor pack to use for a given
  language.

* [resolve files](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-files)

  \[Deep plumbing] Expand a set of file inclusion/exclusion globs.

* [resolve languages](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-languages)

  List installed CodeQL extractor packs.

* [resolve library-path](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-library-path)

  \[Deep plumbing] Determine QL library path and dbscheme for a query.

* [resolve metadata](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-metadata)

  \[Deep plumbing] Resolve and return the key-value metadata pairs from a
  query source file.

* [resolve ml-models](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-ml-models)

  \[Deprecated] \[Experimental] \[Deep plumbing] Determine accessible
  machine learning models.

* [resolve packs](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-packs)

  Display a list of available CodeQL packs and their locations.

* [resolve qlpacks](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-qlpacks)

  Create a list of installed QL packs and their locations.

* [resolve qlref](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-qlref)

  \[Deep plumbing] Dereferences a .qlref file to return a .ql one.

* [resolve queries](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-queries)

  \[Deep plumbing] Expand query directories and suite specifications.

* [resolve ram](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-ram)

  \[Deep plumbing] Prepare RAM options.

* [resolve tests](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-tests)

  \[Deep plumbing] Find QL unit tests in given directories.

* [resolve upgrades](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-upgrades)

  \[Deep plumbing] Determine upgrades to run for a raw dataset.

* [test accept](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/test-accept)

  Accept results of failing unit tests.

* [test extract](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/test-extract)

  \[Plumbing] Build a dataset for a test directory.

* [test run](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/test-run)

  Run unit tests for QL queries.

* [version](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/version)

  Show the version of the CodeQL toolchain.

* [Telemetry in CodeQL for Visual Studio Code](/en/code-security/reference/code-scanning/codeql/codeql-for-vs-code/telemetry-in-codeql-for-visual-studio-code)

  If VS Code telemetry is enabled, GitHub will collect usage data and metrics for the purposes of helping the core developers to improve the CodeQL extension for VS Code.

* [Problem with controller repository](/en/code-security/reference/code-scanning/codeql/codeql-for-vs-code/controller-repository-warning)

  If you see this warning, update your controller repository to a private repository.

* [Alerts found in generated code](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/alerts-in-generated-code)

  When analyzing your code with code scanning, you may wish to build only the code which you wish to analyze.

* [Automatic build failed for a compiled language](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/automatic-build-failed)

  If automatic build fails, you can configure code scanning to use specific build steps for compiled languages.

* [C# compiler unexpectedly failing](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/c-sharp-compiler-unexpectedly-failing)

  If your MSBuild C# compilation is unexpectedly failing, you may need to amend your application project file.

* [Cannot enable CodeQL in a private repository](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/private-repository-enablement)

  GitHub Code Security must be enabled in order to use code scanning on private repositories.

* [Code scanning analysis takes too long](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/analysis-takes-too-long)

  You can fine tune your code scanning configuration to minimize analysis time.

* [CodeQL scanned fewer lines than expected](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/fewer-lines-scanned-than-expected)

  If CodeQL analyzed less code than you expected, you may need to use a custom build command.

* [Enabling default setup takes too long](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/default-setup-timeout)

  If you think that enabling default setup has stalled, you can restart the process.

* [Error: "GitHub Code Security or GitHub Advanced Security must be enabled for this repository to use code scanning"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/advanced-security-must-be-enabled)

  If you see this error, make sure that GitHub Code Security is enabled.

* ["Out of disk" and "Out of memory" errors](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/out-of-disk-or-memory)

  If you see one of these errors with GitHub Actions, you can try alternative runners.

* [Error: 403 "Resource not accessible by integration"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/resource-not-accessible)

  This error may be seen on pull requests created by Dependabot and can be resolved in a couple of different ways.

* [Error: "is not a .ql file, .qls file, a directory, or a query pack specification"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/not-recognized)

  CodeQL was unable to locate one of the queries or sets of queries that are specified for analysis.

* [Error: "No source code was seen during the build"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/no-source-code-seen-during-build)

  When CodeQL fails to find any source code, you need to resolve this problem to unblock code scanning analysis.

* [Error: "Server error"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/server-error)

  If you see this error, it may be transient. Check the current GitHub Actions service status, and try running your workflow again.

* [Extraction errors in the database](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/extraction-errors-in-the-database)

  You can check whether or not extraction errors affect the health of the CodeQL database created.

* [Logs are not detailed enough](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/logs-not-detailed-enough)

  Increase log verbosity and generate debugging artifacts when logs lack diagnostic detail.

* [Results are different than expected](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/results-different-than-expected)

  If your code scanning results are different than you expected, you can check which configurations are active.

* [Some languages were not analyzed with CodeQL advanced setup](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/some-languages-not-analyzed)

  If some languages were not analyzed, you can modify your code scanning workflow to add a matrix specifying the languages you want to analyze.

* [Two CodeQL workflows](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/two-codeql-workflows)

  If you see two workflows named "CodeQL", one workflow may be a pre-existing CodeQL workflow file which has been disabled by default setup.

* [Unclear what triggered a workflow run](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/unclear-what-triggered-a-workflow)

  If you don't know what triggered an analysis, investigate the tool status page or look at the log for the last scan.

* [Warning: "1 issue was detected with this workflow: git checkout HEAD^2 is no longer necessary"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/unnecessary-step-found)

  If you see this warning, you should update your workflow to follow current best practice.

* [Warning: Detected X Kotlin files in your project that could not be processed without a build](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/kotlin-detected-in-no-build)

  CodeQL databases can be created for Java without building the code, but Kotlin files are excluded unless the code is built.

* [Code scanning logs](/en/code-security/reference/code-scanning/code-scanning-logs)

  You can view the output generated during code scanning analysis in GitHub.

* [Automatic dependency submission](/en/code-security/reference/supply-chain-security/automatic-dependency-submission)

  Network access requirements, troubleshooting, and ecosystem-specific behavior for automatic dependency submission.

* [Dependabot options reference](/en/code-security/reference/supply-chain-security/dependabot-options-reference)

  Detailed information for all the options you can use to customize how Dependabot maintains your repositories.

* [Dependabot alert filters](/en/code-security/reference/supply-chain-security/dependabot-alerts-filters)

  Dependabot alerts filters help you prioritize and manage alerts for vulnerable dependencies in your repositories.

* [Supported ecosystems and manifests for dependency scope](/en/code-security/reference/supply-chain-security/supported-ecosystems-and-manifests-for-dependency-scope)

  Dependabot alerts supports a variety of ecosystems and manifests for dependency scope.

* [Dependabot pull request comment commands](/en/code-security/reference/supply-chain-security/dependabot-pull-request-comment-commands)

  Dependabot responds to commands in comments on its pull requests, making it easy to triage and manage dependency updates.

* [Dependabot supported ecosystems and repositories](/en/code-security/reference/supply-chain-security/supported-ecosystems-and-repositories)

  Dependabot supports a variety of ecosystems and repositories

* [Dependabot security updates reference](/en/code-security/reference/supply-chain-security/dependabot-security-updates)

  Find usage information for Dependabot security updates.

* [Dependency graph supported package ecosystems](/en/code-security/reference/supply-chain-security/dependency-graph-supported-package-ecosystems)

  Dependency graph supports a variety of ecosystems.

* [Dependabot on GitHub Actions](/en/code-security/reference/supply-chain-security/dependabot-on-actions)

  Detailed information on using Dependabot with GitHub Actions.

* [CWEs used by GitHub's preset Dependabot rules](/en/code-security/reference/supply-chain-security/criteria-for-preset-rules)

  GitHub uses industry-standard criteria to help you filter Dependabot alerts.

* [Troubleshooting the dependency graph](/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependency-graph-errors)

  If the dependency information reported by the dependency graph is not what you expected, there are a number of points to consider, and various things you can check.

* [Dependabot update pull requests no longer generated](/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-updates-stopped)

  Dependabot can pause updates based on your interaction with Dependabot pull requests. Learn more about the automatic deactivation of Dependabot updates.

* [Troubleshooting Dependabot on GitHub Actions](/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-on-actions)

  This article provides troubleshooting information for issues you may encounter when using Dependabot with GitHub Actions.

* [Vulnerable dependency detection](/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/vulnerability-detection)

  If the dependency information reported by GitHub is not what you expected, there are a number of points to consider, and various things you can check.

* [Dependabot errors](/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-errors)

  Dependabot automatically maintains your dependencies, keeping your code secure and current. This reference helps you diagnose and resolve issues so automated updates can continue.

* [Java package metadata for Dependabot updates](/en/code-security/reference/supply-chain-security/java-package-metadata-dependabot)

  Include metadata in your `pom.xml` file to provide helpful links and context in Dependabot pull requests for Java package updates.

* [Metrics and scores reference](/en/code-security/reference/code-quality/metrics-and-ratings)

  Understand the terminology used by GitHub to assess the quality of your repository's code.

* [Code coverage reference](/en/code-security/reference/code-quality/code-coverage)

  Code Quality shows how much of your code your tests actually exercise, so you can find untested code before you merge.

* [CodeQL-powered analysis for Code Quality](/en/code-security/reference/code-quality/codeql-detection)

  Information on how CodeQL-powered analysis for Code Quality works, the workflow used, and the status checks reported on pull requests.

* [C# CodeQL queries for Code Quality](/en/code-security/reference/code-quality/codeql-queries/csharp-queries)

  Explore the queries that CodeQL uses to analyze code quality for code written in C#.

* [Go CodeQL queries for Code Quality](/en/code-security/reference/code-quality/codeql-queries/go-queries)

  Explore the queries that CodeQL uses to analyze code quality for code written in Go.

* [Java CodeQL queries for Code Quality](/en/code-security/reference/code-quality/codeql-queries/java-queries)

  Explore the queries that CodeQL uses to analyze code quality for code written in Java.

* [JavaScript CodeQL queries for Code Quality](/en/code-security/reference/code-quality/codeql-queries/javascript-queries)

  Explore the queries that CodeQL uses to analyze code quality for code written in JavaScript.

* [Python CodeQL queries for Code Quality](/en/code-security/reference/code-quality/codeql-queries/python-queries)

  Explore the queries that CodeQL uses to analyze code quality for code written in Python.

* [Ruby CodeQL queries for Code Quality](/en/code-security/reference/code-quality/codeql-queries/ruby-queries)

  Explore the queries that CodeQL uses to analyze code quality for code written in Ruby.

* [Repository security advisories](/en/code-security/reference/permissions/repository-security-advisory)

  The actions you can take in a repository security advisory depend on whether you have admin or write permissions to the security advisory.

* [Security overview permissions](/en/code-security/reference/permissions/security-overview)

  The actions you can take in security overview depend on your permissions for the repositories in your organization or enterprise.

* [Investigation tools for security incidents](/en/code-security/reference/security-incident-response/investigation-tools)

  The core GitHub tools you can use to investigate security incidents, what each tool is best used for, and common considerations that affect what data is available.

* [Common security incident investigation areas](/en/code-security/reference/security-incident-response/investigation-areas)

  Reference for investigating security incidents across multiple attack vectors, including the key surfaces and tools to check on GitHub.

* [Secure your secrets at scale with GitHub](/en/code-security/tutorials/secret-protection-adoption-path)

  Leaked credentials expose your organization to data breaches. GitHub Secret Protection detects and prevents secret leaks automatically. Follow this adoption path to assess risk, pilot the solution, and scale protection organization-wide.

* [Planning a trial of GitHub Advanced Security](/en/code-security/tutorials/trialing-github-advanced-security/planning-a-trial-of-ghas)

  Learn how to prepare for a successful trial of Advanced Security.

* [Setting up a trial of GitHub Advanced Security](/en/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security)

  You can try the full set of GitHub Advanced Security features for free.

* [Enabling security features in your trial enterprise](/en/code-security/tutorials/trialing-github-advanced-security/enable-security-features-trial)

  Quickly create an enterprise-level configuration and apply Secret Protection and Code Security features across all repositories in your trial enterprise.

* [Exploring your enterprise trial of GitHub Secret Protection](/en/code-security/tutorials/trialing-github-advanced-security/explore-trial-secret-scanning)

  Introduction to the features available with GitHub Secret Protection in GitHub Enterprise Cloud so you can assess their fit to your business needs.

* [Exploring your enterprise trial of GitHub Code Security](/en/code-security/tutorials/trialing-github-advanced-security/explore-trial-code-scanning)

  Introduction to the features of code and dependency scanning available with GitHub Code Security in GitHub Enterprise Cloud so you can assess their fit to your business needs.

* [Adopting GitHub Advanced Security at scale](/en/adopting-github-advanced-security-at-scale)

  A phased approach to rolling out GitHub Advanced Security at your company using industry and GitHub best practices.

* [Best practices for preventing data leaks in your organization](/en/code-security/tutorials/secure-your-organization/prevent-data-leaks)

  Learn guidance and recommendations to help you avoid private or sensitive data present in your organization from being exposed.

* [Running a security campaign to fix alerts at scale](/en/code-security/tutorials/secure-your-organization/best-practice-fix-alerts-at-scale)

  Launch a focused security campaign to remediate a specific class of security alerts, such as cross-site scripting (XSS), across your organization.

* [Prioritizing Dependabot and code scanning alerts using production context](/en/code-security/tutorials/secure-your-organization/prioritize-alerts-in-production-code)

  Focus remediation on real risk by targeting Dependabot and code scanning alerts in artifacts deployed to production, using metadata from external systems and integrations like Dynatrace, JFrog Artifactory, Microsoft Defender for Cloud, or your own CI/CD workflows.

* [Interpreting secret risk assessment results](/en/code-security/tutorials/secure-your-organization/interpret-secret-risk-assessment)

  Understand the results from your secret risk assessment and prioritize leak remediation.

* [Interpreting code security risk assessment results](/en/code-security/tutorials/secure-your-organization/interpret-code-security-risk-assessment)

  Understand the results from your code security risk assessment and prioritize vulnerability remediation.

* [Organizing remediation efforts for leaked secrets](/en/code-security/tutorials/secure-your-organization/organize-leak-remediation)

  Systematically organize and manage the remediation of leaked secrets using security campaigns and alert assignments.

* [Protecting against security threats](/en/code-security/tutorials/secure-your-organization/protect-against-threats)

  What steps should I take now, in the near future, and on an ongoing basis to reduce exposure to security threats across my organizations on GitHub?

* [Preparing for a security incident](/en/code-security/tutorials/secure-your-organization/prepare-for-a-security-incident)

  Ensure you have the tools and processes in place to respond effectively to a security incident.

* [Responding to a security incident](/en/code-security/tutorials/secure-your-organization/respond-to-a-security-incident)

  Respond strategically to a security incident affecting organizations or repositories in your GitHub enterprise.

* [Calculating the cost savings of push protection](/en/code-security/tutorials/remediate-leaked-secrets/calculate-cost-savings)

  Estimate the remediation time and labor costs you'll avoid by preventing leaked secrets.

* [Assessing the impact of GitHub Secret Protection](/en/code-security/tutorials/remediate-leaked-secrets/assessing-ghsp-impact)

  Measure how GitHub Secret Protection reduces secret exposure across your organization, so you can demonstrate value and identify areas to strengthen your security posture.

* [Evaluating alerts from secret scanning](/en/code-security/tutorials/remediate-leaked-secrets/evaluating-alerts)

  Learn about additional features that can help you evaluate alerts and prioritize their remediation, such as checking a secret's validity.

* [Remediating a leaked secret in your repository](/en/code-security/tutorials/remediate-leaked-secrets/remediating-a-leaked-secret)

  Learn how to respond effectively to a leaked secret in your GitHub repository.

* [Secret scanning partner program](/en/code-security/tutorials/secret-scanning-partner-program)

  As a service provider, you can partner with GitHub to have your secret token formats secured through secret scanning, which searches for accidental commits of your secret format and can be sent to a service provider's verify endpoint.

* [Evaluating default setup for code scanning](/en/code-security/tutorials/customize-code-scanning/evaluate-default-setup)

  Learn how to assess how code scanning is working for you, and how you can customize your setup to best meet your needs.

* [Preparing your code for CodeQL analysis](/en/code-security/tutorials/customize-code-scanning/prepare-code-for-analysis)

  You can build a CodeQL database containing the data needed to analyze your code.

* [Analyzing your code with CodeQL queries](/en/code-security/tutorials/customize-code-scanning/analyze-code)

  You can run queries against a CodeQL database extracted from a codebase.

* [Uploading CodeQL analysis results to GitHub](/en/code-security/tutorials/customize-code-scanning/upload-results)

  You can use the CodeQL CLI to upload CodeQL analysis results to GitHub.

* [Running CodeQL code scanning in a container](/en/code-security/tutorials/customize-code-scanning/run-in-a-container)

  You can run code scanning in a container by ensuring that all processes run in the same container.

* [Customizing analysis with CodeQL packs](/en/code-security/tutorials/customize-code-scanning/customize-analysis)

  You can use CodeQL packs to run CodeQL queries maintained by other people, or to share CodeQL queries that you've developed.

* [Creating CodeQL query suites](/en/code-security/tutorials/customize-code-scanning/create-query-suites)

  You can create query suites for queries you frequently use in your CodeQL analyses.

* [Creating and working with CodeQL packs](/en/code-security/tutorials/customize-code-scanning/create-and-work-with-codeql-packs)

  You can use CodeQL packs to create, share, depend on, and run CodeQL queries and libraries.

* [Dependabot quickstart guide](/en/code-security/tutorials/secure-your-dependencies/dependabot-quickstart)

  Find and fix vulnerable dependencies you rely on with Dependabot.

* [Automating Dependabot with GitHub Actions](/en/code-security/tutorials/secure-your-dependencies/automate-dependabot-with-actions)

  Examples of how you can use GitHub Actions to automate common Dependabot related tasks.

* [Optimizing the creation of pull requests for Dependabot version updates](/en/code-security/tutorials/secure-your-dependencies/optimizing-pr-creation-version-updates)

  Learn how to streamline and efficiently manage your Dependabot pull requests.

* [Setting up Dependabot to run on self-hosted action runners using the Actions Runner Controller](/en/code-security/tutorials/secure-your-dependencies/setting-dependabot-to-run-on-self-hosted-runners-using-arc)

  You can configure the Actions Runner Controller to run Dependabot on self-hosted runners.

* [Customizing Dependabot pull requests to fit your processes](/en/code-security/tutorials/secure-your-dependencies/customizing-dependabot-prs)

  Learn how to tailor your Dependabot pull requests to better suit your own internal workflows.

* [Customizing your dependency review action configuration](/en/code-security/tutorials/secure-your-dependencies/customize-dependency-review-action)

  Learn how to add a basic customization to your dependency review action configuration.

* [Securing your end-to-end supply chain](/en/code-security/tutorials/implement-supply-chain-best-practices/end-to-end-supply-chain-overview)

  Introducing best practice guides on complete end-to-end supply chain security including personal accounts, code, and build processes.

* [Best practices for securing accounts](/en/code-security/tutorials/implement-supply-chain-best-practices/securing-accounts)

  Guidance on how to protect accounts with access to your software supply chain.

* [Best practices for securing code in your supply chain](/en/code-security/tutorials/implement-supply-chain-best-practices/securing-code)

  Guidance on how to protect the center of your supply chain—the code you write and the code you depend on.

* [Best practices for securing your build system](/en/code-security/tutorials/implement-supply-chain-best-practices/securing-builds)

  Guidance on how to protect the end of your supply chain—the systems you use to build and distribute artifacts.

* [Prioritizing Dependabot alerts using metrics](/en/code-security/tutorials/manage-security-alerts/prioritizing-dependabot-alerts-using-metrics)

  You can prioritize Dependabot alerts in your organization by analyzing the provided metrics. Using this approach, you can tell your developers to focus on the most important vulnerabilities first.

* [Participating in a code security campaign](/en/code-security/tutorials/manage-security-alerts/best-practices-for-participating-in-a-security-campaign)

  If you've been assigned alerts as part of a security campaign, this guide explains what campaigns are, what to expect, and how to resolve alerts effectively.

* [Preventing code quality issues from reaching your default branch](/en/code-security/tutorials/improve-code-quality/catch-issues-before-merge)

  Move through Code Quality findings on your pull request, including understanding severity labels, when each finding is best fixed, delegated, or dismissed, and how those choices shape your repository's code health.

* [Raising your repository's code quality score](/en/code-security/tutorials/improve-code-quality/raise-your-quality-rating)

  Prioritize and resolve the findings that pose the most risk, raise your repository's code quality score, and prevent new debt from accumulating.

* [Collaborating in a temporary private fork to resolve a repository security vulnerability](/en/code-security/tutorials/fix-reported-vulnerabilities/collaborate-in-a-fork)

  You can create a temporary private fork to privately collaborate on fixing a security vulnerability in your public repository.

* [Best practices for writing repository security advisories](/en/code-security/tutorials/fix-reported-vulnerabilities/write-security-advisories)

  When you create or edit security advisories, the information you provide is easier for other users to understand when you specify the ecosystem, package name, and affected versions using the standard formats.

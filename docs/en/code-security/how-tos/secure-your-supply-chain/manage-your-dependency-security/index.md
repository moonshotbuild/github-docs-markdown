---
source_path: "/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security"
title: "Managing your dependency security"
intro: "Customize and configure features for dependency management."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Secure your supply chain"
    href: "/en/code-security/how-tos/secure-your-supply-chain"
  - title: "Manage your dependency security"
    href: "/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security"
---

# Managing your dependency security

Customize and configure features for dependency management.

## Links

* [Configuring open source license policies](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-license-policies)

  Create and enforce open source license policies to control which licenses your dependencies are allowed to use.

* [Customizing auto-triage rules to prioritize Dependabot alerts](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/auto-triage-dependabot-alerts)

  You can create your own auto-triage rules to control which alerts are dismissed or snoozed, and which alerts you want Dependabot to open pull requests for.

* [Using GitHub preset rules to prioritize Dependabot alerts](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/prioritize-with-preset-rules)

  Focus on alerts that matter by auto-dismissing low impact development alerts for npm dependencies.

* [Customizing pull requests for Dependabot security updates](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/customizing-dependabot-security-prs)

  Learn how to customize Dependabot pull requests for security updates to align with your project's security priorities and workflows.

* [Controlling which dependencies are updated by Dependabot](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/controlling-dependencies-updated)

  Learn how to configure your dependabot.yml file so that Dependabot automatically updates the packages you specify, in the way you define.

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

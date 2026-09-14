---
source_path: "/en/code-security/concepts/supply-chain-security"
title: "Supply chain security"
intro: "GitHub's security features help you keep track of your projects' dependencies and built artifacts."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Concepts"
    href: "/en/code-security/concepts"
  - title: "Supply chain security"
    href: "/en/code-security/concepts/supply-chain-security"
---

# Supply chain security

GitHub's security features help you keep track of your projects' dependencies and built artifacts.

## Links

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

  The dependabot.yml controls automated dependency updates in your repository.

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

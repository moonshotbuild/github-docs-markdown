---
source_path: "/en/code-security/concepts/secret-security"
title: "Concepts for secret security"
intro: "Learn core concepts for GitHub's secret security features."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Concepts"
    href: "/en/code-security/concepts"
  - title: "Secret security"
    href: "/en/code-security/concepts/secret-security"
---

# Concepts for secret security

Learn core concepts for GitHub's secret security features.

## Links

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

---
source_path: "/en/code-security/tutorials/secret-protection-adoption-path"
title: "Secure your secrets at scale with GitHub"
intro: "Leaked credentials expose your organization to data breaches. GitHub Secret Protection detects and prevents secret leaks automatically. Follow this adoption path to assess risk, pilot the solution, and scale protection organization-wide."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Tutorials"
    href: "/en/code-security/tutorials"
  - title: "Secret protection"
    href: "/en/code-security/tutorials/secret-protection-adoption-path"
---

# Secure your secrets at scale with GitHub

Leaked credentials expose your organization to data breaches. GitHub Secret Protection detects and prevents secret leaks automatically. Follow this adoption path to assess risk, pilot the solution, and scale protection organization-wide.

## Links

### Phase 1: Assess your current secret risk

* [Secret leakage risks](/en/code-security/concepts/secret-security/secret-leakage-risks)

  Secrets like API keys, passwords, and tokens committed to repositories can be exploited by unauthorized users, creating security, compliance, and financial risk to your organization.

* [Running the secret risk assessment for your organization](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/assess-your-secret-risk)

  Determine your organization's exposure to leaked secrets by generating a secret risk assessment report.

* [Interpreting secret risk assessment results](/en/code-security/tutorials/secure-your-organization/interpret-secret-risk-assessment)

  Understand the results from your secret risk assessment and prioritize leak remediation.

* [Viewing your security risk assessment reports](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/viewing-your-security-risk-assessment-reports)

  Understand your organization's exposure to leaked secrets and code vulnerabilities by viewing your most recent security risk assessment reports.

### Phase 2: Evaluate GitHub Secret Protection

* [Secret scanning](/en/code-security/concepts/secret-security/secret-scanning)

  Prevent fraudulent use of your secrets by automatically detecting exposed credentials before they can be exploited.

* [Push protection](/en/code-security/concepts/secret-security/push-protection)

  Secure your secrets by stopping them from ever reaching your repository with push protection.

* [Public monitoring for secret scanning](/en/code-security/concepts/secret-security/public-monitoring)

  Public monitoring detects credentials leaked by your enterprise members in public repositories across GitHub, giving you visibility into secret exposure beyond your enterprise's boundaries.

* [Supported secret scanning patterns](/en/code-security/reference/secret-security/supported-secret-scanning-patterns)

  Lists of supported secrets and the partners that GitHub works with to prevent fraudulent use of secrets that were committed accidentally.

* [Estimating the price of Secret Protection](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/estimate-price)

  Learn how to use the pricing calculator to estimate the monthly cost of GitHub Secret Protection for your repositories.

* [Calculating the cost savings of push protection](/en/code-security/tutorials/remediate-leaked-secrets/calculate-cost-savings)

  Estimate the remediation time and labor costs you'll avoid by preventing leaked secrets.

* [Setting up a trial of GitHub Advanced Security](/en/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security)

  You can try the full set of GitHub Advanced Security features for free.

### Phase 3: Pilot GitHub Secret Protection

* [Best practices for selecting pilot repositories](/en/code-security/concepts/security-at-scale/select-pilot-repositories)

  The right pilot repositories demonstrate value quickly and prepare your organization for broader enablement of GitHub Secret Protection.

* [Pricing and enabling GitHub Secret Protection](/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/protect-your-secrets)

  Secure your organization's secrets within your budget by enabling GitHub Secret Protection.

* [Enabling push protection for your repository](/en/code-security/how-tos/secure-your-secrets/prevent-future-leaks/enable-push-protection)

  With push protection, secret scanning blocks contributors from pushing secrets to a repository and generates an alert whenever a contributor bypasses the block.

* [Remediating a leaked secret in your repository](/en/code-security/tutorials/remediate-leaked-secrets/remediating-a-leaked-secret)

  Learn how to respond effectively to a leaked secret in your GitHub repository.

### Phase 4: Monitor and assess value

* [Assessing the impact of GitHub Secret Protection](/en/code-security/tutorials/remediate-leaked-secrets/assessing-ghsp-impact)

  Measure how GitHub Secret Protection reduces secret exposure across your organization, so you can demonstrate value and identify areas to strengthen your security posture.

* [Secret scanning push protection metrics](/en/code-security/concepts/secret-security/push-protection-metrics)

  Understand push protection's performance across your organizations.

* [Organizing remediation efforts for leaked secrets](/en/code-security/tutorials/secure-your-organization/organize-leak-remediation)

  Systematically organize and manage the remediation of leaked secrets using security campaigns and alert assignments.

* [Evaluating alerts from secret scanning](/en/code-security/tutorials/remediate-leaked-secrets/evaluating-alerts)

  Learn about additional features that can help you evaluate alerts and prioritize their remediation, such as checking a secret's validity.

* [Viewing public monitoring alerts](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-public-monitoring-alerts)

  Find out which credentials your enterprise members have exposed in public repositories across GitHub.

### Phase 5: Scale, customize, and automate

* [Applying a custom security configuration](/en/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/apply-custom-configuration)

  You can apply your custom security configuration to repositories in your organization to meet the specific security needs of those repositories.

* [Defining custom patterns for secret scanning](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/define-custom-patterns)

  Protect your unique secret types by defining custom patterns with regular expressions.

* [Enabling delegated bypass for push protection](/en/code-security/how-tos/secure-your-secrets/manage-bypass-requests/enable-delegated-bypass)

  Control who can push code containing secrets by requiring bypass approval from designated reviewers.

* [Enabling secret scanning for generic patterns](/en/code-security/how-tos/secure-your-secrets/detect-secret-leaks/enabling-secret-scanning-for-generic-patterns)

  You can enable secret scanning to detect additional potential secrets at the repository and organization levels.

* [Enabling generic secret detection for AI-detected secrets](/en/code-security/how-tos/secure-your-secrets/detect-secret-leaks/enabling-secret-scanning-for-ai-detected-secrets)

  You can enable generic secret detection for your repository or organization. Alerts for generic secrets, such as passwords, are displayed in a separate list on the secret scanning alerts page.

* [Scanning for secrets with the GitHub MCP server](/en/code-security/how-tos/use-ghas-with-ai-coding-agents/scan-for-secrets-with-github-mcp-server)

  Detect exposed secrets in real time from your AI coding agent, before they ever reach your repository.

* [Enabling public monitoring for your enterprise](/en/code-security/how-tos/secure-at-scale/configure-enterprise-security/manage-your-coverage/enabling-public-monitoring-for-your-enterprise)

  Start detecting secrets your enterprise members leak in public repositories outside your enterprise's boundaries.

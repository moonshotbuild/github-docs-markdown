---
source_path: "/en/code-security/how-tos/secure-your-secrets/customize-leak-detection"
title: "How-tos for customizing secret leak detection"
intro: "Learn how to customize GitHub's secret leak detection tools."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Secure your secrets"
    href: "/en/code-security/how-tos/secure-your-secrets"
  - title: "Customize leak detection"
    href: "/en/code-security/how-tos/secure-your-secrets/customize-leak-detection"
---

# How-tos for customizing secret leak detection

Learn how to customize GitHub's secret leak detection tools.

## Links

* [Defining custom patterns for secret scanning](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/define-custom-patterns)

  Protect your unique secret types by defining custom patterns with regular expressions.

* [Generating regular expressions for custom patterns with AI](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/generating-regular-expressions-for-custom-patterns-with-ai)

  You can use the AI-powered regular expression generator to write regular expressions for custom patterns. The generator uses an AI model to generate expressions that match your input, and optionally example strings.

* [Managing custom patterns](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/manage-custom-patterns)

  You can view, edit, and remove custom patterns, as well as enable push protection for custom patterns.

* [Excluding folders and files from secret scanning](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/exclude-folders-and-files)

  You can customize secret scanning to automatically close alerts for secrets found in specific directories or files by configuring a secret\_scanning.yml file in your repository.

* [Enabling validity checks for your repository](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/enable-validity-checks)

  Enabling validity checks on your repository helps you prioritize the remediation of alerts as it tells you if a secret is active or inactive.

* [Enabling extended metadata checks for your repository](/en/code-security/how-tos/secure-your-secrets/customize-leak-detection/enable-metadata-checks)

  Learn how to enable extended metadata checks for detected secrets so alerts detected by secret scanning include additional information that help you assess and remediate leaks faster.

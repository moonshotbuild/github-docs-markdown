---
source_path: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/automatic-build-failed"
title: "Automatic build failed for a compiled language"
intro: "If automatic build fails, you can configure code scanning to use specific build steps for compiled languages."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Code scanning"
    href: "/en/code-security/reference/code-scanning"
  - title: "Troubleshoot analysis errors"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors"
  - title: "Automatic build failed"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/automatic-build-failed"
---

# Automatic build failed for a compiled language

If automatic build fails, you can configure code scanning to use specific build steps for compiled languages.

If an automatic build of code for a compiled language within your project fails, you can try changing to the `manual` build mode or removing the `autobuild` step from your code scanning workflow and adding specific build steps. If you're not already using advanced setup, you'll need to enable it first to create a workflow you can edit.

## Further reading

* [Configuring advanced setup for code scanning](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configuring-advanced-setup-for-code-scanning).
* [CodeQL build modes](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/codeql-for-compiled-languages#codeql-build-modes)

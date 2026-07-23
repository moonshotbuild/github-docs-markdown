---
source_path: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/alerts-in-generated-code"
title: "Alerts found in generated code"
intro: "When analyzing your code with code scanning, you may wish to build only the code which you wish to analyze."
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
  - title: "Alerts in generated code"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/alerts-in-generated-code"
---

# Alerts found in generated code

When analyzing your code with code scanning, you may wish to build only the code which you wish to analyze.

When using `build-mode: autobuild` or `build-mode: manual`, for compiled languages like Java, Kotlin, Go, C, C++, and C#, CodeQL analyzes all of the code which was built during the workflow run. To limit the amount of code being analyzed, build only the code which you wish to analyze by specifying your own build steps in a `run` block. You can combine specifying your own build steps with using the `paths` or `paths-ignore` filters on the `pull_request` and `push` events to ensure that your workflow only runs when specific code is changed. For more information, see [Workflow syntax for GitHub Actions](/en/actions/reference/workflows-and-actions/workflow-syntax#onpushpull_requestpull_request_targetpathspaths-ignore).

For languages like JavaScript, Python, and TypeScript, that CodeQL analyzes without compiling the source code, or for a compiled language using `build-mode: none`, you can specify additional configuration options to limit the amount of code to analyze. For more information, see [Workflow configuration options for code scanning](/en/code-security/reference/code-scanning/workflow-configuration-options#specifying-directories-to-scan).

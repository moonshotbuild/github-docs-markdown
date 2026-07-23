---
source_path: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/unclear-what-triggered-a-workflow"
title: "Unclear what triggered a workflow run"
intro: "If you don't know what triggered an analysis, investigate the tool status page or look at the log for the last scan."
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
  - title: "Unclear what triggered a workflow"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/unclear-what-triggered-a-workflow"
---

# Unclear what triggered a workflow run

If you don't know what triggered an analysis, investigate the tool status page or look at the log for the last scan.

The tool status page shows you how well code scanning tools are working for a repository, when files in the repository were first scanned and most recently scanned, and when scans are scheduled. For integrated tools like CodeQL, you can also see more detailed information, including a percentage of files scanned and specific error messages. For more information about the tool status page, see [Use the tool status page for code scanning](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning).

You can also view the logging output from code scanning runs using GitHub Actions (CodeQL or third-party). For more information, see [Viewing code scanning logs from GitHub Actions](/en/code-security/how-tos/view-and-interpret-data/view-code-scanning-logs).

---
source_path: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/server-error"
title: "Error: \"Server error\""
intro: "If you see this error, it may be transient. Check the current GitHub Actions service status, and try running your workflow again."
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
  - title: "Server error"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/server-error"
---

# Error: "Server error"

If you see this error, it may be transient. Check the current GitHub Actions service status, and try running your workflow again.

## About this error

```text
Server error
```

If the run of a workflow for code scanning fails due to a server error, this may be due to a transient communication issue.

## Confirming the cause of the error

You can check the current "Actions" service status on the [Status Dashboard](https://www.githubstatus.com/).

## Fixing the problem

Try running the workflow again. If the problem persists, contact us through the [GitHub Support portal](https://support.github.com).

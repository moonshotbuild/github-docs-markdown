---
source_path: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/not-recognized"
title: "Error: \"is not a .ql file, .qls file, a directory, or a query pack specification\""
intro: "CodeQL was unable to locate one of the queries or sets of queries that are specified for analysis."
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
  - title: "Not recognized"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/not-recognized"
---

# Error: "is not a .ql file, .qls file, a directory, or a query pack specification"

CodeQL was unable to locate one of the queries or sets of queries that are specified for analysis.

## About this error

```text
Is not a .ql file, .qls file, a directory, or a query pack specification.
```

You will see this error if CodeQL is unable to find the named query, query suite, or query pack at the location requested in the workflow.

## Confirming the cause of the error

There are two common reasons for this error:

* There is a typo in the workflow.
* A resource the workflow refers to by path was renamed, deleted, or moved to a new location.

## Fixing the problem

After verifying the location of the resource, you can update the workflow to specify the correct location.

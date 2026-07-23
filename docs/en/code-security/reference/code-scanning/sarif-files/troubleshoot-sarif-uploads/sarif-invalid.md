---
source_path: "/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/sarif-invalid"
title: "SARIF file is invalid"
intro: "Code scanning can only process syntactically valid SARIF files. Invalid files are rejected."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Code scanning"
    href: "/en/code-security/reference/code-scanning"
  - title: "SARIF files"
    href: "/en/code-security/reference/code-scanning/sarif-files"
  - title: "Troubleshoot SARIF uploads"
    href: "/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads"
  - title: "SARIF file invalid"
    href: "/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/sarif-invalid"
---

# SARIF file is invalid

Code scanning can only process syntactically valid SARIF files. Invalid files are rejected.

## About this error

```text
Invalid SARIF
SARIF file invalid
SARIF ZIP upload is invalid
400: Bad Request if the sarif field is invalid
```

One of these errors is reported if code scanning cannot parse the SARIF file.

You are unlikely to see this error when using CodeQL analysis.

## Confirming the cause of the error

You can investigate the underlying cause of the error by looking at the log for the workflow run that uploaded the analysis and by checking the SARIF file in a validator. For more information, see [Using workflow run logs](/en/actions/how-tos/monitor-workflows/use-workflow-run-logs) and visit the [Microsoft SARIF validator](https://sarifweb.azurewebsites.net/).

## Fixing the problem

After you identify the invalid parts of the SARIF file, you may be able to resolve smaller issues manually, but you may need to talk to the maintainers of the tool. For information about validation and the format supported by code scanning, see [SARIF support for code scanning](/en/code-security/reference/code-scanning/sarif-files/sarif-support).

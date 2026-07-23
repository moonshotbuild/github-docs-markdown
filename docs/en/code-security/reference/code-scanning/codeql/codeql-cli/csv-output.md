---
source_path: "/en/code-security/reference/code-scanning/codeql/codeql-cli/csv-output"
title: "CodeQL CLI CSV output"
intro: "Understand CSV results from the CodeQL CLI."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Code scanning"
    href: "/en/code-security/reference/code-scanning"
  - title: "CodeQL"
    href: "/en/code-security/reference/code-scanning/codeql"
  - title: "CodeQL CLI"
    href: "/en/code-security/reference/code-scanning/codeql/codeql-cli"
  - title: "CSV output"
    href: "/en/code-security/reference/code-scanning/codeql/codeql-cli/csv-output"
---

# CodeQL CLI CSV output

Understand CSV results from the CodeQL CLI.

When you save analysis results from the CodeQL CLI in CSV format, each line corresponds to an alert, containing a comma-separated list with the following information:

**Property**|**Description**|**Example**
-----|-----|-----
Name | Name of the query that identified the result. | `Inefficient regular expression`
Description | Description of the query.| `A regular expression that requires exponential time to match certain inputs can be a performance bottleneck, and may be vulnerable to denial-of-service attacks.`
Severity | Severity of the query.| `error`
Message | Alert message.| `This part of the regular expression may cause exponential backtracking on strings containing many repetitions of '\\\\'.`
Path | Path of the file containing the alert. | `/vendor/codemirror/markdown.js`
Start line | Line of the file where the code that triggered the alert begins. | `617`
Start column | Column of the start line that marks the start of the alert code. Not included when equal to 1. | `32`
End line | Line of the file where the code that triggered the alert ends. Not included when the same value as the start line. | `64`
End column | Where available, the column of the end line that marks the end of the alert code. Otherwise the end line is repeated. | `617`

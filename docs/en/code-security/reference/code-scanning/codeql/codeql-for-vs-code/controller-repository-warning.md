---
source_path: "/en/code-security/reference/code-scanning/codeql/codeql-for-vs-code/controller-repository-warning"
title: "Problem with controller repository"
intro: "If you see this warning, update your controller repository to a private repository."
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
  - title: "CodeQL for VS Code"
    href: "/en/code-security/reference/code-scanning/codeql/codeql-for-vs-code"
  - title: "Controller repository warning"
    href: "/en/code-security/reference/code-scanning/codeql/codeql-for-vs-code/controller-repository-warning"
---

# Problem with controller repository

If you see this warning, update your controller repository to a private repository.

## About this warning

```text
Publicly visible controller repository can't be used to analyze private repositories. NUMBER private repositories were not analyzed.
```

If you run variant analysis on a custom list of repositories, you may receive this warning as a banner in Visual Studio Code, where NUMBER is the number of private repositories that have not been analyzed.

## Confirming the cause of the problem

When you run variant analysis, you'll see any errors and warnings displayed in the "Variant Analysis Results" view.

## Fixing the problem

To analyze private repositories, you should edit your settings to update your controller repository to a private repository. For information on how to edit the controller repository, see [Customizing settings](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/customize-settings#configuring-settings-for-variant-analysis).

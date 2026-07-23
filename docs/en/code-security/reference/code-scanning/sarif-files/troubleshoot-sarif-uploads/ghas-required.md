---
source_path: "/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/ghas-required"
title: "Upload fails because GitHub Code Security is disabled"
intro: "You can only upload SARIF results to private or internal repositories where GitHub Code Security is enabled."
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
  - title: "GitHub Code Security disabled"
    href: "/en/code-security/reference/code-scanning/sarif-files/troubleshoot-sarif-uploads/ghas-required"
---

# Upload fails because GitHub Code Security is disabled

You can only upload SARIF results to repositories where GitHub Code Security is enabled.

## About this error

```text
GitHub Code Security or GitHub Advanced Security not enabled
GitHub Code Security or GitHub Advanced Security blocked by a policy
403: GitHub Code Security or GitHub Advanced Security is not enabled
```

This error is reported if a process attempts to upload a SARIF file to a repository where GitHub Code Security is not enabled or where use of this feature is blocked by a policy.

You will only see this error for SARIF files that contain results created using CodeQL and for uploads to repositories with private or internal visibility. GitHub Code Security is enabled by default for all public repositories.

For information on how to confirm this error and fix the problem, see [Error: "GitHub Code Security or GitHub Advanced Security must be enabled for this repository to use code scanning"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/advanced-security-must-be-enabled).

---
source_path: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/create-database-bundles"
title: "Creating CodeQL CLI database bundles"
intro: "Create a database bundle with CodeQL troubleshooting information."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Find and fix code vulnerabilities"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities"
  - title: "Scan from the command line"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line"
  - title: "Create database bundles"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/create-database-bundles"
---

# Creating CodeQL CLI database bundles

Create a database bundle with CodeQL troubleshooting information.

> [!WARNING]
> CodeQL CLI database bundles contain a copy of the source code being analyzed by CodeQL, therefore we suggest sharing these bundles only with people who are authorized to access that source code.

The following CodeQL CLI command syntax is suggested when creating a database bundle for troubleshooting purposes. This sample `database bundle` command requires CodeQL CLI version 2.17.6 or higher.

```shell
codeql database bundle --output=codeql-debug-artifacts.zip --include-diagnostics --include-logs --include-results -- <dir>
```

For this command, `<dir>` must be the path to the directory where the CodeQL database was created.

The successful command execution creates a zip file called `codeql-debug-artifacts.zip` which contains CodeQL troubleshooting information. That file is the database bundle.

This command assumes that the `--log-dir` command line argument was not used for the `database create` and `database analyze` commands. When that command line argument is used, the log files created by those commands will not be included with the database bundle.

## Increasing the verbosity for `database create` and `database analyze`

If the `database create` and `database analyze` commands are not detailed enough for troubleshooting purposes, you can increase their verbosity.

Both commands support the `--verbosity` command line argument which can be set to `progress++` prior to creating a database bundle.

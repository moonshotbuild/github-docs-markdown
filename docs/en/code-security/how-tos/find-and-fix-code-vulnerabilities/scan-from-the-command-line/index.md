---
source_path: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line"
title: "Scan from the command line"
intro: "Run code scanning from the command line using the CodeQL CLI to configure scans, customize queries, and troubleshoot results."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Find and fix code vulnerabilities"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities"
  - title: "Scan from the command line"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line"
---

# Scan from the command line

Run code scanning from the command line using the CodeQL CLI to configure scans, customize queries, and troubleshoot results.

## Links

* [Setting up the CodeQL CLI](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/set-up-codeql-cli)

  To get started with the CodeQL CLI, you need to download and set up the CLI so that it can access the tools and libraries required to create and analyze databases.

* [Writing custom queries for the CodeQL CLI](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/write-custom-queries)

  You can write your own CodeQL queries to find specific vulnerabilities and errors.

* [Publishing and using CodeQL packs](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/publish-and-use-packs)

  Share or download a CodeQL pack, then analyze your CodeQL database.

* [Testing custom queries](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/test-custom-queries)

  Verify your custom CodeQL queries and catch breaking changes before they affect your code scanning results following new releases of the CodeQL CLI.

* [Testing query help files](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/test-query-help-files)

  Ensure your CodeQL query help files are valid by previewing them as Markdown.

* [Downloading CodeQL databases from GitHub](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/download-databases)

  Expand the coverage of the CodeQL CLI by adding ready-made databases.

* [Checking out the CodeQL CLI source code](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/check-out-source-code)

  Set up the CodeQL CLI directly from the source code.

* [Using incremental analysis with the CodeQL CLI](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/incremental-analysis)

  Get faster CodeQL results on pull requests by analyzing only what changed. Incremental analysis can reduce scan times by up to 10x when you run the CodeQL CLI in your own CI/CD system.

* [Specifying command options in a CodeQL configuration file](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/specify-command-options)

  Save time by adding your frequently used command options and custom CodeQL packs to a CodeQL configuration file.

* [Creating CodeQL CLI database bundles](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-the-command-line/create-database-bundles)

  Create a database bundle with CodeQL troubleshooting information.

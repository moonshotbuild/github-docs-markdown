---
source_path: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors"
title: "Troubleshooting code scanning analysis errors"
intro: "Identify and resolve errors that occur during code analysis, including build failures, incomplete scans, resource limits, and unexpected results."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Code scanning"
    href: "/en/code-security/reference/code-scanning"
  - title: "Troubleshoot analysis errors"
    href: "/en/code-security/reference/code-scanning/troubleshoot-analysis-errors"
---

# Troubleshooting code scanning analysis errors

Identify and resolve errors that occur during code analysis, including build failures, incomplete scans, resource limits, and unexpected results.

## Links

* [Alerts found in generated code](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/alerts-in-generated-code)

  When analyzing your code with code scanning, you may wish to build only the code which you wish to analyze.

* [Automatic build failed for a compiled language](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/automatic-build-failed)

  If automatic build fails, you can configure code scanning to use specific build steps for compiled languages.

* [C# compiler unexpectedly failing](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/c-sharp-compiler-unexpectedly-failing)

  If your MSBuild C# compilation is unexpectedly failing, you may need to amend your application project file.

* [Cannot enable CodeQL in a private repository](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/private-repository-enablement)

  GitHub Code Security must be enabled in order to use code scanning on private repositories.

* [Code scanning analysis takes too long](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/analysis-takes-too-long)

  You can fine tune your code scanning configuration to minimize analysis time.

* [CodeQL scanned fewer lines than expected](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/fewer-lines-scanned-than-expected)

  If CodeQL analyzed less code than you expected, you may need to use a custom build command.

* [Enabling default setup takes too long](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/default-setup-timeout)

  If you think that enabling default setup has stalled, you can restart the process.

* [Error: "GitHub Code Security or GitHub Advanced Security must be enabled for this repository to use code scanning"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/advanced-security-must-be-enabled)

  If you see this error, make sure that GitHub Code Security is enabled.

* ["Out of disk" and "Out of memory" errors](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/out-of-disk-or-memory)

  If you see one of these errors with GitHub Actions, you can try alternative runners.

* [Error: 403 "Resource not accessible by integration"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/resource-not-accessible)

  This error may be seen on pull requests created by Dependabot and can be resolved in a couple of different ways.

* [Error: "is not a .ql file, .qls file, a directory, or a query pack specification"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/not-recognized)

  CodeQL was unable to locate one of the queries or sets of queries that are specified for analysis.

* [Error: "No source code was seen during the build"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/no-source-code-seen-during-build)

  When CodeQL fails to find any source code, you need to resolve this problem to unblock code scanning analysis.

* [Error: "Server error"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/server-error)

  If you see this error, it may be transient. Check the current GitHub Actions service status, and try running your workflow again.

* [Extraction errors in the database](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/extraction-errors-in-the-database)

  You can check whether or not extraction errors affect the health of the CodeQL database created.

* [Logs are not detailed enough](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/logs-not-detailed-enough)

  Increase log verbosity and generate debugging artifacts when logs lack diagnostic detail.

* [Results are different than expected](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/results-different-than-expected)

  If your code scanning results are different than you expected, you can check which configurations are active.

* [Some languages were not analyzed with CodeQL advanced setup](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/some-languages-not-analyzed)

  If some languages were not analyzed, you can modify your code scanning workflow to add a matrix specifying the languages you want to analyze.

* [Two CodeQL workflows](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/two-codeql-workflows)

  If you see two workflows named "CodeQL", one workflow may be a pre-existing CodeQL workflow file which has been disabled by default setup.

* [Unclear what triggered a workflow run](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/unclear-what-triggered-a-workflow)

  If you don't know what triggered an analysis, investigate the tool status page or look at the log for the last scan.

* [Warning: "1 issue was detected with this workflow: git checkout HEAD^2 is no longer necessary"](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/unnecessary-step-found)

  If you see this warning, you should update your workflow to follow current best practice.

* [Warning: Detected X Kotlin files in your project that could not be processed without a build](/en/code-security/reference/code-scanning/troubleshoot-analysis-errors/kotlin-detected-in-no-build)

  CodeQL databases can be created for Java without building the code, but Kotlin files are excluded unless the code is built.

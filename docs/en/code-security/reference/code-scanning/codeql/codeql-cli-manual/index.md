---
source_path: "/en/code-security/reference/code-scanning/codeql/codeql-cli-manual"
title: "CodeQL CLI commands manual"
intro: "Reference information for the commands available in the most recent release of   CodeQL CLI."
product: "Security and code quality"
document_type: "subcategory"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Code scanning"
    href: "/en/code-security/reference/code-scanning"
  - title: "CodeQL"
    href: "/en/code-security/reference/code-scanning/codeql"
  - title: "CodeQL CLI manual"
    href: "/en/code-security/reference/code-scanning/codeql/codeql-cli-manual"
---

# CodeQL CLI commands manual

Reference information for the commands available in the most recent release of   CodeQL CLI.

> [!NOTE]
> This content describes the most recent release of the CodeQL CLI. For more information about this release, see https://github.com/github/codeql-cli-binaries/releases.
>
> To see details of the options available for this command in an earlier release, run the command with the <span style="white-space: nowrap;">`--help`</span> option in your terminal.

## Links

* [bqrs decode](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-decode)

  Convert result data from BQRS into other forms.

* [bqrs diff](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-diff)

  Compute the difference between two result sets.

* [bqrs hash](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-hash)

  [Plumbing] Compute a stable hash of a BQRS file.

* [bqrs info](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-info)

  Display metadata for a BQRS file.

* [bqrs interpret](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/bqrs-interpret)

  [Plumbing] Interpret data in a single BQRS.

* [database add-diagnostic](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-add-diagnostic)

  [Experimental] Add a piece of diagnostic information to a database.

* [database analyze](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-analyze)

  Analyze a database, producing meaningful results in the context of the
source code.

* [database bundle](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-bundle)

  Create a relocatable archive of a CodeQL database.

* [database cleanup](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-cleanup)

  Compact a CodeQL database on disk.

* [database create](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-create)

  Create a CodeQL database for a source tree that can be analyzed using
one of the CodeQL products.

* [database export-diagnostics](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-export-diagnostics)

  [Experimental] Export diagnostic information from a database for a
failed analysis.

* [database finalize](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-finalize)

  [Plumbing] Final steps in database creation.

* [database import](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-import)

  [Advanced] [Plumbing] Import unfinalized database(s) into another
unfinalized database.

* [database index-files](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-index-files)

  [Plumbing] Index standalone files with a given CodeQL extractor.

* [database init](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-init)

  [Plumbing] Create an empty CodeQL database.

* [database interpret-results](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-interpret-results)

  [Plumbing] Interpret computed query results into meaningful formats
such as SARIF or CSV.

* [database print-baseline](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-print-baseline)

  [Plumbing] Print a summary of the baseline lines of code seen.

* [database run-queries](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-run-queries)

  [Plumbing] Run a set of queries together.

* [database trace-command](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-trace-command)

  [Plumbing] Run a single command as part of a traced build.

* [database unbundle](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-unbundle)

  Extracts a CodeQL database archive.

* [database upgrade](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/database-upgrade)

  Upgrade a database so it is usable by the current tools.

* [dataset check](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-check)

  [Plumbing] Check a particular dataset for internal consistency.

* [dataset cleanup](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-cleanup)

  [Plumbing] Clean up temporary files from a dataset.

* [dataset import](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-import)

  [Plumbing] Import a set of TRAP files to a raw dataset.

* [dataset measure](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-measure)

  [Plumbing] Collect statistics about the relations in a particular
dataset.

* [dataset upgrade](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/dataset-upgrade)

  [Plumbing] Upgrade a dataset so it is usable by the current tools.

* [diagnostic add](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/diagnostic-add)

  [Experimental] [Plumbing] Add a piece of diagnostic information.

* [diagnostic export](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/diagnostic-export)

  [Experimental] Export diagnostic information for a failed analysis.

* [execute cli-server](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-cli-server)

  [Deep plumbing] Server for running multiple commands while avoiding
repeated JVM initialization.

* [execute language-server](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-language-server)

  [Plumbing] On-line support for the QL language in IDEs.

* [execute queries](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-queries)

  [Plumbing] Run one or more queries against a dataset.

* [execute query-server](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-query-server)

  [Plumbing] Support for running queries from IDEs.

* [execute query-server2](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-query-server2)

  [Plumbing] Support for running queries from IDEs.

* [execute upgrades](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/execute-upgrades)

  [Plumbing] Run upgrade scripts on an existing raw QL dataset.

* [generate extensible-predicate-metadata](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-extensible-predicate-metadata)

  [Experimental] [Deep plumbing] Report the extensible predicates
found in the given pack.

* [generate log-summary](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-log-summary)

  [Advanced] Create a summary of a structured log file.

* [generate overlay-changes](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-overlay-changes)

  [Plumbing] Generate a file that can be used for the
--overlay-changes option to
codeql database create when extracting an overlay database.

* [generate query-help](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/generate-query-help)

  Generate end-user query help from .qhelp files.

* [github merge-results](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/github-merge-results)

  [Deep plumbing] Merges multiple SARIF files into a single SARIF file.

* [github upload-results](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/github-upload-results)

  Uploads a SARIF file to GitHub code scanning.

* [pack add](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-add)

  Adds a list of QL library packs with optional version
ranges as dependencies of the current package, and then installs them.

* [pack bundle](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-bundle)

  [Plumbing] Bundle a QL library pack.

* [pack ci](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-ci)

  Install dependencies for this pack, verifying that the
existing lock file is up to date.

* [pack create](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-create)

  [Plumbing] Builds the contents of a QL package from
source code.

* [pack download](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-download)

  Download the set of qlpacks referenced by the query
spec of the command line from the registry. Packs can be provided by
name or implicitly inside of a query suite (.qls) file.

* [pack init](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-init)

  Initializes a qlpack in the specified directory.

* [pack install](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-install)

  Install dependencies for this pack.

* [pack ls](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-ls)

  [Deep plumbing] List the CodeQL packages rooted at
this directory. This directory must contain a qlpack.yml or
.codeqlmanifest.json file.

* [pack packlist](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-packlist)

  [Plumbing] Compute the set of files to be included in
a QL query pack or library pack.

* [pack publish](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-publish)

  Publishes a QL library pack to a package registry.

* [pack resolve-dependencies](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-resolve-dependencies)

  [Plumbing] Compute the set of required dependencies
for this QL pack.

* [pack upgrade](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/pack-upgrade)

  Update the dependencies for this pack to the latest
available versions.

* [query compile](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-compile)

  Compile or check QL code.

* [query decompile](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-decompile)

  [Plumbing] Read an intermediate representation of a compiled query
from a .qlo file.

* [query format](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-format)

  Autoformat QL source code.

* [query run](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/query-run)

  Run a single query.

* [resolve database](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-database)

  [Deep plumbing] Report metadata about the database.

* [resolve extensions](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-extensions)

  [Experimental] [Deep plumbing] Determine accessible extensions. This
includes machine learning models and data extensions.

* [resolve extensions-by-pack](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-extensions-by-pack)

  [Experimental] [Deep plumbing] Determine accessible extensions for
the given paths to pack roots. This includes machine learning models and
data extensions.

* [resolve extractor](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-extractor)

  [Deep plumbing] Determine the extractor pack to use for a given
language.

* [resolve files](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-files)

  [Deep plumbing] Expand a set of file inclusion/exclusion globs.

* [resolve languages](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-languages)

  List installed CodeQL extractor packs.

* [resolve library-path](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-library-path)

  [Deep plumbing] Determine QL library path and dbscheme for a query.

* [resolve library-paths](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-library-paths)

  [Deep plumbing] Determine QL library paths and dbschemes for multiple
queries.

* [resolve metadata](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-metadata)

  [Deep plumbing] Resolve and return the key-value metadata pairs from a
query source file.

* [resolve ml-models](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-ml-models)

  [Deprecated] [Experimental] [Deep plumbing] Determine accessible
machine learning models.

* [resolve packs](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-packs)

  Display a list of available CodeQL packs and their locations.

* [resolve qlpacks](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-qlpacks)

  Create a list of installed QL packs and their locations.

* [resolve qlref](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-qlref)

  [Deep plumbing] Dereferences a .qlref file to return a .ql one.

* [resolve queries](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-queries)

  [Deep plumbing] Expand query directories and suite specifications.

* [resolve ram](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-ram)

  [Deep plumbing] Prepare RAM options.

* [resolve tests](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-tests)

  [Deep plumbing] Find QL unit tests in given directories.

* [resolve upgrades](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/resolve-upgrades)

  [Deep plumbing] Determine upgrades to run for a raw dataset.

* [test accept](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/test-accept)

  Accept results of failing unit tests.

* [test extract](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/test-extract)

  [Plumbing] Build a dataset for a test directory.

* [test run](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/test-run)

  Run unit tests for QL queries.

* [version](/en/code-security/reference/code-scanning/codeql/codeql-cli-manual/version)

  Show the version of the CodeQL toolchain.

---
source_path: "/en/code-security/reference/code-quality/codeql-queries/ruby-queries"
title: "Ruby CodeQL queries for Code Quality"
intro: "Explore the queries that CodeQL uses to analyze code quality for code written in Ruby."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Code quality"
    href: "/en/code-security/reference/code-quality"
  - title: "CodeQL queries"
    href: "/en/code-security/reference/code-quality/codeql-queries"
  - title: "Ruby queries"
    href: "/en/code-security/reference/code-quality/codeql-queries/ruby-queries"
---

# Ruby CodeQL queries for Code Quality

Explore the queries that CodeQL uses to analyze code quality for code written in Ruby.

Code Quality uses the following CodeQL queries to analyze Ruby code and detect code quality issues on:

* Your **default branch**, with results shown on the repository's "Standard findings" dashboard
* **Pull requests**, with findings shown as comments made by `github-code-quality[bot]`

Copilot Autofix suggestions are provided for findings where possible.

<div class="ghd-tool rowheaders">

| Query name | Category | Severity |
| --- | --- | --- |
| [Useless assignment to local variable](https://codeql.github.com/codeql-query-help/ruby/rb-useless-assignment-to-local/) | Maintainability | Warning |
| [Database query in a loop](https://codeql.github.com/codeql-query-help/ruby/rb-database-query-in-loop/) | Reliability | Info |
| [Potentially uninitialized local variable](https://codeql.github.com/codeql-query-help/ruby/rb-uninitialized-local-variable/) | Reliability | Error |

</div>

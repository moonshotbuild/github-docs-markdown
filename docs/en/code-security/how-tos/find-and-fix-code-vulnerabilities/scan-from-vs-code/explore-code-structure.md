---
source_path: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/explore-code-structure"
title: "Exploring the structure of your source code"
intro: "Visualize how your code maps to CodeQL classes in VS Code."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Find and fix code vulnerabilities"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities"
  - title: "Scan from VS Code"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code"
  - title: "Explore code structure"
    href: "/en/code-security/how-tos/find-and-fix-code-vulnerabilities/scan-from-vs-code/explore-code-structure"
---

# Exploring the structure of your source code

Visualize how your code maps to CodeQL classes in VS Code.

## Prerequisites

To view the abstract syntax tree (AST) of a source file, you need to have an appropriate CodeQL query (usually `printAST.ql`) in your workspace. If you do not have an appropriate query, you can update your copy of the [`github/codeql`](https://github.com/github/codeql) repository from the `main` branch.

> [!NOTE] Updating your repository may discard your query caches, making your next query runs slower.

## Viewing the abstract syntax tree of a source file

1. Open the "Databases" view in the extension, and right-click the database that you want to explore. Click **Add Database Source to Workspace**.
1. Navigate to a CodeQL database's source file in the File Explorer.
1. Run **CodeQL: View AST** from the VS Code Command Palette. This runs a CodeQL query over the active file, which may take a few seconds. Once the query is complete, the AST viewer will display the structure of the source file.
1. To see the nested structure of the source file, click the arrows and expand the nodes. These nodes represent different elements of your code, such as statements and expressions.
1. To see the source code corresponding to a particular node, click the node in the AST viewer. Similarly, you can click a section of the source code to display the corresponding node.

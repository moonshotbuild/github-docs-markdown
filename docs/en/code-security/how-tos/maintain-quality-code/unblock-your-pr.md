---
source_path: "/en/code-security/how-tos/maintain-quality-code/unblock-your-pr"
title: "Resolving a block on your pull request"
intro: "Identify and resolve a code quality or coverage threshold block on your pull request so you can merge your changes."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Maintain quality code"
    href: "/en/code-security/how-tos/maintain-quality-code"
  - title: "Unblock your PR"
    href: "/en/code-security/how-tos/maintain-quality-code/unblock-your-pr"
---

# Resolving a block on your pull request

Identify and resolve a code quality or coverage threshold block on your pull request so you can merge your changes.

## Understanding why your pull request is blocked

Repository administrators and organization owners can set quality gates using GitHub Code Quality. When you open a pull request, checks automatically run to evaluate your changes against these standards.

There are two types of blocks:

* **Code quality findings**: your changes introduce issues that fall below the required quality threshold.
* **Coverage threshold**: your changes cause code coverage to fall below a required minimum, or cause coverage to drop by more than a permitted amount relative to the default branch.

These checks help maintain a healthy, maintainable codebase and prevent technical debt from accumulating.

## Resolving a code quality findings block

If your pull request introduces code that falls below the required quality threshold, you'll see a merge block banner at the bottom of the pull request in the "Checks" section: "Merging is blocked: Code quality findings were detected."

![Screenshot of the merge block banner in the Checks section of a pull request.](/assets/images/help/code-quality/code-quality-merge-block.png)

The quality gate set by your repository administrator or organization owner defines the **minimum severity level** that will block merging. All findings at that severity level or higher must be fixed or dismissed before you can merge. If the merge block banner does not specify a severity level, your repository requires **all findings** to be addressed.

To unblock your pull request, you need to fix or dismiss the findings that meet or exceed the blocking severity:

1. Review the comments left by the `github-code-quality[bot]` on your pull request. Each comment is labeled by severity (**Error**, **Warning**, **Note**).
2. Fix or dismiss the relevant findings. For detailed instructions, see [Fixing code quality findings on a pull request](/en/code-security/how-tos/maintain-quality-code/fix-pr-findings).
3. Verify the merge block banner is no longer present in the "Checks" section of your pull request.

## Resolving a coverage threshold block

If your pull request is blocked by a coverage threshold rule, you'll see a merge block banner in the "Checks" section with a message describing which threshold was not met. For example:

* "Coverage 22.0% is below minimum 50.0%": your pull request branch coverage is below the minimum coverage percentage configured in the ruleset.
* "Coverage decreased by 2.5%, maximum allowed drop is 1.0%": your changes caused coverage to drop by more than the permitted amount relative to the default branch.

To unblock your pull request, you need to add or modify tests so that more of the codebase is executed:

1. Review the coverage summary comment on your pull request to identify which files or areas lack coverage.
2. Add or update tests to increase execution coverage. Copilot can help you write and update your tests. See [Testing code](/en/copilot/tutorials/copilot-cookbook/testing-code).
3. Push your changes. The coverage check will re-run automatically.

## Next steps

* [Fixing code quality findings in your repository backlog](/en/code-security/how-tos/maintain-quality-code/fix-backlog-findings)

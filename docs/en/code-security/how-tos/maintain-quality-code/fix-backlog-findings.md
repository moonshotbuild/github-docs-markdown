---
source_path: "/en/code-security/how-tos/maintain-quality-code/fix-backlog-findings"
title: "Fixing code quality findings in your repository backlog"
intro: "Generate autofixes for findings on the default branch of your repository, or dismiss findings that aren't relevant."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Maintain quality code"
    href: "/en/code-security/how-tos/maintain-quality-code"
  - title: "Fix backlog findings"
    href: "/en/code-security/how-tos/maintain-quality-code/fix-backlog-findings"
---

# Fixing code quality findings in your repository backlog

Generate autofixes for findings on the default branch of your repository, or dismiss findings that aren't relevant.

> \[!TIP]
> If you're new to Code Quality, see [Raising your repository's code quality score](/en/code-security/tutorials/improve-code-quality/raise-your-quality-rating?utm_campaign=code-quality-ga-july-2026\&utm_medium=docs\&utm_source=docs-fix-backlog-walkthrough-tip) for a guided walkthrough of reviewing and improving your repository's quality scores.

## How Code Quality works on your default branch

Code Quality scans your default branch and reports findings on "Code quality" pages on the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-shield" aria-label="shield" role="img"><path d="M7.467.133a1.748 1.748 0 0 1 1.066 0l5.25 1.68A1.75 1.75 0 0 1 15 3.48V7c0 1.566-.32 3.182-1.303 4.682-.983 1.498-2.585 2.813-5.032 3.855a1.697 1.697 0 0 1-1.33 0c-2.447-1.042-4.049-2.357-5.032-3.855C1.32 10.182 1 8.566 1 7V3.48a1.75 1.75 0 0 1 1.217-1.667Zm.61 1.429a.25.25 0 0 0-.153 0l-5.25 1.68a.25.25 0 0 0-.174.238V7c0 1.358.275 2.666 1.057 3.86.784 1.194 2.121 2.34 4.366 3.297a.196.196 0 0 0 .154 0c2.245-.956 3.582-2.104 4.366-3.298C13.225 9.666 13.5 8.36 13.5 7V3.48a.251.251 0 0 0-.174-.237l-5.25-1.68ZM8.75 4.75v3a.75.75 0 0 1-1.5 0v-3a.75.75 0 0 1 1.5 0ZM9 10.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path></svg> Security and quality** tab of your repository. It runs **two types of analysis**.

1. **Standard findings**: Code Quality uses CodeQL to perform a deterministic, rules-based scan of your default branch. Finding are grouped by rule and language, labeled by severity (**Error**, **Warning**, **Note**), and each includes a suggested autofix.

2. **AI findings**: Code Quality uses AI-powered analysis to identify quality issues in the files most recently pushed to your default branch, including issues that rule-based analysis may not detect - such as best practices, naming conventions, or design considerations.

> \[!NOTE]
> The "AI findings" page for recently changed files is currently in public preview and subject to change.

For information on resolving AI findings, see [Fixing code quality findings in recently merged files](/en/code-security/how-tos/maintain-quality-code/fix-findings-in-recent-merges).

## Resolving standard findings

You can resolve findings individually or assign multiple findings to Copilot.

> \[!NOTE]
> Agentic Autofix for GitHub Code Quality backlog findings is currently in public preview and subject to change.

### Resolving a single finding

1. Navigate to the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-shield" aria-label="shield" role="img"><path d="M7.467.133a1.748 1.748 0 0 1 1.066 0l5.25 1.68A1.75 1.75 0 0 1 15 3.48V7c0 1.566-.32 3.182-1.303 4.682-.983 1.498-2.585 2.813-5.032 3.855a1.697 1.697 0 0 1-1.33 0c-2.447-1.042-4.049-2.357-5.032-3.855C1.32 10.182 1 8.566 1 7V3.48a1.75 1.75 0 0 1 1.217-1.667Zm.61 1.429a.25.25 0 0 0-.153 0l-5.25 1.68a.25.25 0 0 0-.174.238V7c0 1.358.275 2.666 1.057 3.86.784 1.194 2.121 2.34 4.366 3.297a.196.196 0 0 0 .154 0c2.245-.956 3.582-2.104 4.366-3.298C13.225 9.666 13.5 8.36 13.5 7V3.48a.251.251 0 0 0-.174-.237l-5.25-1.68ZM8.75 4.75v3a.75.75 0 0 1-1.5 0v-3a.75.75 0 0 1 1.5 0ZM9 10.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path></svg> Security and quality** tab of your repository.

2. Click to expand **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-code-review" aria-label="code review" role="img"><path d="M1.75 1h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 13H8.061l-2.574 2.573A1.458 1.458 0 0 1 3 14.543V13H1.75A1.75 1.75 0 0 1 0 11.25v-8.5C0 1.784.784 1 1.75 1ZM1.5 2.75v8.5c0 .138.112.25.25.25h2a.75.75 0 0 1 .75.75v2.19l2.72-2.72a.749.749 0 0 1 .53-.22h6.5a.25.25 0 0 0 .25-.25v-8.5a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25Zm5.28 1.72a.75.75 0 0 1 0 1.06L5.31 7l1.47 1.47a.751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018l-2-2a.75.75 0 0 1 0-1.06l2-2a.75.75 0 0 1 1.06 0Zm2.44 0a.75.75 0 0 1 1.06 0l2 2a.75.75 0 0 1 0 1.06l-2 2a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L10.69 7 9.22 5.53a.75.75 0 0 1 0-1.06Z"></path></svg> Code quality**, then click **Standard findings**.

3. Use the dashboard filters to focus on the findings most likely to affect your quality scores. For example, to see all "Error"-level findings for "Reliability", set the filter to:

   `is:open category:reliability severity:error`

4. Findings are grouped by rule. Click a rule name to be taken to a detailed view of all findings for that rule.

   ![Screenshot showing a rule in the "Standard findings" view. The rule name is highlighted in dark orange.](/assets/images/help/code-quality/click-rule-name.png)

5. Click **Show more**, then review the explanation of the rule, what the recommended fix is, supporting code examples and references.

   ![Screenshot showing the results for a code quality rule. The text "Show more" is highlighted in dark orange.](/assets/images/help/code-quality/click-show-more.png)

6. To the right of an individual finding, click **Assign to Copilot**. Assigning a finding to Copilot consumes AI credits.

7. Review the draft pull request that Copilot opens with a fix for the finding.

8. When the autofix pull request is ready for review, change its status from "Draft" to "Ready for review", and wait for CI checks to pass before merging.

9. Alternatively, if a finding isn't relevant or actionable, click **Dismiss**. For example, you might dismiss a finding that is in legacy code no longer maintained, is a known exception to your team's coding standards, or is a false positive that doesn't pose a real quality risk.

To raise a maintainability or reliability score, you must resolve every finding at the highest severity level currently affecting that metric. See [Metrics and scores reference](/en/code-security/reference/code-quality/metrics-and-ratings).

### Assigning multiple findings to Copilot

If you have many findings for a rule and want to remediate them efficiently, you can select these findings in bulk and assign them to Copilot for agentic remediation. Copilot will open a pull request with fixes for the selected findings.

You don't need a Copilot license to use this feature, but your enterprise owner must allow Code Quality for your organization. See [Allowing use of GitHub Code Quality in your enterprise](/en/code-security/how-tos/secure-at-scale/configure-enterprise-security/configure-specific-tools/allow-github-code-quality-in-enterprise).

For the best results, start with a single rule that has many high-severity findings. This lets you validate the quality of the autofixes on a cohesive set of changes before expanding to other rules.

1. Navigate to the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-shield" aria-label="shield" role="img"><path d="M7.467.133a1.748 1.748 0 0 1 1.066 0l5.25 1.68A1.75 1.75 0 0 1 15 3.48V7c0 1.566-.32 3.182-1.303 4.682-.983 1.498-2.585 2.813-5.032 3.855a1.697 1.697 0 0 1-1.33 0c-2.447-1.042-4.049-2.357-5.032-3.855C1.32 10.182 1 8.566 1 7V3.48a1.75 1.75 0 0 1 1.217-1.667Zm.61 1.429a.25.25 0 0 0-.153 0l-5.25 1.68a.25.25 0 0 0-.174.238V7c0 1.358.275 2.666 1.057 3.86.784 1.194 2.121 2.34 4.366 3.297a.196.196 0 0 0 .154 0c2.245-.956 3.582-2.104 4.366-3.298C13.225 9.666 13.5 8.36 13.5 7V3.48a.251.251 0 0 0-.174-.237l-5.25-1.68ZM8.75 4.75v3a.75.75 0 0 1-1.5 0v-3a.75.75 0 0 1 1.5 0ZM9 10.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0Z"></path></svg> Security and quality** tab of your repository.
2. Click to expand **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-code-review" aria-label="code review" role="img"><path d="M1.75 1h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 13H8.061l-2.574 2.573A1.458 1.458 0 0 1 3 14.543V13H1.75A1.75 1.75 0 0 1 0 11.25v-8.5C0 1.784.784 1 1.75 1ZM1.5 2.75v8.5c0 .138.112.25.25.25h2a.75.75 0 0 1 .75.75v2.19l2.72-2.72a.749.749 0 0 1 .53-.22h6.5a.25.25 0 0 0 .25-.25v-8.5a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25Zm5.28 1.72a.75.75 0 0 1 0 1.06L5.31 7l1.47 1.47a.751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018l-2-2a.75.75 0 0 1 0-1.06l2-2a.75.75 0 0 1 1.06 0Zm2.44 0a.75.75 0 0 1 1.06 0l2 2a.75.75 0 0 1 0 1.06l-2 2a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042L10.69 7 9.22 5.53a.75.75 0 0 1 0-1.06Z"></path></svg> Code quality**, then click **Standard findings**.
3. Select the findings you want to remediate. You can select up to 25 findings per page, one page at a time.
4. Click **Assign to Copilot**.

   ![Screenshot of the "Standard findings" view. The "3 of 3 selected" checkbox and the "Dismiss" and "Assign to Copilot" buttons are outlined in orange.](/assets/images/help/code-quality/assign-findings-bulk.png)
5. Copilot will open a pull request with fixes for the selected findings. Review the pull request carefully before merging.

## Verifying that your code quality scores have updated

After your autofix pull requests are merged, return to the "Standard findings" view to confirm that:

* The number of findings has decreased.
* The maintainability or reliability score has improved, if you resolved all findings at the current minimum severity level for that metric.

## Next steps

* [Fixing code quality findings in recently merged files](/en/code-security/how-tos/maintain-quality-code/fix-findings-in-recent-merges)

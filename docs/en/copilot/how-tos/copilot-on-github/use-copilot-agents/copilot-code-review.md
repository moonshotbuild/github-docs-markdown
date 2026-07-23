---
source_path: "/en/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review"
title: "Using GitHub Copilot code review on GitHub"
intro: "GitHub Copilot reviews your pull requests and suggests ready-to-apply changes, so you get fast, actionable feedback on every commit."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Copilot on GitHub"
    href: "/en/copilot/how-tos/copilot-on-github"
  - title: "Use Copilot agents"
    href: "/en/copilot/how-tos/copilot-on-github/use-copilot-agents"
  - title: "Copilot code review"
    href: "/en/copilot/how-tos/copilot-on-github/use-copilot-agents/copilot-code-review"
---

# Using GitHub Copilot code review on GitHub

GitHub Copilot reviews your pull requests and suggests ready-to-apply changes, so you get fast, actionable feedback on every commit.

Copilot code review is also available for organization members without a Copilot license, when enabled by an enterprise administrator or organization owner. See [Copilot code review for organization members without a Copilot license](/en/copilot/concepts/agents/code-review#copilot-code-review-for-organization-members-without-a-copilot-license).

## Request a review from Copilot

1. On GitHub.com, create or open a pull request.

2. Under "Reviewers" in the right sidebar, next to **Copilot**, click **Request**.

   ![Screenshot of Copilot with 'Request' button under 'Reviewers'.](/assets/images/help/copilot/code-review/request-review@2x.png)

3. Wait for Copilot to finish reviewing. This usually takes less than 30 seconds.

4. Read through Copilot's comments on the pull request.

   ![Screenshot of a code review left by Copilot.](/assets/images/help/copilot/code-review/review-comment@2x.png)

Copilot always leaves a "Comment" review, not an "Approve" or "Request changes" review. Its reviews do not count toward required approvals and will not block merging.

Copilot's review comments work like comments from human reviewers. Add reactions, reply, resolve, or hide them. Any replies you add are visible to other people but not to Copilot.

You can also request a review from Copilot through the GitHub REST API by requesting `copilot-pull-request-reviewer[bot]` as a reviewer. For more information, see [REST API endpoints for review requests](/en/rest/pulls/review-requests#request-reviewers-for-a-pull-request).

## Work with suggested changes

Copilot's feedback often includes suggested changes you can apply in a few clicks. Accept a single suggestion or group multiple suggestions into one commit. For more information, see [Incorporating feedback in your pull request](/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests/incorporating-feedback-in-your-pull-request).

To have Copilot cloud agent implement suggested changes directly:

1. Enable GitHub Copilot code review and Copilot cloud agent.
2. On a review comment from GitHub Copilot code review, click **Fix with Copilot**. This creates a draft comment where you instruct Copilot to address specific feedback. You can choose whether Copilot creates a new pull request against your branch or commits directly to the same pull request.

## Provide feedback on reviews

Rate Copilot's comments to help improve future suggestions.

1. On a review comment from Copilot, click the thumbs up (:+1:) or thumbs down (:-1:) button.

   ![Screenshot showing a Copilot code review comment with the thumbs up and thumbs down buttons.](/assets/images/help/copilot/code-review/feedback-controls@2x.png)

2. If you click thumbs down, optionally pick a reason and leave a comment, then click **Submit feedback**.

   ![Screenshot of the form for providing additional information when you give negative feedback on a comment from Copilot.](/assets/images/help/copilot/code-review/feedback-modal@2x.png)

## Request a re-review

When you push new changes to a pull request that Copilot has reviewed, it does not automatically re-review unless you've configured automatic reviews to include new pushes.

To manually request a re-review, click the <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-sync" aria-label="Re-request review" role="img"><path d="M1.705 8.005a.75.75 0 0 1 .834.656 5.5 5.5 0 0 0 9.592 2.97l-1.204-1.204a.25.25 0 0 1 .177-.427h3.646a.25.25 0 0 1 .25.25v3.646a.25.25 0 0 1-.427.177l-1.38-1.38A7.002 7.002 0 0 1 1.05 8.84a.75.75 0 0 1 .656-.834ZM8 2.5a5.487 5.487 0 0 0-4.131 1.869l1.204 1.204A.25.25 0 0 1 4.896 6H1.25A.25.25 0 0 1 1 5.75V2.104a.25.25 0 0 1 .427-.177l1.38 1.38A7.002 7.002 0 0 1 14.95 7.16a.75.75 0 0 1-1.49.178A5.5 5.5 0 0 0 8 2.5Z"></path></svg> button next to Copilot's name in the **Reviewers** menu. For more information, see [Requesting a pull request review](/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/requesting-a-pull-request-review).

To automatically request re-reviews on every push, enable automatic code review and select **Review new pushes** in the ruleset settings. For more information, see [Configuring automatic code review by GitHub Copilot](/en/copilot/how-tos/copilot-on-github/set-up-copilot/configure-automatic-review#configuring-automatic-code-review-for-repositories-in-an-organization).

When re-reviewing, Copilot may repeat previous comments, even if you resolved or downvoted them.

## Enable automatic reviews

By default, you request reviews from Copilot manually on each pull request. To enable automatic reviews for all pull requests, see [Configuring automatic code review by GitHub Copilot](/en/copilot/how-tos/copilot-on-github/set-up-copilot/configure-automatic-review).

## Customize reviews with custom instructions

You can customize Copilot code review by adding custom instructions to your repository. Repository custom instructions can either be repository wide or path specific.

Use `.github/copilot-instructions.md` for repository-wide review guidance that should apply across the entire codebase. This is a good place to describe organization-wide expectations, such as coding standards, review criteria, or general practices that Copilot should consider in every review.

Use an `AGENTS.md` file in the root of your repository to provide additional repository context that helps Copilot better understand how your project works. For example, you can explain which patterns are intentional, which parts of the codebase need closer scrutiny, and what your team considers good architecture, testing, and implementation practices. This helps make reviews more relevant and aligned with the way your team builds software.

Use `.github/instructions/**/*.instructions.md` files for path-specific instructions that only apply when reviewing matching files. This is useful when different parts of the repository follow different conventions, require specialized checks, or need review guidance tailored to a particular language, framework, or subsystem.

For more information, see [Adding repository custom instructions for GitHub Copilot](/en/copilot/how-tos/copilot-on-github/customize-copilot/add-custom-instructions/add-repository-instructions).

> \[!NOTE]
> When reviewing a pull request, Copilot reads repository custom instructions, agent instructions, and agent skills from the head branch (the branch with your changes), not the base branch. For example, when merging `my-feature-branch` into `main`, Copilot uses the instructions and skills in `my-feature-branch`, so you can test changes to them in the same pull request without merging them first.

### Example

This example of a `.github/copilot-instructions.md` file contains three instructions that will be applied to all Copilot code reviews in the repository.

```text
When performing a code review, respond in Spanish.

When performing a code review, apply the checks in the `/security/security-checklist.md` file.

When performing a code review, focus on readability and avoid nested ternary operators.
```

## MCP servers and agent skills

> \[!NOTE]
> Support for agent skills and MCP servers with Copilot code review is in public preview and subject to change.

Copilot code review can use agent skills and MCP servers configured in the repository, when they are relevant to the review.

To make these available for Copilot code review on GitHub, configure:

* **Agent skills** in your repository (in `.github/skills`). If you want a skill to target review tasks, use a review-focused skill directory name such as `code-review`. For setup details, see [Adding agent skills for GitHub Copilot](/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/add-skills).
* **MCP servers** in repository Copilot settings. The GitHub MCP server and Playwright MCP server are enabled by default. For setup details, see [Configure MCP servers for your repository](/en/copilot/how-tos/copilot-on-github/customize-copilot/configure-mcp-servers).

Copilot code review is more likely to use this context when:

* Agent skills directories have review-focused names and descriptions, such as `code-review`, that indicate they are intended for pull request review.
* Your agent skills or custom instructions explicitly tell Copilot code review to use specific MCP context.
* Pull request descriptions reference items available through configured MCP servers, such as issue keys or incident IDs.

To verify which MCP context Copilot code review used for a specific review, open the linked review session from the pull request timeline, then check the session logs to see which MCP servers and tools were called.

In repository settings, **Allow Copilot to use MCP tools when reviewing pull requests** is enabled by default. Disable this setting if you want MCP servers available only for Copilot cloud agent, and not for Copilot code review. For step-by-step instructions, see [Configure MCP servers for your repository](/en/copilot/how-tos/copilot-on-github/customize-copilot/configure-mcp-servers#disabling-mcp-tools-for-code-review).

## Further reading

* [About GitHub Copilot code review](/en/copilot/concepts/agents/code-review)
* [Review output from Copilot](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/review-copilot-output)

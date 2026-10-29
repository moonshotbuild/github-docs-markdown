---
source_path: "/en/copilot/how-tos/copilot-on-github/use-copilot-agents/manage-and-track-agents"
title: "Managing agent sessions"
intro: "Monitor an agent's progress in real time, steer it with follow-up prompts, and stop or archive sessions."
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
  - title: "Manage agent sessions"
    href: "/en/copilot/how-tos/copilot-on-github/use-copilot-agents/manage-and-track-agents"
---

# Managing agent sessions

Monitor an agent's progress in real time, steer it with follow-up prompts, and stop or archive sessions.

Use the agents panel on GitHub to monitor and manage agent sessions across your repositories.

## Monitor agent activity

Track sessions from the agents panel (available from any page on GitHub) or from your [Copilot home page](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&utm_source=managing-agent-sessions-article-product-cta\&utm_medium=docs\&utm_campaign=universe-2026). Sessions that you started, or that another user prompted Copilot to work on, appear in your sessions list.

Click a session to open the session log and overview, where you can monitor the agent's progress, token usage, and session length.

## Review session logs

Session logs show Copilot's internal reasoning and the tools it used to understand your repository, make changes, and validate its work. Copilot has its own ephemeral development environment, so it can run automated tests and linters to validate changes before pushing.

## Trace commits to session logs

Commits from Copilot cloud agent are authored by Copilot, with the person who started the task listed as co-author. Each commit message includes a link to the session logs, so you can trace why a change was made during code review or an audit. Commits are signed and appear as "Verified" on GitHub.

## Steer an agent session

If Copilot is heading in the wrong direction, or you realize your original prompt needs adjusting, you can redirect it without stopping the session.

1. Open your [Copilot home page](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&utm_source=manage-track-agents-home-1\&utm_medium=docs\&utm_campaign=universe-2026) and select the session.

2. In the prompt box below the session log, type your follow-up. For example:

   ```text
   Use our existing ErrorHandler utility class instead of writing custom try-catch blocks for each endpoint.
   ```

3. Press <kbd>Enter</kbd>. Copilot implements your input after it finishes its current tool call.

Each steering message consumes AI credits. Steering is not available for third-party coding agents.

## Continue a session from another client

Sessions that run in a cloud sandbox aren't tied to the device or client where you started them. The session, its files, and its in-progress work live in GitHub-hosted infrastructure. So you can move between clients as your day changes, without copying files, reinstalling dependencies, or explaining the task again. For more information, see [About cloud sandboxes for GitHub Copilot](/en/copilot/concepts/security-governance-and-network-settings/about-cloud-sandboxes#continue-sessions-across-clients).

Here's how a single session might move with you from your desk to your phone and back.

1. **Start in the GitHub Copilot app.** At your desk, you start a session in a cloud sandbox and describe the task. Copilot starts working in the cloud, so you can close your laptop and the session keeps running.

2. **Steer from GitHub Mobile.** On the go, you open the session on your phone to check Copilot's progress. If it's heading in the wrong direction, you send a follow-up prompt to redirect it.

3. **Review on GitHub.com.** Later, from any browser, you open the session to read the session log and check the changes Copilot made after your follow-up.

4. **Finish in Copilot CLI.** Back in your terminal, you resume the same session, with its full history and work intact, and keep working until you're ready to open a pull request.

At each step, you work with the same session. Copilot keeps the conversation and the work so far, so each client picks up where the last one left off.

### Find your sessions in each client

* **GitHub.com**: Go to [github.com/copilot](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&utm_source=manage-track-agents-home-2\&utm_medium=docs\&utm_campaign=universe-2026). Your most recent sessions are listed under "Pick up where you left off." To see all your sessions, click **View all**.
* **GitHub Mobile**: Tap **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> Copilot** in the bottom-right corner. Your sessions are listed under "Agent sessions."
* **Copilot CLI**: Open the **Sessions** tab, or enter `/resume` in an interactive session. Cloud sessions appear alongside your local sessions. For more information, see [Working with multiple GitHub Copilot CLI sessions](/en/copilot/how-tos/copilot-cli/use-copilot-cli/work-with-multiple-sessions).
* **GitHub Copilot app**: Your sessions appear in the sidebar. Click a session to open it.

## Stop a session

If the task no longer needs to be done, or you want to start over with a new prompt, click **Stop session** in the session log viewer. Stopping a session ends the GitHub Actions run and preserves any commits already pushed.

## Archive sessions

Archive stopped sessions to remove them from your sessions list.

1. Open the stopped session.
2. Click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="More actions" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg>**, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-inbox" aria-label="inbox" role="img"><path d="M2.8 2.06A1.75 1.75 0 0 1 4.41 1h7.18c.7 0 1.333.417 1.61 1.06l2.74 6.395c.04.093.06.194.06.295v4.5A1.75 1.75 0 0 1 14.25 15H1.75A1.75 1.75 0 0 1 0 13.25v-4.5c0-.101.02-.202.06-.295Zm1.61.44a.25.25 0 0 0-.23.152L1.887 8H4.75a.75.75 0 0 1 .6.3L6.625 10h2.75l1.275-1.7a.75.75 0 0 1 .6-.3h2.863L11.82 2.652a.25.25 0 0 0-.23-.152Zm10.09 7h-2.875l-1.275 1.7a.75.75 0 0 1-.6.3h-3.5a.75.75 0 0 1-.6-.3L4.375 9.5H1.5v3.75c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25Z"></path></svg> Archive session**.
3. In the dialog, click **Yes, archive**.

Copilot cloud agent sessions can be archived but not deleted. Only local sessions (from GitHub Copilot CLI, VS Code, JetBrains, or the GitHub Copilot app) can be deleted. For more information about deleting sessions, see [About GitHub Copilot session data](/en/copilot/concepts/security-governance-and-network-settings/session-data#deleting-session-data).

## Share a session

Copilot cloud agent sessions are **shared** by default. They appear in the "All sessions" view on the "Agents" tab of your repository, visible to anyone with access to the repository.

Local sessions (from GitHub Copilot CLI, VS Code, JetBrains, or the GitHub Copilot app) are **unshared** by default. You can choose to share a local session from the "Agents" tab of your repository, giving view-only access to repository collaborators. To share or unshare a local session, use the sharing controls in the session's menu.

Recipients can view the session's prompts, responses, and file changes, but cannot steer or modify the session. Shared local sessions appear in the "All sessions" view but are not indexed for other users' session queries (they will not appear in another user's `/chronicle` results).

For more information about session syncing, see [About GitHub Copilot session data](/en/copilot/concepts/security-governance-and-network-settings/session-data#session-syncing).

## Query past sessions

You can search your session history by asking natural language questions in Copilot Chat in VS Code, JetBrains, the GitHub Copilot app, or GitHub.com. Copilot searches across your synced sessions from Copilot CLI, Copilot cloud agent, and Copilot code review to provide answers.

You can only query sessions that you started. Your session data is private by default, but you can choose to share individual sessions for view-only access. See [Share a session](#share-a-session) earlier in this article.

### Prerequisites

Your sessions must be synced to your GitHub account. By default, session data is synced automatically. If you have opted out of syncing (by setting `"remoteExport": false` in your CLI settings JSON), or if your organization has not enabled the "Store local sessions in the Cloud" policy, session querying is not available. For more information, see [About GitHub Copilot session data](/en/copilot/concepts/security-governance-and-network-settings/session-data#session-syncing).

### Example queries

```text
What agent tasks did I run last week?
```

```text
Find the session where I refactored authentication.
```

```text
Have I worked on anything related to the payments API?
```

```text
Show me sessions where the agent struggled or I had to correct it multiple times.
```

Copilot can search across your prompts, responses, file changes, and other context from your synced sessions.

For CLI-specific session querying and `/chronicle` commands, see [Using GitHub Copilot CLI session data](/en/copilot/how-tos/copilot-cli/use-copilot-cli/chronicle). For conceptual information about how session data is stored and synced, see [About GitHub Copilot session data](/en/copilot/concepts/security-governance-and-network-settings/session-data).

## Further reading

* [Best practices for using GitHub Copilot to work on tasks](/en/copilot/tutorials/cloud-agent/get-the-best-results)

---
source_path: "/en/copilot/get-started/quickstart-copilot-app"
title: "Getting started with the GitHub Copilot app"
intro: "Sign in to the GitHub Copilot app, connect a repository or local folder, and create your first agent session to make code changes."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "Get started"
    href: "/en/copilot/get-started"
  - title: "Copilot app quickstart"
    href: "/en/copilot/get-started/quickstart-copilot-app"
---

# Getting started with the GitHub Copilot app

Sign in to the GitHub Copilot app, connect a repository or local folder, and create your first agent session to make code changes.

For a conceptual overview of the GitHub Copilot app, see [GitHub Copilot app](/en/copilot/concepts/copilot-surfaces/github-copilot-app).

In this quickstart, you will:

1. Install and sign in to the GitHub Copilot app.
2. Connect a repository or local folder.
3. Make code changes in an agent session.

## Prerequisites

* A GitHub account.
* A Copilot plan, or you can configure your own model provider.
  * If you use your own model provider, you will need provider credentials such as an API key. For setup steps, see [Adding LLM models to the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/add-llm-models).
* [Git](https://github.com/git-guides/install-git?utm_source=get-started-app-doc-install-git-guide\&utm_medium=docs\&utm_campaign=universe-2026) installed on your computer.

> [!NOTE]
> For Copilot Business and Copilot Enterprise users, the GitHub Copilot app policy must remain enabled. This policy is enabled by default and is separate from the Copilot CLI policy. See [Managing policies and features for GitHub Copilot in your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies) or [Managing policies and features for GitHub Copilot in your enterprise](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies).

## Installing the GitHub Copilot app

Download and install the GitHub Copilot app for your operating system. For other operating systems and architectures, see the [download page](https://github.com/features/ai/github-app?utm_source=get-started-app-doc-app-features\&utm_medium=docs\&utm_campaign=universe-2026).

<a href="https://github.com/features/ai/github-app?utm_source=app-download-docs&utm_medium=docs&utm_campaign=universe-2026" target="_blank" class="btn btn-primary mt-3 mr-3 no-underline js-os-download" data-os-download-mac="https://gh.io/copilot-app-mac" data-os-download-mac-intel="https://gh.io/copilot-app-mac-intel" data-os-download-windows="https://gh.io/copilot-app-win64" data-os-download-windows-arm="https://gh.io/copilot-app-win-arm" data-os-download-linux="https://gh.io/copilot-app-linux" data-os-download-linux-arm="https://github.com/github/app/releases/latest/download/GitHub-Copilot-linux-arm64.AppImage"><svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-desktop-download" aria-label="desktop download icon" role="img"><path d="m4.927 5.427 2.896 2.896a.25.25 0 0 0 .354 0l2.896-2.896A.25.25 0 0 0 10.896 5H8.75V.75a.75.75 0 1 0-1.5 0V5H5.104a.25.25 0 0 0-.177.427Z"></path><path d="M1.573 2.573a.25.25 0 0 0-.073.177v7.5a.25.25 0 0 0 .25.25h12.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25h-3a.75.75 0 1 1 0-1.5h3A1.75 1.75 0 0 1 16 2.75v7.5A1.75 1.75 0 0 1 14.25 12h-3.727c.099 1.041.52 1.872 1.292 2.757A.75.75 0 0 1 11.25 16h-6.5a.75.75 0 0 1-.565-1.243c.772-.885 1.192-1.716 1.292-2.757H1.75A1.75 1.75 0 0 1 0 10.25v-7.5A1.75 1.75 0 0 1 1.75 1h3a.75.75 0 0 1 0 1.5h-3a.25.25 0 0 0-.177.073ZM6.982 12a5.72 5.72 0 0 1-.765 2.5h3.566a5.72 5.72 0 0 1-.765-2.5H6.982Z"></path></svg> <span class="js-os-download-label">Download the GitHub Copilot app</span></a>

## Opening the GitHub Copilot app for the first time

1. Open the GitHub Copilot app.
2. Click **Sign in to GitHub** and follow the prompts to authenticate.

   If you use GitHub Enterprise Cloud with data residency, choose **Use GitHub Enterprise** and enter your `*.ghe.com` hostname when prompted. GitHub Enterprise Server is not supported by the GitHub Copilot app.
3. If you do not have a Copilot plan, choose whether to sign up for a plan or continue with your own model provider.
   * If you choose to use your own model provider, select a provider, enter any required credentials, then click **Save and continue**.
4. When prompted, select one or more repositories based on your recent GitHub activity. You can also add a local folder or repository, or skip this step and add repositories later.
5. Choose a theme, then complete onboarding to open the app.

## Connecting a repository or folder

To work on code, you need at least one repository or local folder connected to the app. You can connect a folder already on your machine, including a repository you've already cloned locally, or a repository you clone from GitHub or another remote Git host such as Azure DevOps. Connecting a repository or folder unlocks the core app workflow: reading code, making edits, and opening pull requests from agent sessions. If you skipped repository setup during onboarding, or want to add more repositories or folders later:

1. In the sidebar, next to **Sessions**, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="New" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg>.
2. Choose where to add the repository or folder from:

* **Open local folder** — Select a folder already on your machine, including one that contains a repository you've already cloned locally.
* **Add GitHub repository** — Browse and clone a repository from GitHub.
* **Clone repository** — Clone from a Git URL for repositories hosted outside GitHub (for example, on Azure DevOps) or for private repositories without app access.

## Making your first code changes

1. In the sidebar, next to **Sessions**, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="New" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg>, then select the connected repository or folder under "Start session in."

2. Select a session mode from the dropdown below the prompt field—for example, **Interactive** to work collaboratively with the agent.

3. In the prompt box, paste this prompt:

   ```copilot copy
   Suggest a small low-risk code change in this repository, implement it, and explain the diff.
   ```

4. Respond to any requests for input from the agent. After the agent makes changes, click **Changes** above the prompt box to view the diff.

5. Continue iterating in the same session until you are happy with the result.

6. If you want to keep the change, click **Create PR** to open a pull request for review.

7. If you create a pull request, click **PR** above the prompt box to view it directly in the app.

**Optional:** If you already have tasks you want to complete in your repository, click **Issues** in the sidebar to find an issue and start a session from it. For more information, see [Managing issues and pull requests with the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/managing-issues-and-pull-requests).

## Orienting yourself

The sidebar gives you access to the main areas of the app:

* **New** — Start a new agent session.
* **Pull requests** — Browse pull requests, check CI status, and leave reviews.
* **Issues** — Browse issues and start agent sessions to work on them.
* **[Automations](https://github.com/copilot/app/launch?open=ghapp%3A%2F%2Fautomations\&utm_source=get-started-app-doc-app-launch-my-automations-cta\&utm_medium=docs\&utm_campaign=universe-2026)** — Saved agent tasks that run on a schedule or on demand.
* **Customize** — Discover and manage plugins, skills, MCP servers, and canvases.
* **Search** — Search across your repositories directly from the app.
* **Projects** — Organize ongoing work with Copilot. Within a project, you can start multiple sessions across repositories, track progress, share context, review artifacts, and set up recurring tasks. See [Working with projects in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/working-with-projects).
* **Sessions** — View connected repositories, local folders, and their active agent sessions, or start a new session for a repository or folder.
* **Chats** — General conversations that do not require a dedicated branch or workspace.

## Next steps

Find out more about using the GitHub Copilot app:

* [Working with agent sessions in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/agent-sessions)
* [Working with canvas extensions in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/working-with-canvas-extensions)
* [Managing issues and pull requests with the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/managing-issues-and-pull-requests)
* [Using automations in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/using-automations)
* [Slash commands for the GitHub Copilot app](/en/copilot/reference/github-copilot-app-reference/slash-commands)
* [Built-in skills for the GitHub Copilot app](/en/copilot/reference/github-copilot-app-reference/built-in-skills)

---
source_path: "/en/integrations/how-tos/teams/integrate-github-with-teams"
title: "Integrating GitHub with Teams"
intro: "Set up the GitHub integration with Teams to improve collaboration and streamline workflows."
product: "Integrations"
document_type: "article"
breadcrumbs:
  - title: "Integrations"
    href: "/en/integrations"
  - title: "How-tos"
    href: "/en/integrations/how-tos"
  - title: "Teams"
    href: "/en/integrations/how-tos/teams"
  - title: "Integrate GitHub with Teams"
    href: "/en/integrations/how-tos/teams/integrate-github-with-teams"
---

# Integrating GitHub with Teams

Set up the GitHub integration with Teams to improve collaboration and streamline workflows.

## About the GitHub integration for Teams

The GitHub integration for Microsoft Teams gives you and your teams visibility into your GitHub projects directly in Teams channels. You can work with Copilot cloud agent to research, plan and triage in conversations, create artifacts such as issues and pull requests, start and steer agent sessions, and keep track of changes without leaving Teams.

With the GitHub integration for Teams, you can:

* Get **GitHub notifications** in Teams channels.

* Use **commands** to take actions on GitHub.

* See **previews** when sharing links to GitHub resources.

* **Delegate tasks to Copilot** by replying to a notification and @mentioning GitHub.

* **Initiate and steer Copilot cloud agent sessions** in a conversation. Teammates can collaborate with each other and the agent, add context, correct assumptions, continue an agent task, and review the resulting plan, issues, pull requests and other artifacts. You can also choose a model, connect MCP servers, and work across multiple repositories in a single session. You can follow the plan, changes, and pull request in a canvas without leaving Teams. Copilot Memory can retain context across sessions and is in public preview.

The combined **GitHub** app includes repository notifications and Copilot. If you already use **GitHub Notifications**, update it to the combined app. Your existing subscriptions and scheduled reminders are preserved.

When you grant the GitHub app access to your Teams workspace, you are granting it certain permissions. The permissions provided are necessary for the app to function correctly and provide the features you expect. See [Permissions for GitHub in Teams](/en/integrations/reference/teams-permissions).

## Prerequisites

To use the GitHub integration for Teams, you need:

* A GitHub account.

* A Teams workspace where you have permission to install apps.

* If you get Copilot through an organization or enterprise, including an enterprise with managed users, the Copilot cloud agent policy is enabled by default, but an owner can turn it off. Copilot runs your Teams sessions in a cloud sandbox, which doesn't need a separate setting. See [Managing cloud sandboxes for your organization or enterprise](/en/copilot/how-tos/cloud-and-local-sandboxes/enabling-or-disabling-cloud-sandboxes-for-your-organization).

## Installing the GitHub integration for Teams in a single workspace

1. Go to the [GitHub integration for Teams](https://teams.microsoft.com/l/app/ca9e26b7-dce5-44a0-b2b7-a70a3d65ce25) listing in the Teams app store.
2. Click **Add**.
3. Follow the prompts to sign in to Teams and approve access.
4. In a Teams message or channel, @mention the app by typing `@GitHub` and follow the prompts to connect your GitHub account.
5. To see what else you can do, in the thread, @mention the app by typing `@GitHub help`.

### Choosing what to configure next

* To receive repository events, use `@GitHub subscribe OWNER/REPO`. See [Customizing notifications for GitHub in Teams](/en/integrations/how-tos/teams/customize-notifications).

* To choose default repositories for a channel, use `@GitHub settings`.

* To start a task, mention `@GitHub` and describe the work. In a personal chat, name the repositories in your prompt.

Notification subscriptions, review reminders, and Copilot repository settings are separate. For multi-repository sessions, models, MCP servers, and Copilot Memory, see [Integrating Copilot cloud agent with Teams](/en/copilot/how-tos/copilot-integrations/integrate-cloud-agent-with-teams).

## Further reading

* [Using GitHub in Teams](/en/integrations/how-tos/teams/use-github-in-teams) - Learn how to use the GitHub integration for Teams.

* [Customizing notifications for GitHub in Teams](/en/integrations/how-tos/teams/customize-notifications) - Learn how to customize your GitHub notifications in Teams.

* [Integrating Copilot cloud agent with Teams](/en/copilot/how-tos/copilot-integrations/integrate-cloud-agent-with-teams) - Learn about Copilot cloud agent with Teams.

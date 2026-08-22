---
source_path: "/en/integrations/how-tos/teams/use-github-in-teams"
title: "Using GitHub in Teams"
intro: "Learn how to use GitHub in Teams to improve collaboration and streamline your workflow."
product: "Integrations"
document_type: "article"
breadcrumbs:
  - title: "Integrations"
    href: "/en/integrations"
  - title: "How-tos"
    href: "/en/integrations/how-tos"
  - title: "Teams"
    href: "/en/integrations/how-tos/teams"
  - title: "Use GitHub in Teams"
    href: "/en/integrations/how-tos/teams/use-github-in-teams"
---

# Using GitHub in Teams

Learn how to use GitHub in Teams to improve collaboration and streamline your workflow.

The GitHub integration for Microsoft Teams lets you connect your GitHub account to the GitHub app in Teams. Once connected, you can subscribe to notifications, run commands, and collaborate on issues and pull requests directly within Teams.

You can also use the GitHub integration to initiate and steer Copilot cloud agent sessions in a conversation, including asking Copilot to perform deep research, planning and triage tasks within a thread. Teammates can collaborate with each other and the agent, add context, correct assumptions, continue an agent task, and review the resulting artifacts.

> \[!NOTE]
>
> * GitHub Copilot in Teams is currently in public preview and subject to change.

## Connecting your GitHub account to the GitHub app in Teams

> \[!NOTE] Before you can connect your accounts, an admin for your Teams workspace must have installed the GitHub app. See [Integrating GitHub with Teams](/en/integrations/how-tos/teams/integrate-github-with-teams).

1. In Teams, open a direct message or personal app conversation with the GitHub app.
2. Run `@GitHub` and follow the prompts in Teams and in your browser to authorize the connection.

Once your GitHub account is connected, Teams will show you a list of available commands and features.

## Using commands for notifications in Teams

In channels, start commands with `@GitHub`. In the personal app, omit the prefix. For the full list of commands, see [Command reference for the GitHub integration in Teams](/en/integrations/reference/teams-command-reference).

| Command                           | Description                                                                    |
| --------------------------------- | ------------------------------------------------------------------------------ |
| `@GitHub subscribe OWNER/REPO`    | Subscribes the channel to notifications for the specified repository.          |
| `@GitHub unsubscribe OWNER/REPO`  | Unsubscribes the channel from notifications for the specified repository.      |
| `@GitHub subscribe list`          | Lists all repositories the channel is subscribed to.                           |
| `@GitHub subscribe list features` | Lists all repositories and notification features the channel is subscribed to. |

> \[!NOTE] When you subscribe a channel to a repository, you may be prompted to install the GitHub app and grant access to the repository or organization.

## Working with issues and pull requests

You can create, comment on, and manage issues and pull requests directly from Teams with or without using Copilot.

To have Copilot perform an action, @mention the app in any Teams chat by typing `@GitHub` followed by your task, and see [Initiating Copilot cloud agent sessions within Teams](#initiating--data-variablescopilotcopilot_cloud_agent--sessions-within-teams) below.

> \[!NOTE]
> Pull requests created in a shared context by Copilot use the app's identity. If you use repository rulesets, because these pull requests aren't attributed to a person, one more approval is required before merging, as long as the repository already requires at least one approval. This is enabled by default. See [Available rules for rulesets](/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets#additional-approval-for-unattributed-copilot-pull-requests).

For step-by-step instructions to work with issues and pull requests independent of Copilot, see [Creating issues with the GitHub integration in Teams](/en/integrations/tutorials/teams/create-issues) and [Managing issues with the GitHub integration in Teams](/en/integrations/tutorials/teams/manage-issues).

## Mentions in Teams

When you subscribe to a repository in Teams, you will see yourself mentioned in notifications for repository events in which you have been referenced. Mentions require you to be logged in to your GitHub account through the GitHub app in Teams.

> \[!NOTE] If you have multiple Teams workspaces where you use the GitHub app, mentions will only work in the workspace where you logged in most recently.

The following are scenarios in which you will be mentioned:

* You are assigned to an issue.
* Your review is requested on a pull request.
* You are mentioned in a pull request, issue description, comment, or discussion.
* Your review is requested on a deployment.
* You receive a scheduled reminder for a pull request review request.

## Threading conversations

Notifications for each issue or pull request are grouped into a thread in Teams. The parent card shows the latest status of the issue or pull request along with context such as assignees, reviewers, labels, and checks. When the state of an issue or pull request changes, Teams posts the update as a reply in the thread and as a channel message.

## Unfurling links to GitHub activities in Teams

Link previews provide additional context when sharing links to GitHub resources in Teams. Link previews are shown for:

* Pull requests
* Issues
* Discussions
* Comments
* Code snippets
* Repositories
* User accounts or organizations

Previews of links will not be shown if any of the following apply:

* The repository is private and the user who shared the link is not signed in to GitHub in Teams.
* The GitHub app has not been authorized for the repository.

## Personal app experience

The GitHub personal app in Teams lets you manage subscriptions and receive notifications in a private chat. In the personal app, commands do not require the `@GitHub` prefix and notifications are not threaded.

## Scheduling reminders for pull request reviews

You can schedule reminders for pending pull request reviews in channels or in the personal app. For instructions, see [Scheduling pull request reminders in Teams](/en/integrations/how-tos/teams/schedule-reminders).

## Initiating Copilot cloud agent sessions within Teams

The GitHub app integrates Copilot cloud agent into Teams. You can summon Copilot cloud agent in threads where discussions are taking place and ask it to make changes based on the context of those discussions.

Use Copilot in direct messages, threads, and channels. Besides creating issues, pull requests and other artifacts, working with Copilot in Teams allows you to:

* Move directly from discussion to investigation and implementation.
* Ask questions and investigate failures.
* Plan work before implementation.
* Collaboratively steer an agent with teammates.
* Delegate work from any device.
* Let tasks run asynchronously.
* Review the resulting work in the open.
* Resume work on the agent-generated artifacts outside of Teams, in GitHub, the terminal, or your preferred code editor.

For more information, see [Integrating Copilot cloud agent with Teams](/en/copilot/how-tos/use-copilot-agents/cloud-agent/integrate-cloud-agent-with-teams).

## Feedback and support

You can view and share feedback in our [discussion forum](https://github.com/orgs/community/discussions/205453).

## Further reading

* [Customizing notifications for GitHub in Teams](/en/integrations/how-tos/teams/customize-notifications) - Learn how to customize your GitHub notifications in Teams.
* [Scheduling pull request reminders in Teams](/en/integrations/how-tos/teams/schedule-reminders) - Learn how to schedule reminders for pull request reviews.
* [Command reference for the GitHub integration in Teams](/en/integrations/reference/teams-command-reference) - Review all available Teams commands.
* [Tutorials for the GitHub Teams integration](/en/integrations/tutorials/teams) - Build skills and knowledge about the GitHub Teams integration through examples and hands-on activities.

---
source_path: "/en/integrations/how-tos/slack/integrate-github-with-slack"
title: "Integrating GitHub with Slack"
intro: "Learn how to integrate GitHub with Slack to improve collaboration and streamline workflows."
product: "Integrations"
document_type: "article"
breadcrumbs:
  - title: "Integrations"
    href: "/en/integrations"
  - title: "How-tos"
    href: "/en/integrations/how-tos"
  - title: "Slack"
    href: "/en/integrations/how-tos/slack"
  - title: "Integrate GitHub with Slack"
    href: "/en/integrations/how-tos/slack/integrate-github-with-slack"
---

# Integrating GitHub with Slack

Learn how to integrate GitHub with Slack to improve collaboration and streamline workflows.

## About the GitHub integration for Slack

The GitHub integration for Slack gives you and your teams full visibility into your GitHub projects directly in Slack channels. You can work with Copilot cloud agent to research, plan and triage in conversations, create artifacts such as issues and pull requests, start and steer agent sessions, and keep track of changes without leaving Slack.

With the GitHub integration for Slack, you can:

* Get **GitHub notifications** in Slack channels.

* Use **slash commands** to take actions on GitHub.

* Give your team **context** when sharing links to GitHub activities and properties.

* **Initiate and steer Copilot cloud agent sessions** in a conversation. Teammates can collaborate with each other and the agent, add context, correct assumptions, continue an agent task, and review the resulting plan, issues, pull requests and other artifacts.

  > \[!NOTE]
  >
  > * This feature is currently in public preview and subject to change.

When you grant the GitHub app access to your Slack workspace, you are granting it certain permissions. The permissions provided are necessary for the app to function correctly and provide the features you expect. See [Permissions for GitHub in Slack](/en/integrations/reference/slack-permissions).

## Prerequisites

To use the GitHub integration for Slack, you need:

* A GitHub account.

* A Slack workspace where you have permission to install apps.

* To use Copilot cloud agent, you must have cloud sandboxes enabled for your Copilot plan. See [Cloud sandboxing for GitHub Copilot](/en/copilot/concepts/about-cloud-and-local-sandboxes#cloud-sandboxing).

  > \[!NOTE]
  > Cloud sandbox policies share the same configuration as Copilot cloud agent policies. Members of an organization or enterprise, including an enterprise with managed users may need their owner to enable cloud sandboxes and Copilot cloud agent before they can use Copilot in Slack. See [Enabling or disabling cloud sandboxes for your organization or enterprise](/en/copilot/how-tos/cloud-and-local-sandboxes/enabling-or-disabling-cloud-sandboxes-for-your-organization).

## Installing the GitHub integration for Slack in a single workspace

The GitHub integration for Slack only needs to be installed once per workspace, and can be installed by anyone with admin permissions in the Slack workspace.

1. Go to the [GitHub integration for Slack](https://slack.github.com/) page.
2. Click **Add to Slack**.
3. If you're not already signed in to Slack, you'll be prompted to do so.
4. Follow the prompts on screen to allow GitHub access to your Slack workspace.
5. Once the integration is installed, you can invite the GitHub app to specific channels by typing `/invite @github` in the desired channel.
6. Also once the integration is installed, to work with Copilot cloud agent, @mention the app by typing `@GitHub` in a Slack message or channel. Then, if prompted, connect your GitHub account.

To see what else you can do with Copilot, in the thread, @mention the app by typing `@GitHub help`.

## Installing the GitHub integration for Slack on the Slack Enterprise Grid

If you are an admin or owner of a Slack Enterprise Grid organization, you can install the GitHub integration for Slack across multiple workspaces in your organization.

1. In your Slack Enterprise Grid settings, under "Integrations", click **Install apps**.
2. Search for the GitHub app.
3. Click the ellipsis (**...**) to the right of the GitHub app and select **Add to more workspaces**.
4. Follow the prompts on screen to complete the installation.

## Further reading

* [Using GitHub in Slack](/en/integrations/how-tos/slack/use-github-in-slack) - Learn how to use the GitHub integration for Slack.

* [Integrating Copilot cloud agent with Slack](/en/copilot/how-tos/use-copilot-agents/cloud-agent/integrate-cloud-agent-with-slack) - Learn about Copilot cloud agent with Slack.

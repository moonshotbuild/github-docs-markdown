---
source_path: "/en/copilot/how-tos/use-copilot-agents/cloud-agent/create-automations"
title: "Creating automations with Copilot cloud agent"
intro: "Create and manage automations to run Copilot cloud agent on a schedule, in response to events in a repository, or programmatically via the API."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Use Copilot agents"
    href: "/en/copilot/how-tos/use-copilot-agents"
  - title: "Copilot cloud agent"
    href: "/en/copilot/how-tos/use-copilot-agents/cloud-agent"
  - title: "Create cloud automations"
    href: "/en/copilot/how-tos/use-copilot-agents/cloud-agent/create-automations"
---

# Creating automations with Copilot cloud agent

Create and manage automations to run Copilot cloud agent on a schedule, in response to events in a repository, or programmatically via the API.

## Introduction

With automations, you can set up Copilot cloud agent to run automatically, either on a schedule, in response to an event in a repository or triggered via the API. Automations can take action within the repository where they are configured, such as opening a pull request or labeling an issue.

You can create and manage automations from the **Agents** tab of a repository on GitHub.

You can also create and manage automations from:

* The **Automations** tab in the GitHub Copilot app
* The **Agents** window in VS Code
* The REST API

For an overview of automations, including triggers, tools, visibility, and security, see [Copilot automations](/en/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/about-automations).

## Prerequisites

For automations to be available in a repository, all of the following must be true:

* The repository must be **private or internal**. Automations are not available in public repositories.
* Copilot cloud agent must be enabled for the repository. If you have Copilot Business or Copilot Enterprise, an administrator must enable the Copilot cloud agent policy. See [Managing GitHub Copilot in the cloud for your enterprise or organization](/en/copilot/concepts/enterprise/cloud-agent-access).
* The organization must allow both Copilot cloud agent and automations in the repository (both are enabled by default). See [Managing GitHub Copilot in the cloud for your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/add-copilot-cloud-agent).

Automations are available with the GitHub Copilot Pro, GitHub Copilot Pro+, GitHub Copilot Max, GitHub Copilot Business, and GitHub Copilot Enterprise plans.

### Enabling cloud automations in VS Code

To use cloud automations from VS Code, complete the repository prerequisites above, then:

1. Update to VS Code 1.144 or later.
2. In the Settings editor, enable `chat.automations.cloud.enabled`.
3. Open the **Agents** window, then select the **Automations** tab.

For creation and management instructions, see [Create and manage agent automations](https://code.visualstudio.com/docs/agents/run/automations) in the VS Code documentation.

## Creating an automation

> [!WARNING]
> The Copilot cloud agent sessions started by an automation are visible to others with access to the repository. Don't include secrets or other sensitive information in your prompt. To give Copilot access to sensitive values, use repository secrets. See [Configure secrets and variables for Copilot cloud agent](/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/configure-secrets-and-variables).

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-agent" aria-label="agent" role="img"><path d="M14.5 8.9v-.052A2.956 2.956 0 0 0 11.542 5.9a.815.815 0 0 1-.751-.501l-.145-.348A3.496 3.496 0 0 0 7.421 2.9h-.206a3.754 3.754 0 0 0-3.736 4.118l.011.121a.822.822 0 0 1-.619.879A1.81 1.81 0 0 0 1.5 9.773v.14c0 1.097.89 1.987 1.987 1.987H4.5a.75.75 0 0 1 0 1.5H3.487A3.487 3.487 0 0 1 0 9.913v-.14C0 8.449.785 7.274 1.963 6.75A5.253 5.253 0 0 1 7.215 1.4h.206a4.992 4.992 0 0 1 4.586 3.024A4.455 4.455 0 0 1 16 8.848V8.9a.75.75 0 0 1-1.5 0Z"></path><path d="m8.38 7.67 2.25 2.25a.749.749 0 0 1 0 1.061L8.38 13.23a.749.749 0 1 1-1.06-1.06l1.719-1.72L7.32 8.731A.75.75 0 0 1 8.38 7.67ZM15 13.45h-3a.75.75 0 0 1 0-1.5h3a.75.75 0 0 1 0 1.5Z"></path></svg> Agents**.
3. In the sidebar, click **Automations**.
4. Click **Create automation**.
5. Click **Create with agent** to work with Copilot to create your automations, or **Create manually** to set up automations with a form.

### Creating an automation with Copilot

After you click **Create with agent**, a chat window will appear and Copilot will ask what you want to automate.

You can work with Copilot to design your automation, setting up the triggers, tools and prompt.

Copilot can even help you create self-improving groups of automations which learn from outcomes and suggest improvements to themselves.

### Creating an automation manually

1. Enter a **name** for the automation.

2. Under **Type**, choose the kind of automation you want to create:

   * **Personal**: Only you can see the automation. AI credits are charged to you, and actions taken on GitHub use your identity.
   * **Shared**: Everyone with access to the repository can see the automation. AI credits are charged to the organization or user that owns the repository, and actions taken on GitHub use Copilot's identity.

   You can't change the type after you create the automation. See [Copilot automations](/en/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/about-automations#personal-and-shared-automations).

3. Select one or more **triggers** that determine when the automation runs. You can optionally configure filters for triggers to control when they fire.

   For issues and pull request triggers, you can choose:

   * **What resources on GitHub can be updated during the run**. From the **Configured tools can change** dropdown, choose **Anything in this repository** to let GitHub tools create and update any resource in the repository. Choose **Only this issue** to limit those tools' writes to the issue or pull request that triggered the run and any resources created during the run. This setting doesn't limit tools from MCP servers, which can access resources allowed by their server configuration and credentials. Depending on your repository configuration, the **Anything in this repository** option may not be available.
   * **Whether activity from Copilot in the cloud can trigger this automation**: From the **Can be triggered by** dropdown, pick **Anyone except Copilot in the cloud** to ignore events triggered by Copilot, including automations. Pick **Anyone** to listen for all events, including events triggered by Copilot.
   * **Whether users with only read access to the repository can trigger this automation**: By default, automations ignore activity from users who don't have write access to the repository. Uncheck the **Ignore events triggered by users without write access to this repository** box to listen for these events. Depending on your repository configuration, the **Ignore events triggered by users without write access to this repository** option may be locked in an enabled state.

4. In the **prompt** field, describe the task you want Copilot to perform each time the automation runs.

   For example, `Label this issue as a bug, an enhancement, or other, based on its content.`

5. Optionally, select the **model** and **reasoning level** you want Copilot to use. See [Changing the AI model for GitHub Copilot cloud agent](/en/copilot/how-tos/use-copilot-agents/cloud-agent/changing-the-ai-model).

6. Select the **tools** Copilot can use when the automation runs, such as pushing changes, updating issue labels, or creating a pull request.

   You can select GitHub tools, and tools from any MCP servers configured in the repository's MCP settings. To make an external system's tools available, a repository administrator must first configure its MCP server for the repository. See [Configure MCP servers for your repository](/en/copilot/how-tos/copilot-on-github/customize-copilot/configure-mcp-servers).

   Select only the tools the task requires. The tools you select control what actions Copilot can take in your repository. Optionally, you can use the **Suggest tools** button to ask Copilot to suggest tools based on your prompt. See [Copilot automations](/en/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/about-automations#tools-and-actions).

7. Optionally, under **AI credit limits**, set limits on how many AI credits the automation can consume. See [Setting AI credits limits](#setting-ai-credits-limits).

8. Save the automation by clicking **Create automation**.

## Setting AI credits limits

Each time an automation runs, it consumes AI credits, which are billed to you for a personal automation, or to the repository owner for a shared automation. To control costs, you can set limits in the **AI credit limits** section when you create or edit an automation.

You can set the following optional limits, in AI credits. Leave a limit empty if you don't want to set it.

* **Per run**: Stops a run as soon as it reaches the limit. The minimum is 30 AI credits.
* **Daily**: Prevents new runs from starting once the limit is reached. Resets every day at 00:00 UTC.
* **Weekly**: Prevents new runs from starting once the limit is reached. Resets every Monday at 00:00 UTC.
* **Monthly**: Prevents new runs from starting once the limit is reached. Resets on the first day of each month at 00:00 UTC.

The daily, weekly, and monthly limits don't stop a run that is already in progress. To cap the cost of each individual run, set a per-run limit.

To remove a limit, edit the automation and clear the value.

## Testing an automation

You can run an automation immediately, without waiting for its trigger to fire, to check that it behaves as you expect.

1. Open the automation you want to test from the **Automations** pane.
2. Click the **Run** button.
3. From the **Trigger** dropdown, pick the trigger you want to simulate.
4. If you picked the **Manual** trigger, optionally enter **Context** which will be included in the agent's prompt. You can use this to simulate triggering the automation via the API.

   If you picked another trigger, fill in **Resource URL** with the relevant resource, for example the URL of the issue that was opened or the pull request comment that was created.
5. Click **Run now**.

   Copilot starts a Copilot cloud agent session and runs the automation's prompt with the tools you selected. You can open the session to follow its progress and review any changes it makes.

## Managing your Automations

Your personal automations are private to you. Shared automations are visible to everyone with read access to the repository, and anyone with write access can edit them.

The sessions started from any automation are visible to everyone with read access to the repository.

From the **Automations** pane in a repository, you can:

* View your personal automations and the repository's shared automations, the sessions they have started, and the AI credits they have consumed.
* Edit an automation to change its name, prompt, triggers, tools, model, reasoning effort or AI credits limits, and track the automation's revision history.
* Review proposed improvements to an automation's tools, triggers or prompt, proposed by the automation itself or other automations.
* Disable an automation to stop it running, or enable it again later.
* Delete an automation you no longer need.

To see all of your automations across every repository, and navigate to manage each one, use the Automations view at the user level.

## Further reading

* [Copilot automations](/en/copilot/concepts/agent-capabilities/agent-powered-workflows-and-operations/about-automations)
* [Starting GitHub Copilot sessions](/en/copilot/how-tos/use-copilot-agents/cloud-agent/start-copilot-sessions)
* [Risks and mitigations for GitHub Copilot cloud agent](/en/copilot/concepts/agents/cloud-agent/risks-and-mitigations)

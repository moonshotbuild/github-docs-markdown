---
source_path: "/en/copilot/how-tos/github-copilot-app/customize-github-copilot-app"
title: "Customizing the GitHub Copilot app"
intro: "Customize the GitHub Copilot app so it works the way you and your team do."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "GitHub Copilot app"
    href: "/en/copilot/how-tos/github-copilot-app"
  - title: "Customize the GitHub Copilot app"
    href: "/en/copilot/how-tos/github-copilot-app/customize-github-copilot-app"
---

# Customizing the GitHub Copilot app

Customize the GitHub Copilot app so it works the way you and your team do.

Tailor the GitHub Copilot app to your workflows so your agents follow your conventions, use your preferred tools, and apply the right expertise to every task.

## Setting global and repository instructions

You can set global instructions in the app settings under **General**.

You can set repository-specific instructions in the app settings, under the repository name in the "Projects" section.

## Adding agent skills

Agent skills are folders of instructions, scripts, and resources that Copilot can load when relevant to improve its performance in specialized tasks. Any skills configured for your repositories or Copilot CLI are automatically available in the GitHub Copilot app. You can also add and manage skills in the app settings under **Skills**.

For more information about agent skills, see [About agent skills](/en/copilot/concepts/agents/about-agent-skills).

For a GitHub-provided built-in skills reference, see [Built-in skills for the GitHub Copilot app](/en/copilot/reference/github-copilot-app-reference/built-in-skills).

## Configuring MCP servers

MCP servers connect the agent to external tools and data sources. Any MCP servers configured for your repositories or Copilot CLI are automatically available in the GitHub Copilot app. You can also add and manage additional MCP servers in the app settings under **MCP Servers**. The app includes a catalog of popular servers, or you can add a custom server.

For more information about MCP, see [Adding MCP servers for GitHub Copilot CLI](/en/copilot/how-tos/copilot-cli/customize-copilot/add-mcp-servers).

## Using custom agents

Custom agents are specialized versions of Copilot cloud agent that you can tailor to specific tasks and workflows.

Use the agent picker dropdown in the prompt box to select a custom agent before or during a session.

Alternatively, type `/agent` in the prompt box to choose and invoke a custom agent.

For more information, see [About custom agents](/en/copilot/concepts/agents/cloud-agent/about-custom-agents).

## Adding plugins

Plugins are installable packages that add a preconfigured set of capabilities, such as skills, hooks, and custom agents, extending GitHub Copilot app's functionality.

To browse and install plugins, open app settings, then click **Plugins**.

For more information, see [About GitHub Copilot plugins](/en/copilot/concepts/agents/about-plugins).

## Working with canvas extensions

Use canvas extensions to build shared, agent-driven artifacts and interfaces for team or personal workflows. In a session, use `/create-canvas` to scaffold a canvas extension, then iterate on the canvas with the agent. For more information, see [Working with canvas extensions in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/working-with-canvas-extensions).

## Organization and enterprise management

Enterprise and organization owners can set policies to govern how Copilot is used across surfaces. For the major policies supported by the GitHub Copilot app, see [Supported surfaces for GitHub Copilot policies](/en/copilot/reference/supported-surfaces-for-policies).

Enterprises can also define a `managed-settings.json` file to control which actions users can take in supported Copilot clients, such as which plugins users can install and whether "YOLO-style" commands are permitted. See [Configuring enterprise-managed settings](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings).

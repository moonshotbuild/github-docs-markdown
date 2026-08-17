---
source_path: "/en/copilot/how-tos/administer-copilot/view-code-generation"
title: "Viewing the code generation dashboard"
intro: "The code generation dashboard shows how Copilot generates code across your enterprise, including activity from both users and agents."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Administer Copilot"
    href: "/en/copilot/how-tos/administer-copilot"
  - title: "View code generation"
    href: "/en/copilot/how-tos/administer-copilot/view-code-generation"
---

# Viewing the code generation dashboard

The code generation dashboard shows how Copilot generates code across your enterprise, including activity from both users and agents.

By comparing user-initiated and agent-initiated activity across models, languages, and modes, you can see how teams are adopting AI-assisted and agent-driven development.

The dashboard shows aggregated code generation activity, including:

* **Lines of code changed with AI**. The total lines of code added and deleted across all modes.
* **User-initiated code changes**. Lines suggested or manually added through completions and chat actions.
* **Agent-initiated code changes**. Lines automatically added or deleted by agents across edit, agent, and custom modes.
* **Activity by model and language**. User-initiated and agent-initiated activity grouped by model and language.

For a detailed list of available metrics and definitions, see [Data available in Copilot usage metrics](/en/copilot/reference/copilot-usage-metrics/copilot-usage-metrics#code-generation-dashboard-metrics).

## Prerequisite

To access Copilot usage metrics, the **"Copilot usage metrics"** policy must be enabled:

* [Managing policies and features for GitHub Copilot in your enterprise](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies#defining-policies-for-your-enterprise)
* [Managing policies and features for GitHub Copilot in your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies#enabling-copilot-features-and-models-in-your-organization)

## Accessing the dashboard

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.
2. Click the **Insights** tab.
3. In the left sidebar, click **Code generation**.

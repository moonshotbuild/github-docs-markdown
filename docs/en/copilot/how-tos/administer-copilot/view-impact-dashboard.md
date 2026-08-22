---
source_path: "/en/copilot/how-tos/administer-copilot/view-impact-dashboard"
title: "Viewing the Copilot impact dashboard"
intro: "The impact dashboard shows how deeply your organization has adopted Copilot, and how that adoption connects to pull request output."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Administer Copilot"
    href: "/en/copilot/how-tos/administer-copilot"
  - title: "View impact dashboard"
    href: "/en/copilot/how-tos/administer-copilot/view-impact-dashboard"
---

# Viewing the Copilot impact dashboard

The impact dashboard shows how deeply your organization has adopted Copilot, and how that adoption connects to pull request output.

Instead of a flat active-user count, the impact dashboard groups users into adoption cohorts based on how they engage with Copilot, and connects that engagement to pull request throughput. This gives you a more meaningful signal of adoption depth than daily or weekly active user counts alone.

For a detailed explanation of what the dashboard shows, including adoption cohorts, engagement trends, potential return on investment, and recommendations, see [GitHub Copilot usage metrics](/en/copilot/concepts/copilot-usage-metrics/copilot-metrics).

## Prerequisite

To access Copilot usage metrics, the **"Copilot usage metrics"** policy must be enabled:

* [Managing policies and features for GitHub Copilot in your enterprise](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies#defining-policies-for-your-enterprise)
* [Managing policies and features for GitHub Copilot in your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies#enabling-copilot-features-and-models-in-your-organization)

## Accessing the dashboard

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.
2. Click the **Insights** tab.
3. In the left sidebar, click **Copilot impact**.

## Estimating potential return on investment

The "Potential return on investment" section provides a directional comparison of cost and pull request output across adoption phases.

1. Under "Average developer cost in your organization", select a compensation band.
2. In the "Transition your developers to be agent-first" card, compare the cost, payroll, and pull request estimates for "Phase 0-1 Passive and Code First Users" and "Phase 2-3 Agent First Users".

Treat the figures as directional estimates rather than exact financial results. Use them with the adoption multiplier metrics for code shipped and time to merge pull requests.

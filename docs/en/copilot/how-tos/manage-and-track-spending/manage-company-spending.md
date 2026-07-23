---
source_path: "/en/copilot/how-tos/manage-and-track-spending/manage-company-spending"
title: "Managing your company's spending on GitHub Copilot"
intro: "Learn how to track spending, view usage, and optimize license distribution."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Manage and track spending"
    href: "/en/copilot/how-tos/manage-and-track-spending"
  - title: "Manage company spending"
    href: "/en/copilot/how-tos/manage-and-track-spending/manage-company-spending"
---

# Managing your company's spending on GitHub Copilot

Learn how to track spending, view usage, and optimize license distribution.

When you're adopting GitHub Copilot in an enterprise, you will want to set budgets and track spending to ensure your rollout is sustainable. GitHub offers billing tools to help you visualize your spending patterns, control AI credits consumption with budget controls, receive alerts when you reach budget thresholds, and optimize your license usage.

## Understanding who can grant licenses

To control spending, it's important to understand who can affect your bill by granting licenses to users. These are people with the **organization owner** role in organizations where you enable GitHub Copilot. Organization owners can receive requests for access from members through the GitHub UI.

We recommend that you identify the people with this role and communicate with them about your company's strategy for distributing licenses. For example, you may have a budget or limited pilot program, or you may distribute licenses through an internal website.

For more information, see [Viewing people in your enterprise](/en/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/viewing-people-in-your-enterprise#viewing-members).

## Managing AI credits usage

Each Copilot license includes AI credits that are pooled across your enterprise. When the pool is exhausted, additional usage is charged at $0.01 USD per AI credit, subject to your budget controls.

### Tracking usage

To track AI credits consumption, navigate to **Billing & licensing** > **AI usage** in your enterprise settings. You can filter usage by user, model, organization, or cost center, and export the data for further analysis.

### Controlling usage with budgets

You can set budgets at the user, cost center, and enterprise level to control how AI credits are consumed. For an overview of how budget controls work, see [Budgets for usage-based billing](/en/copilot/concepts/billing/budgets-for-usage-based-billing). For guidance on choosing the right configuration, see [Optimizing your budget configuration](/en/copilot/tutorials/budgets/optimizing-your-budget-configuration).

## Mapping spending to groups of users

You can create cost centers to map spending to individual business units or groups of users. Cost centers allow you to track costs tied to different initiatives and charge the costs to specific areas of your business.

For example, if you were running a pilot program for GitHub Copilot Enterprise for a group of employees, you might want to create a cost center to track their spending and set a budget independently of the rest of the company.

For more information, see [Controlling and tracking costs at scale](/en/billing/tutorials/control-costs-at-scale).

## Preventing overspending

You can set budgets to control Copilot spending at multiple levels.

* **User-level budgets** cap how many AI credits any single user can consume per billing cycle, from both the shared pool and additional usage.
* **Cost center budgets** and **enterprise spending limits** cap metered charges after the shared pool is exhausted.

Enable "Stop usage when budget limit is reached" on every spending limit you create. Without it, reaching a limit sends a notification but does not block usage and charges continue to accrue.

For step-by-step instructions, see [Setting up budgets to control spending on metered products](/en/billing/how-tos/set-up-budgets).

## Visualizing spending trends

You can understand your spending trends by viewing graphs of Copilot usage over a certain timeframe. Usage includes costs for Copilot licenses and any additional AI credits beyond the included pool.

For more detailed insights, you can group usage by the type of Copilot plan, and enterprises can filter the results by cost center.

1. Go to your enterprise or organization account settings and click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-credit-card" aria-label="credit-card" role="img"><path d="M10.75 9a.75.75 0 0 0 0 1.5h1.5a.75.75 0 0 0 0-1.5h-1.5Z"></path><path d="M0 3.75C0 2.784.784 2 1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 14H1.75A1.75 1.75 0 0 1 0 12.25ZM14.5 6.5h-13v5.75c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25Zm0-2.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25V5h13Z"></path></svg> Billing & Licensing**.

2. In the left sidebar, click **Usage**. For enterprises, then click **Metered usage**.

3. In the "Metered usage" section, in the search field, enter `product:copilot`. To filter by cost center, add a query like `cost_center:ce-pilot-group`.

4. To understand spending differences between Copilot Business and Copilot Enterprise plans, select the **Group: None** dropdown menu and click **Group by: SKU**.

   ![Screenshot of the "Usage" page. A line chart tracks Copilot spending over the current month, grouped by SKU.](/assets/images/help/copilot/track-spending.png)

5. To visualize AI credits consumption in detail, in the left sidebar under "Metered usage" click **AI usage**.

6. By default, the chart and table show usage grouped by model. Use the filter, "Group by", and "Timeframe" controls to show the data you want.

   ![Screenshot of the "AI usage" page. A line chart tracks AI usage over the current month, grouped by model.](/assets/images/help/copilot/track-spending-prs.png)

## Next steps

As well as managing spending on licenses, it is important to ensure licenses are being used effectively. When you begin rolling out Copilot in a company, you may see low rates of adoption at first. An effective enablement process is essential to drive adoption of Copilot in your company. Tailor this process to your company's needs and goals, and design it to help your teams understand how to use Copilot effectively.

To ensure your licenses are being used effectively, you can use the API to identify inactive users. We recommend sending these users a message with advice and resources for getting started. If a user remains inactive, you can revoke their license and assign it to another user.

If you're not sure how best to distribute licenses, GitHub has found that many successful rollouts offer a fully self-service model where developers can claim a license without approval. This allows people to get started quickly and ensures you're giving licenses to people who plan to use them.

For detailed guidance, see:

* [Driving GitHub Copilot adoption in your company](/en/copilot/tutorials/roll-out-at-scale/enable-developers/drive-adoption)
* [Setting up a self-serve process for GitHub Copilot licenses](/en/copilot/tutorials/roll-out-at-scale/assign-licenses/set-up-self-serve-licenses)
* [Reminding inactive users to use their GitHub Copilot license](/en/copilot/tutorials/roll-out-at-scale/assign-licenses/remind-inactive-users)

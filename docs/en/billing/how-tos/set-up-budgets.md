---
source_path: "/en/billing/how-tos/set-up-budgets"
title: "Setting up budgets to control spending on metered products"
intro: "Prevent overspending by setting budgets and tracking when metered usage nears or exceeds a budget threshold."
product: "Billing and payments"
document_type: "article"
breadcrumbs:
  - title: "Billing and payments"
    href: "/en/billing"
  - title: "How-tos"
    href: "/en/billing/how-tos"
  - title: "Set up budgets"
    href: "/en/billing/how-tos/set-up-budgets"
---

# Setting up budgets to control spending on metered products

Prevent overspending by setting budgets and tracking when metered usage nears or exceeds a budget threshold.

Budgets help you track and control spending on different products. To learn more, see [Budgets and alerts](/en/billing/concepts/budgets-and-alerts).

## Plan your budget type and scope

Before you create a budget, it’s important to understand how budget types and scopes interact. Usage of metered products can count toward multiple applicable budgets at the same time, and if any budget with **Stop usage when budget limit is reached** enabled is exhausted, additional usage is blocked.

![Screenshot of budgets for "octo-org": "Actions" budget is $50 and "Actions Linux 96-core" budget is $100. All the "Actions" budget has been used.](/assets/images/help/billing/org-budget-example.png)

In this example, the organization has set a budget of $50 for the "Actions" product and a budget of $100 for one of the SKUs within the "Actions" product. The organization has used all the included quota of actions minutes and an extra $50 of billed minutes. Some of the extra use was for Linux 96-core runners so it is applied to both budgets. Overall, the organization has used the full budget for the "Actions" product of $50. Members are now blocked from using all GitHub-hosted runners until the next billing cycle or until the "Actions" product budget is increased. The SKU budget for Linux 96-core runners serves no purpose and is confusing, so should be deleted.

We recommend that you avoid creating overlapping budgets for the use of a product and a SKU, or an organization and a repository, so that users are not unexpectedly blocked from using a feature that they rely on. Alternatively, you may prefer to monitor use without blocking users by disabling the "Stop usage when budget limit is reached" option.

For Copilot under usage-based billing, user-level budgets add another layer to consider. A user-level budget can block a user even when the enterprise or cost center budget still has capacity. It is the first check in the evaluation sequence. When planning your budget configuration, account for how user-level budgets, cost center budgets, and the enterprise spending limit interact. See [Budgets for usage-based billing](/en/copilot/concepts/billing/budgets-for-usage-based-billing#how-billing-flows-through-budgets).

## Managing budgets for your personal account

You can set budgets and receive alerts when your usage of a product reaches 75%, 90%, or 100% of a defined budget. Budgets can be set for a specific repository or for your whole account.

1. Open your billing overview page: [https://github.com/settings/billing](https://github.com/settings/billing?ref_product=github\&ref_type=engagement\&ref_style=text).

2. Click **Budgets and alerts**.

3. To create a new budget, click **New budget**.

4. Under "Budget Type" select **Product-level budget**, **SKU-level budget**, or **Bundled AI credits budget**.

   * To limit spending at a Product-level, in "Product-level budget" choose a product from the dropdown, for example: Codespaces.
   * To limit spending at a SKU-level, in "SKU-level budget" choose a Product and then a SKU, for example: Codespaces and Codespaces storage.
   * To limit spending on AI credits across all features, enable "Bundled AI credits budget" or to limit spending for a specific feature, set a SKU-level budget for the feature (such as Copilot AI credits, Spark AI credits, or Copilot cloud agent).

5. Under "Budget scope", set the scope of spending for this budget.

6. Under "Budget", set a budget amount.

   To stop any usage and further spending once the budget limit is reached, select **Stop usage when budget limit is reached**, if available. This option is not available for user-level budgets, which always enforce a hard stop.

   > \[!IMPORTANT] If you do not select **Stop usage when budget limit is reached**, you will be notified by email if you exceed your budget, but usage **will not** be stopped.

7. To receive an alert if your budget has reached 75%, 90% and 100% thresholds, select **Receive budget threshold alerts** under "Alerts". When the budget has reached the specific threshold, you will be notified via email and a banner on GitHub. You may opt out at any time.

8. Click **Create budget**.

To edit or delete a budget, on the "Budget and alerts" page, click **Edit** or **Delete** next to the budget you want to edit or delete. Follow the prompts.

### Managing included usage alerts for your personal account

GitHub can send you email notifications when the included usage for your plan reaches 90% and 100% during a billing period. To learn more about what these alerts cover, see [Budgets and alerts](/en/billing/concepts/budgets-and-alerts#included-usage-alerts).

1. Open your billing overview page: [https://github.com/settings/billing](https://github.com/settings/billing?ref_product=github\&ref_type=engagement\&ref_style=text).

2. Click **Budgets and alerts**.

3. Under "Included usage alerts", select or clear **Receive alerts when my included usage reaches 90% and 100%** to opt in or out of email notifications.

## Managing budgets for your organization or enterprise

> \[!IMPORTANT]
> Copilot usage is now measured in AI credits under usage-based billing. Existing premium request budgets have been automatically converted to AI credit budgets. See [Usage-based billing for organizations and enterprises](/en/copilot/concepts/billing/usage-based-billing-for-organizations-and-enterprises).

You can set budgets and receive alerts when your usage of a product or license type reaches 75%, 90%, or 100% of a defined budget. For budgets that control metered use of a product, you can also block further use when the budget is exhausted. Each budget has a scope.

* **Organization budget scopes**: the whole organization or a single repository within the organization
* **Enterprise budget scopes**:
  * Metered products: the whole enterprise, a single organization, a single repository, or a single cost center
  * Enterprise licenses (metered): the whole enterprise or a single cost center
  * AI credits (bundled): the whole enterprise, a single organization, a single cost center, or per user

### Viewing budgets

If you are an organization owner, enterprise owner, or billing manager, any account-level budget is listed at the top of the "Budgets and alerts" page, followed by budgets for smaller scopes.

1. Navigate to your organization or enterprise. For example, from the [Organizations](https://github.com/settings/organizations?ref_product=github\&ref_type=engagement\&ref_style=text) or [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) pages on GitHub.com.

2. Click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-credit-card" aria-label="credit-card" role="img"><path d="M10.75 9a.75.75 0 0 0 0 1.5h1.5a.75.75 0 0 0 0-1.5h-1.5Z"></path><path d="M0 3.75C0 2.784.784 2 1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 14H1.75A1.75 1.75 0 0 1 0 12.25ZM14.5 6.5h-13v5.75c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25Zm0-2.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25V5h13Z"></path></svg> Billing & Licensing** to display the billing and licensing overview for the account:
   * **Organization** accounts: under "Access" in the sidebar for settings.
   * **Enterprise** accounts: a separate tab at the top of the page.

3. Click **Budgets and alerts**.

4. Optionally, in the enterprise view only, to filter by scope, select **Scope**, then choose a scope.

### Creating a budget

As the owner of an enterprise or organization account, or as a billing manager, you can set a budget at the account level, or at any level below this.

1. In the "Budgets and alerts" view, click **New budget**.

2. Under "Budget Type" select **Product-level budget**, **SKU-level budget**, or **Bundled AI credits budget**.

   * **Product-level budget**: Limits spending on a single product (for example, Codespaces).
   * **SKU-level budget**: Limits spending on a specific SKU within a product (for example, GitHub Secret Protection within GitHub Advanced Security).
   * **Bundled AI credits budget**: Limits spending across all SKUs that consume AI credits, including Copilot, Copilot cloud agent, and Spark. Available where overage spend is enabled.

3. Under "Budget scope", set the scope of spending for this budget.

   * **Enterprise**: Tracks spending across all organizations, repositories, and cost centers in the enterprise.
   * **Organization**: Tracks spending for all repositories in the organization.
   * **Cost center**: Tracks spending for a single cost center.
   * **Users**: Sets a per-user budget. Available when you select **Bundled AI credits budget** as the budget type.
     * Leave the user field empty to create a universal budget that applies to all Copilot-licensed users.
     * Select a cost center to create a user-level budget that applies to every user in that cost center. This sets one per-user amount for all current and future members, and overrides the universal budget for them.
     * Select a specific user to create an individual budget that overrides both the universal budget and any cost center user-level budget for that user.

4. Under "Budget", set a budget amount or license count.

   To stop any usage and further spending once the budget limit is reached, select **Stop usage when budget limit is reached** or **Limit usage when budget limit is reached**, if available. **This option is available for metered products and for Advanced Security SKU-level budgets**. For Advanced Security, this option prevents new enablement on additional repositories. It doesn't disable Advanced Security on repositories where it is already active. See [GitHub Advanced Security license billing](/en/billing/concepts/product-billing/github-advanced-security#hard-budgets-for-github-advanced-security-skus).

   > \[!IMPORTANT] If you do not select one of these options, you will be notified by email if you exceed your budget, but usage **will not** be stopped.

5. To receive an alert if your budget has reached 75%, 90% and 100% thresholds, select **Receive budget threshold alerts** under "Alerts". When the budget has reached the specific threshold, you will be notified via email and a banner on GitHub. You may opt out at any time.

   Under "Alert Recipients", select the people who will receive the alerts.

6. Click **Create budget**.

### Managing included usage alerts

GitHub can send email notifications when the included usage for your account reaches 90% and 100% during a billing period. To learn more about what these alerts cover, see [Budgets and alerts](/en/billing/concepts/budgets-and-alerts#included-usage-alerts).

1. Navigate to the "Budgets and alerts" view. See [Viewing budgets](#viewing-budgets).
2. Under "Included usage alerts", select or clear **Receive alerts when my included usage reaches 90% and 100%** to opt in or out of email notifications.

### Editing or deleting a budget

> \[!IMPORTANT] Deleting a budget may remove any limits on spending, depending on your other existing budgets.

You can edit or delete a budget at any time, but you cannot change the scope of a budget after creating it.

1. Navigate to the "Budgets and alerts" view. See [Viewing budgets](#viewing-budgets).
2. In the list of budgets, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="View actions" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg> next to the budget you want to edit, and click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-pencil" aria-label="pencil" role="img"><path d="M11.013 1.427a1.75 1.75 0 0 1 2.474 0l1.086 1.086a1.75 1.75 0 0 1 0 2.474l-8.61 8.61c-.21.21-.47.364-.756.445l-3.251.93a.75.75 0 0 1-.927-.928l.929-3.25c.081-.286.235-.547.445-.758l8.61-8.61Zm.176 4.823L9.75 4.81l-6.286 6.287a.253.253 0 0 0-.064.108l-.558 1.953 1.953-.558a.253.253 0 0 0 .108-.064Zm1.238-3.763a.25.25 0 0 0-.354 0L10.811 3.75l1.439 1.44 1.263-1.263a.25.25 0 0 0 0-.354Z"></path></svg> Edit** or **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-trash" aria-label="trash" role="img"><path d="M11 1.75V3h2.25a.75.75 0 0 1 0 1.5H2.75a.75.75 0 0 1 0-1.5H5V1.75C5 .784 5.784 0 6.75 0h2.5C10.216 0 11 .784 11 1.75ZM4.496 6.675l.66 6.6a.25.25 0 0 0 .249.225h5.19a.25.25 0 0 0 .249-.225l.66-6.6a.75.75 0 0 1 1.492.149l-.66 6.6A1.748 1.748 0 0 1 10.595 15h-5.19a1.75 1.75 0 0 1-1.741-1.575l-.66-6.6a.75.75 0 1 1 1.492-.15ZM6.5 1.75V3h3V1.75a.25.25 0 0 0-.25-.25h-2.5a.25.25 0 0 0-.25.25Z"></path></svg> Delete**.
3. Follow the prompts.

### Controlling included usage for a cost center

Budgets cap metered charges after the shared pool of AI credits is exhausted. To cap how much of the pool a cost center can use **before** the metered phase, use an included usage control. GitHub sets the cap automatically based on the licenses assigned to the cost center, and you choose whether members are blocked or roll into paid overage when the cap is reached. See [Budgets for usage-based billing](/en/copilot/concepts/billing/budgets-for-usage-based-billing#included-usage-controls-for-cost-centers) and [Cost centers](/en/billing/concepts/cost-centers).

> \[!NOTE]
> Enabling included usage controls does not retroactively redistribute the shared AI credits enterprise pool. After the setting is enabled, users in the cost center share only the included AI credits funded by licenses attributed to that cost center. When the setting is disabled, users in the cost center can continue drawing from the shared enterprise pool.

## Next steps

For Copilot-specific budget guidance under usage-based billing, including user-level budgets and configuration scenarios, see [Budgets for usage-based billing](/en/copilot/concepts/billing/budgets-for-usage-based-billing) and [Optimizing your budget configuration](/en/copilot/tutorials/budgets/optimizing-your-budget-configuration).

---
source_path: "/en/billing/how-tos/products/use-cost-centers"
title: "Using cost centers to allocate costs to business units"
intro: "Learn how to create and use cost centers to manage costs across your company's divisions at scale."
product: "Billing and payments"
document_type: "article"
breadcrumbs:
  - title: "Billing and payments"
    href: "/en/billing"
  - title: "How-tos"
    href: "/en/billing/how-tos"
  - title: "Products"
    href: "/en/billing/how-tos/products"
  - title: "Use cost centers"
    href: "/en/billing/how-tos/products/use-cost-centers"
---

# Using cost centers to allocate costs to business units

Learn how to create and use cost centers to manage costs across your company's divisions at scale.

> \[!NOTE] Before you create or update a cost center, if you're unsure of how spending will be allocated to the cost center, see [Cost center allocation for different products](/en/billing/reference/cost-center-allocation).

## Creating a cost center

> \[!NOTE]
> An enterprise can create up to 1,000 cost centers.

Create cost centers to monitor and manage expenses for specific organizations or repositories. A single cost center can include multiple resources of any type, such as organizations, repositories, users, and enterprise teams.

When you create a cost center, you can add **organizations**, **repositories**, **users**, or **enterprise teams**. The cost center will then track spending for the selected entities.

You can assign an enterprise team to a cost center. Every member of the team is added to the cost center, and membership stays current automatically as people join or leave the team—so you don't have to add or remove users one by one. For more information about enterprise teams, see [Creating enterprise teams](/en/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/create-enterprise-teams).

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.

2. At the top of the page, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-credit-card" aria-label="credit-card" role="img"><path d="M10.75 9a.75.75 0 0 0 0 1.5h1.5a.75.75 0 0 0 0-1.5h-1.5Z"></path><path d="M0 3.75C0 2.784.784 2 1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 14H1.75A1.75 1.75 0 0 1 0 12.25ZM14.5 6.5h-13v5.75c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25Zm0-2.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25V5h13Z"></path></svg> Billing and licensing**.

3. Click **Cost centers**.

4. Click **New cost center** in the upper-right corner.

5. In the text box under "Name", enter a name for your cost center.

6. If your account is billed to Azure, you have the option to add an Azure ID. Your credentials will be verified against Azure to ensure the Azure IDs associated to your account are available.

7. Under **Resources**, select the organizations, repositories, users, and/or enterprise teams that will be a part of the cost center.

   > \[!NOTE]
   > A resource (organization, repository, user, or enterprise team) can belong to only one cost center at a time. A cost center can hold many resources, but each resource lives in a single cost center. If you add a resource that belongs to a different cost center, it will be moved to the new cost center and you will be notified.

8. Click **Create cost center**.

## Adding a budget to a cost center

After you create a cost center, you can add a monthly budget and receive alerts from the cost center to monitor your spending and usage. See [Setting up budgets to control spending on metered products](/en/billing/how-tos/set-up-budgets).

## Viewing cost center usage

You can view the usage of your cost centers and download the usage data for further analysis. See [Gathering insights on your spending](/en/billing/tutorials/gather-insights).

## Viewing, editing, and deleting cost centers

You can view, edit, and delete cost centers to manage your business units effectively.

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.
2. At the top of the page, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-credit-card" aria-label="credit-card" role="img"><path d="M10.75 9a.75.75 0 0 0 0 1.5h1.5a.75.75 0 0 0 0-1.5h-1.5Z"></path><path d="M0 3.75C0 2.784.784 2 1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 14H1.75A1.75 1.75 0 0 1 0 12.25ZM14.5 6.5h-13v5.75c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25Zm0-2.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25V5h13Z"></path></svg> Billing and licensing**.
3. Click **Cost centers**.
4. Select <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="Cost center dropdown" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg> to the right of a cost center, then click **View details**, **Edit**, or **Delete**.
5. Follow the prompts.

## Further reading

* [Controlling and tracking costs at scale](/en/billing/tutorials/control-costs-at-scale)
* [REST API endpoints for billing](/en/rest/billing/billing)

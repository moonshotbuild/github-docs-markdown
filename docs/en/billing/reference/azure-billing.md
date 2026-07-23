---
source_path: "/en/billing/reference/azure-billing"
title: "Billing through Azure subscriptions"
intro: "Learn how billing works when you connect your GitHub account to an Azure subscription."
product: "Billing and payments"
document_type: "article"
breadcrumbs:
  - title: "Billing and payments"
    href: "/en/billing"
  - title: "Reference"
    href: "/en/billing/reference"
  - title: "Azure billing"
    href: "/en/billing/reference/azure-billing"
---

# Billing through Azure subscriptions

Learn how billing works when you connect your GitHub account to an Azure subscription.

You can connect an Azure subscription to your GitHub account. When you do, charges for GitHub products (such as Copilot, GitHub Actions, or Codespaces) are billed through Azure instead of directly through GitHub.

Connecting an Azure subscription allows you to consolidate invoices and manage GitHub spending within your organization’s existing Azure billing processes.

For details on how to connect, see [Connecting an Azure subscription](/en/billing/how-tos/set-up-payment/connect-azure-sub).

## Billing cycles and invoicing

* Azure billing periods run on a **calendar month**: from the first day to the last day of each month.
* Usage data from GitHub is transmitted to Azure **daily**.
* Your charges for the month appear on your **Azure invoice at the start of the next month**.

If you enable Azure subscription billing in the middle of a GitHub billing cycle:

* Usage before the switch is charged by GitHub on your next GitHub bill.
* Usage after the switch is charged by Azure, beginning from the date metered billing is enabled.

## Usage tracking

* Usage is measured daily and sent to Azure.
* The usage metric depends on the product:

  * **Copilot:** Number of active seats.
  * **Actions:** Minutes used.
  * **Codespaces:** Compute hours used.

## Payment methods

When you pay through Azure, your organization’s standard Azure payment methods apply. You will not be billed separately by GitHub for the connected products.

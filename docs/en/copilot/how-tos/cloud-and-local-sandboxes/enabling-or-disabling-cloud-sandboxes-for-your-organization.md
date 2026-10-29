---
source_path: "/en/copilot/how-tos/cloud-and-local-sandboxes/enabling-or-disabling-cloud-sandboxes-for-your-organization"
title: "Managing cloud sandboxes for your organization or enterprise"
intro: "Decide which members can use Copilot features that run in cloud sandboxes, and keep cloud sandbox spending under control."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Sandbox Copilot"
    href: "/en/copilot/how-tos/cloud-and-local-sandboxes"
  - title: "Manage cloud sandboxes"
    href: "/en/copilot/how-tos/cloud-and-local-sandboxes/enabling-or-disabling-cloud-sandboxes-for-your-organization"
---

# Managing cloud sandboxes for your organization or enterprise

Decide which members can use Copilot features that run in cloud sandboxes, and keep cloud sandbox spending under control.

## About managing cloud sandboxes

Cloud sandboxes don't have their own access setting, and you can't opt out of them separately from Copilot policies. Copilot uses a cloud sandbox when a member starts a cloud session from any Copilot client. To manage cloud sandboxes, you control access to those features with Copilot policies, and you control spending with budgets.

For more information about cloud sandboxes, see [About cloud sandboxes for GitHub Copilot](/en/copilot/concepts/security-governance-and-network-settings/about-cloud-sandboxes).

## Controlling who can use cloud sandboxes

If members get Copilot through your organization or enterprise, the **Copilot in the cloud** policy controls whether they can run Copilot agents in a cloud environment that GitHub manages, from any Copilot client. The policy is enabled by default. When the policy is disabled, Copilot can't create cloud sandboxes for those members.

* To set the policy for an organization, see [Managing GitHub Copilot in the cloud for your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-copilot-in-the-cloud).
* To set the policy for an enterprise, see [Managing GitHub Copilot in the cloud for your enterprise or organization](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/manage-copilot-in-the-cloud).

## Controlling spending on cloud sandboxes

To monitor and limit cloud sandbox spending, set a budget for cloud sandbox usage. You can create a budget for all cloud sandbox usage or for a specific cloud sandbox SKU. See [Billing for cloud and local sandboxes for GitHub Copilot](/en/billing/concepts/product-billing/cloud-and-local-sandboxes#managing-your-budget-for-cloud-sandboxes).

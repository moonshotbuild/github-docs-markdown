---
source_path: "/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-a-dedicated-enterprise-for-copilot-business"
title: "Setting up a dedicated enterprise for GitHub Copilot Business"
intro: "Create an enterprise account for managing Copilot Business licenses without adopting GitHub Enterprise."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Copilot on GitHub"
    href: "/en/copilot/how-tos/copilot-on-github"
  - title: "Set up Copilot"
    href: "/en/copilot/how-tos/copilot-on-github/set-up-copilot"
  - title: "Enable Copilot"
    href: "/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot"
  - title: "Set up a dedicated enterprise"
    href: "/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot/set-up-a-dedicated-enterprise-for-copilot-business"
---

# Setting up a dedicated enterprise for GitHub Copilot Business

Create an enterprise account for managing Copilot Business licenses without adopting GitHub Enterprise.

With a dedicated enterprise account, you get enterprise-grade identity provider integrations for authentication and provisioning without paying for GitHub Enterprise licenses. See [About enterprise accounts for Copilot Business](/en/copilot/concepts/about-enterprise-accounts-for-copilot-business).

## Create an enterprise account

To create an enterprise account, contact GitHub's [sales team](https://github.com/enterprise/contact?ref_product=copilot\&ref_type=purchase\&ref_style=text). They will provision you with a standard enterprise account with Copilot enabled.

## Add users to your enterprise

Once you have an enterprise account, add the people who will receive Copilot Business licenses. How you add users depends on your enterprise type.
Once you have an enterprise account, add the people who will receive Copilot Business licenses. How you add users depends on your enterprise type.

Do not create any organizations during setup. Adding users to organizations assigns GitHub Enterprise licenses, while adding users directly to the enterprise keeps your setup limited to Copilot Business.

### Enterprise with personal accounts

Invite users directly to your enterprise. For detailed steps, see [Adding users to your enterprise](/en/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/invite-users-directly).

### Enterprise with managed users

If your enterprise uses Enterprise Managed Users, provision user accounts from your identity provider (IdP) through SCIM.
For setup and provisioning guidance, see [Getting started with Enterprise Managed Users](/en/enterprise-cloud@latest/admin/managing-iam/understanding-iam-for-enterprises/getting-started-with-enterprise-managed-users).

Provisioned users appear automatically in your enterprise's **People** list. You can then assign Copilot Business licenses directly to these users or to enterprise teams synced with your IdP.

## Create teams (optional)

Group users to scale license assignment by creating enterprise teams. See [Creating enterprise teams](/en/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/create-enterprise-teams).

## Convert your trial to a paid enterprise account

To begin using Copilot Business after your trial, convert to a paid enterprise account. See [Setting up a trial of GitHub Enterprise Cloud](/en/enterprise-cloud@latest/admin/overview/setting-up-a-trial-of-github-enterprise-cloud#purchasing-github-enterprise).

## Enable Copilot for the enterprise

1. Ensure you are signed in as an enterprise administrator on GitHub.
2. To purchase GitHub Copilot for your enterprise, [contact GitHub's Sales team](https://github.com/enterprise/contact?ref_product=copilot\&ref_type=engagement\&ref_style=text).

## Assign Copilot licenses

Give people access to Copilot by assigning Copilot Business licenses to users or enterprise teams.

For detailed steps, see [Granting users access to GitHub Copilot in your enterprise](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-access/grant-access#assigning-licenses-to-users-or-teams).

## Govern the use of Copilot in your enterprise

After you assign licenses, you can centrally govern how members use Copilot:

* **Policies**. Control feature availability with policies in AI Controls.
* **Enterprise managed settings**. Distribute client governance and extensibility configuration from a centrally defined source. You can apply permission seetings like disabling bypass mode, restrict plugins, and set the default model for new conversations to Copilot CLI and VS Code. See [Configuring enterprise-managed settings](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings).

To use server-managed settings, you need an organization and a `.github-private` repository, which requires a GitHub Enterprise license for the user who creates them. Alternatively, you can deploy managed settings through MDM or a file-based deployment without creating an organization.

## Next steps

Help your developers start using Copilot and measure its impact. See [Driving GitHub Copilot adoption in your company](/en/copilot/tutorials/roll-out-at-scale/enable-developers/drive-adoption).

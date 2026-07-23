---
source_path: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/prepare-for-custom-agents"
title: "Preparing to use custom agents in your enterprise"
intro: "Set up your enterprise for custom agents by configuring their source organization and repository, availability, and management permissions."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Administer Copilot"
    href: "/en/copilot/how-tos/administer-copilot"
  - title: "Manage for enterprise"
    href: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise"
  - title: "Manage agents"
    href: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents"
  - title: "Prepare for custom agents"
    href: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/prepare-for-custom-agents"
---

# Preparing to use custom agents in your enterprise

Set up your enterprise for custom agents by configuring their source organization and repository, availability, and management permissions.

Enterprise-level custom agents are defined in a specific repository within an organization in your enterprise.

Before you can create and use custom agents, you need to create this repository and configure the relevant enterprise settings.

## Creating a repository for your enterprise governance

1. Create a `.github-private` repository for your enterprise governance. If you don't already have a `.github-private` repo, see [Creating a \`.github-private\` repository](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/create-github-private-repo).

2. To automatically configure a ruleset that allows only enterprise owners to edit agent profiles, in the "Protect agent files using rulesets" section, click **Create ruleset**.

   > \[!NOTE]
   >
   > * Members of your enterprise with write access to the custom agent repository can still create pull requests proposing changes to your agent profiles. Enterprise members with bypass access to the ruleset can then merge those pull requests as they see fit.
   > * Creating this ruleset will also block organization owners in your enterprise from creating or editing organization-level custom agents. To prevent this, you can edit the ruleset to target only the organization containing your enterprise-level custom agents.

## Next steps

To reduce your administrative burden and empower your SMEs, you can delegate the creation and management of custom agents in your enterprise by creating a team of AI managers. See [Establishing AI managers in your enterprise](/en/copilot/tutorials/roll-out-at-scale/govern-at-scale/establish-ai-managers).

If you prefer to maintain full control over your enterprise's tooling to ensure security and compliance, you can create and manage custom agents yourself. See [Testing and releasing custom agents in your organization or enterprise](/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/test-custom-agents).

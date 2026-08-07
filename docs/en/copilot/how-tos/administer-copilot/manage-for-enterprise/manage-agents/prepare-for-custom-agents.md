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

Enterprise-level custom agents are defined in a `.github-private` repository within an organization in your enterprise. Preparing your enterprise involves creating that repository, configuring it as your source of governance, protecting your agent files, and deciding who can manage custom agents.

Work through the following steps to set up your enterprise.

## Set up your governance repository

1. **Create a `.github-private` repository** to house your enterprise's agent profiles, client permissions, and plugin settings.
2. **Select the repository as your source of governance** so that your enterprise reads its settings from the repository.

For both steps, see [Creating a \`.github-private\` repository](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/create-github-private-repo).

## Protecting your agent files using rulesets

To automatically configure a ruleset that allows only enterprise owners to edit agent profiles across your enterprise:

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.
2. At the top of the page, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> AI controls**.
3. On the "Agents" tab, in the "Protect agent files using rulesets" section, click **Create ruleset**.

> \[!NOTE]
>
> * Members of your enterprise with write access to the custom agent repository can still create pull requests proposing changes to your agent profiles. Enterprise members with bypass access to the ruleset can then merge those pull requests as they see fit.
> * Creating this ruleset will also block organization owners in your enterprise from creating or editing organization-level custom agents. To prevent this, you can edit the ruleset to target only the organization containing your enterprise-level custom agents.

## Decide who manages your custom agents

To reduce your administrative burden and empower your SMEs, you can delegate the creation and management of custom agents in your enterprise by creating a team of AI managers. See [Establishing AI managers in your enterprise](/en/copilot/tutorials/roll-out-at-scale/govern-at-scale/establish-ai-managers).

If you prefer to maintain full control over your enterprise's tooling to ensure security and compliance, you can create and manage custom agents yourself. See [Testing and releasing custom agents in your organization or enterprise](/en/copilot/how-tos/copilot-on-github/customize-copilot/customize-cloud-agent/test-custom-agents).

## Next steps

To centrally control Copilot client behavior across your enterprise, configure enterprise managed settings. See [Configuring enterprise-managed settings](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings).

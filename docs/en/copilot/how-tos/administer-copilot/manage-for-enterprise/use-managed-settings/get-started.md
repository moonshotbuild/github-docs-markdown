---
source_path: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings/get-started"
title: "Getting started with enterprise-managed settings"
intro: "Configure enterprise managed settings to centrally control Copilot client behavior across your enterprise."
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
  - title: "Use enterprise managed settings"
    href: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings"
  - title: "Get started"
    href: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings/get-started"
---

# Getting started with enterprise-managed settings

Configure enterprise managed settings to centrally control Copilot client behavior across your enterprise.

With enterprise managed settings, you can centrally define and distribute configuration settings for GitHub Copilot to supported clients. This ensures everyone works within the guardrails you define, with the option to specialize settings for different teams. For example, you can block agents from performing sensitive operations, install approved agent plugins, or ensure that sessions run in a sandbox.

This guide walks through creating the `managed-settings.json` file on GitHub, rolling out the settings to users, and overriding specific settings for enterprise teams. As a low-friction example, we'll ensure new conversations start in auto model mode for most users, and override this setting for a specific enterprise team. This example will allow you to test the managed settings deployment without causing disruption to users.

> \[!NOTE] If you use a dedicated enterprise for Copilot Business, there is additional guidance to consider. See [Using enterprise-managed settings without organizations](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings/copilot-business-only).

## Supported clients

The following clients are supported, although not every client supports every property:

* Copilot CLI
* VS Code
* The GitHub Copilot app
* Copilot cloud agent
* JetBrains IDEs

For a full reference of supported keys, see [Enterprise managed settings](/en/copilot/reference/enterprise-administrators/enterprise-managed-settings).

## 1. Create a `.github-private` repository

You can host the `managed-settings.json` file in a `.github-private` repository owned by a designated organization in your enterprise. This allows you to keep your managed settings next to your custom agent profiles, in a place that members of the enterprise can view.

For instructions on **creating the repository and selecting it as your enterprise's source of client governance**, see [Creating a \`.github-private\` repository](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/create-github-private-repo).

The governance settings in this repository apply to all users who receive a Copilot license from your enterprise or any of its organizations, regardless of whether the user has access to the `.github-private` repository or the organization that owns it. We recommend giving the repository internal visibility, so that enterprise members can view the governance settings, and restricting edits of the `managed-settings.json` file to administrators and AI managers.

> \[!TIP] This is called a "server-managed" deployment. There are other methods of distributing managed settings to users, including mobile device management (MDM) and local file delivery. For more information, see [Choosing how to deploy enterprise-managed settings to users](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings/deploy-managed-settings).

## 2. Create the `managed-settings.json` file

In this example, we're using a very simple configuration that ensures users' conversations start in auto mode. This means Copilot will automatically choose the best model for a user's task from your enterprise's allowed models, which reduces rate limiting issues for users.

1. In the `.github-private` repository, create a file at `copilot/managed-settings.json`.

2. Add configuration to the file. For example:

   ```json copy
   {
     "model": "auto"
   }
   ```

3. Commit your changes to the default branch.

For a real rollout, **check the supported keys and their coverage across clients**. See [Enterprise managed settings](/en/copilot/reference/enterprise-administrators/enterprise-managed-settings).

## 3. Override the setting for specific teams

You can override supported properties of the `managed-settings.json` file for enterprise teams. In this example, we'll disable the auto model default for a team that needs to stick to specific models for specialized work.

After you complete this section, your `.github-private` repository will have the following structure:

* **`.github-private/`**
  * **`copilot/`**
    * **`managed-settings.json`**: `{ "model": { "overridable": "auto" } }`
    * **`team-mappings.json`**: `{ "no-auto.json": ["special-team"] }`
    * **`teams/`**
      * **`no-auto.json`**: `{ "model": "unmanaged" }`

### Steps

1. Create an enterprise team containing users who should not receive the auto mode default. In this example, we'll call it `special-team`. See [Creating enterprise teams](/en/enterprise-cloud@latest/admin/managing-accounts-and-repositories/managing-users-in-your-enterprise/create-enterprise-teams).

2. In your `copilot/managed-settings.json` file, mark the key as eligible for override using the `{ "overridable": VALUE }` syntax. The `VALUE` is the default when teams files do not declare a different value for a given key.

   For example, we will make `model` overridable for enterprise teams, with `auto` remaining the default for everyone else:

   ```json copy
   {
     "model": { "overridable": "auto" }
   }
   ```

3. In your `.github-private` repository, create a dedicated settings file for the enterprise team under `copilot/teams/`. For example: `copilot/teams/no-auto.json`.

   In this file, add configuration that provides values for overridable properties.

   The following example removes the control on auto model mode. Everything else remains governed by your `managed-settings.json` file.

   ```json copy
   {
     "model": "unmanaged"
   }
   ```

4. In your `.github-private` repository, create `copilot/team-mappings.json`. In this file, map the name of the enterprise team to its special configuration file. The key is the settings file name, and the value is an array of team slugs, so you can apply one file across multiple teams.

   ```json copy
   {
     "no-auto.json": ["special-team"]
   }
   ```

5. Commit and push your changes to the default branch.

Later, you can add different overrides for other keys and other teams. **For a more complete example**, see [Overriding enterprise-managed settings for teams](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings/override-settings-for-teams).

## 4. Validate and check the settings

Validate your repository-based settings, then confirm that supported clients receive the expected configuration.

### Validate server-managed settings

For server-managed deployments, GitHub automatically validates the settings in your selected `.github-private` repository. The validator checks the following files:

* `copilot/managed-settings.json`
* `copilot/team-mappings.json`
* Any files in `copilot/teams/` that are referenced in `copilot/team-mappings.json`

To review configuration issues:

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.
2. At the top of the page, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> AI controls**.
3. On the **Agents** tab, find the "Copilot settings validation" section.
4. Review the errors and warnings. Each issue identifies the affected file and JSON path.
5. To fix an issue, update the affected file and commit the change to the default branch of the `.github-private` repository. Then reload the **Agents** page to check the updated configuration.

If the validator finds no issues, the "Copilot settings validation" section isn't displayed. If validation is temporarily unavailable, your existing settings continue to apply. Reload the **Agents** page later to check again.

### Check settings on clients

After checking for validation issues, confirm that your settings are active for users and overridden for specific teams. In this example, new conversations should start in auto mode for most Copilot users in your enterprise. New conversations should not start in auto mode for members of the `special-team` enterprise team.

For server-managed deployments, users on a supported client see the specified settings within about an hour. This includes `copilot/managed-settings.json`, `copilot/team-mappings.json`, and files in `copilot/teams/`. Restarting the client or signing in again triggers an immediate refresh.

If a user does not see these settings, ensure they receive access to Copilot through your enterprise or one of its organizations. If a user receives a license from multiple billing entities, ensure they have selected your enterprise in the "Usage billed to" dropdown in their [personal Copilot settings](https://github.com/settings/copilot/features).

For MDM-managed deployments, clients check for updated policies hourly. For file-based deployments, restart the client to load an updated file. These deployment methods apply to all users with the settings installed on their machine, regardless of where their Copilot license comes from.

## Next step

Now you've created a simple managed settings setup, you can:

* Add additional governance properties to the file. See [Enterprise managed settings](/en/copilot/reference/enterprise-administrators/enterprise-managed-settings).
* Decide whether to deploy settings to users through other methods. See [Choosing how to deploy enterprise-managed settings to users](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/use-managed-settings/deploy-managed-settings).

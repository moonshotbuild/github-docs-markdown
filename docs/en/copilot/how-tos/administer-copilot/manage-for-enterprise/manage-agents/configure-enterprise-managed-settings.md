---
source_path: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings"
title: "Configuring enterprise-managed settings"
intro: "Configure enterprise managed settings to centrally control Copilot client behavior across your enterprise using server-managed, MDM-managed, or file-based deployment."
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
  - title: "Enterprise managed settings"
    href: "/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/configure-enterprise-managed-settings"
---

# Configuring enterprise-managed settings

Configure enterprise managed settings to centrally control Copilot client behavior across your enterprise using server-managed, MDM-managed, or file-based deployment.

With enterprise managed settings, enterprise owners can centrally define and distribute configuration settings to Copilot CLI and VS Code for users on your enterprise's Copilot plan, ensuring every member works within the same guardrails. Additional client support will follow.

These settings apply enterprise-wide, with no organization-level override. For each supported key, the `managed-settings.json` value takes precedence over any file-based configuration a user sets in their client.

Managed settings are loaded locally when the client starts, even if the device has no network connection. This means controls such as disabled bypass mode and restricted plugin configuration still apply before sign in or any server round trip, and remain active when users switch accounts.

## Defining settings

For detailed information on the available properties and syntax, see [Enterprise managed settings reference](/en/copilot/reference/enterprise-managed-settings-reference).

## Choosing a deployment method

There are multiple ways to deploy enterprise managed settings. Use the following guidelines to choose the right method for you. For any method, pilot on a small device group before broad deployment.

* **Server-managed**: Default for most enterprises and best for review workflows and audit history
* **MDM-managed**: Best when IT teams need device-group targeting through existing MDM tooling on macOS and Windows
* **File-based**: Available on all platforms, and useful when server-managed and MDM-managed deployment are not available, including developer environments such as containers and Codespaces

## Deploying server-managed settings

1. Create and configure your `.github-private` repository. See [Creating a \`.github-private\` repository](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-agents/create-github-private-repo).
2. In the repository, create or update `copilot/managed-settings.json`.
3. Add your enterprise policy keys and values in JSON format.
4. Commit and push your changes to the default branch.
5. Confirm that enterprise users are running a supported client. Updated settings are applied automatically within about an hour, or immediately after the client restarts or the user signs in again.

## Deploying MDM-managed settings

1. Create or update your `managed-settings.json` payload using the same JSON schema used for server-managed settings.

2. Deploy the payload using your enterprise MDM platform and standard rollout process.

3. Assign the policy to the target device groups.

   Clients do not need to restart, and check for updated policies on an hourly basis. In VS Code, an administrator can force a check for testing by running the `Developer: Sync Account Policy` command.

4. Confirm the settings took effect. See [Verifying the configuration has applied](#verifying-the-configuration-has-applied).

## Deploying file-based settings

1. Create or update a `managed-settings.json` file with the policy keys and values you want to enforce.
2. Distribute the file to managed machines using your standard device management process. Machines that don't receive the file are not restricted by this policy, so file-based deployment only provides coverage for the machines you actively distribute to.
3. Apply file permissions according to your enterprise security requirements.
4. Ask users to restart supported clients so the updated policy is loaded at startup.
5. Confirm the settings took effect. See [Verifying the configuration has applied](#verifying-the-configuration-has-applied).

## Verifying the configuration has applied

Once the configuration is committed, users on a supported client see the specified settings within about an hour, since clients periodically check the server for updated configuration. Restarting the client or signing in again applies the latest settings immediately.

If a user does not see these settings, ensure they receive access to Copilot through your enterprise or one of its organizations. If a user receives a license from multiple billing entities, ensure they have selected your enterprise in the "Usage billed to" dropdown in their [personal Copilot settings](https://github.com/settings/copilot/features).

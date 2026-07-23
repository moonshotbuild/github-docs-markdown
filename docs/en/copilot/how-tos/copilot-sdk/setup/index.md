---
source_path: "/en/copilot/how-tos/copilot-sdk/setup"
title: "Set up Copilot SDK"
intro: "Configure and deploy the GitHub Copilot SDK for your use case."
product: "GitHub Copilot"
document_type: "subcategory"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Copilot SDK"
    href: "/en/copilot/how-tos/copilot-sdk"
  - title: "Set up Copilot SDK"
    href: "/en/copilot/how-tos/copilot-sdk/setup"
---

# Set up Copilot SDK

Configure and deploy the GitHub Copilot SDK for your use case.

## Links

* [Azure managed identity with BYOK](/en/copilot/how-tos/copilot-sdk/setup/azure-managed-identity)

  The GitHub Copilot SDK's BYOK (bring your own key) supports static API keys, but Azure deployments often use Managed Identity (Microsoft Entra ID) instead of long-lived keys. The GitHub Copilot SDK is designed to compose with the Azure Identity SDK for maximum flexibility. Supply a bearer token provider callback that can fetch fresh tokens on demand using an Azure Identity SDK API.

* [Backend services setup](/en/copilot/how-tos/copilot-sdk/setup/backend-services)

  Run the Copilot SDK in server-side applications—APIs, web backends, microservices, and background workers. The CLI runs as a headless server that your backend code connects to over the network.

* [Default setup (bundled CLI)](/en/copilot/how-tos/copilot-sdk/setup/bundled-cli)

  The Node.js and .NET SDKs include the Copilot CLI as a dependency—your app ships with everything it needs, with no extra installation or configuration required.

* [Setup guides](/en/copilot/how-tos/copilot-sdk/setup/choosing-a-setup-path)

  These guides walk you through configuring the Copilot SDK for your specific use case—from personal side projects to production platforms serving thousands of users.

* [GitHub OAuth setup](/en/copilot/how-tos/copilot-sdk/setup/github-oauth)

  Let users authenticate with their GitHub accounts to use Copilot through your application. This supports individual accounts, organization memberships, and enterprise identities.

* [Local CLI setup](/en/copilot/how-tos/copilot-sdk/setup/local-cli)

  Use a specific CLI binary instead of the SDK's automatic CLI management. This is an advanced option—you supply the CLI path explicitly, and you are responsible for ensuring version compatibility with the SDK.

* [Multi-tenancy and server deployments](/en/copilot/how-tos/copilot-sdk/setup/multi-tenancy)

  Multi-user server mode means running the Copilot SDK from backend code that serves more than one human, tenant, workspace, or integration account. In this setup, the application owns request routing and authorization, while the SDK and runtime provide per-session state, per-session authentication, and explicit tool registration so one user's session does not inherit another user's tools or identity.

* [Scaling and multi-tenancy](/en/copilot/how-tos/copilot-sdk/setup/scaling)

  Design your Copilot SDK deployment to serve multiple users, handle concurrent sessions, and scale horizontally across infrastructure. This guide covers session isolation patterns, scaling topologies, and production best practices.

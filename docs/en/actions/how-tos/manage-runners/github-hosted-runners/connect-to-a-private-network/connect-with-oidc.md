---
source_path: "/en/actions/how-tos/manage-runners/github-hosted-runners/connect-to-a-private-network/connect-with-oidc"
title: "Using an API gateway with OIDC"
intro: "You can use OpenID Connect (OIDC) tokens to authenticate your workflow."
product: "GitHub Actions"
document_type: "article"
breadcrumbs:
  - title: "GitHub Actions"
    href: "/en/actions"
  - title: "How-tos"
    href: "/en/actions/how-tos"
  - title: "Manage runners"
    href: "/en/actions/how-tos/manage-runners"
  - title: "GitHub-hosted runners"
    href: "/en/actions/how-tos/manage-runners/github-hosted-runners"
  - title: "Connect to a private network"
    href: "/en/actions/how-tos/manage-runners/github-hosted-runners/connect-to-a-private-network"
  - title: "Connect with OIDC"
    href: "/en/actions/how-tos/manage-runners/github-hosted-runners/connect-to-a-private-network/connect-with-oidc"
---

# Using an API gateway with OIDC

You can use OpenID Connect (OIDC) tokens to authenticate your workflow.

## Using an API gateway with OIDC

With GitHub Actions, you can use OpenID Connect (OIDC) tokens to authenticate your workflow outside of GitHub Actions. For example, you could run an API gateway on the edge of your private network that authenticates incoming requests with the OIDC token and then makes API requests on behalf of your workflow in your private network.

The following diagram gives an overview of this solution's architecture:

![Diagram of an OIDC gateway architecture, starting with a GitHub Actions runner and ending with a private network's private service.](/assets/images/help/actions/actions-oidc-gateway.png)

It's important that you verify not just that the OIDC token came from GitHub Actions, but that it came specifically from your expected workflows, so that other GitHub Actions users aren't able to access services in your private network. You can use OIDC claims to create these conditions. For more information, see [OpenID Connect reference](/en/actions/reference/security/oidc#oidc-claims-used-to-define-trust-conditions-on-cloud-roles).

The main disadvantages of this approach are that you must implement the API gateway to make requests on your behalf, and you must run the gateway on the edge of your network.

The following advantages apply.

* You don't need to configure any firewalls, or modify the routing of your private network.
* The API gateway is stateless and scales horizontally to handle high availability and high throughput.

For more information, see [a reference implementation of an API Gateway](https://github.com/github/actions-oidc-gateway-example) in the github/actions-oidc-gateway repository. This implementation requires customization for your use case and is not ready-to-run as-is. For more information, see [OpenID Connect](/en/actions/concepts/security/openid-connect).

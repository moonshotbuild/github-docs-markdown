---
source_path: "/en/apps/creating-github-apps/authenticating-with-a-github-app"
title: "Authenticating with a GitHub App"
intro: "Learn how to authenticate with GitHub Apps."
product: "Apps"
document_type: "subcategory"
breadcrumbs:
  - title: "Apps"
    href: "/en/apps"
  - title: "Creating GitHub Apps"
    href: "/en/apps/creating-github-apps"
  - title: "Authenticate with a GitHub App"
    href: "/en/apps/creating-github-apps/authenticating-with-a-github-app"
---

# Authenticating with a GitHub App

Learn how to authenticate with GitHub Apps.

## Links

* [About authentication with a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/about-authentication-with-a-github-app)

  Your GitHub App can authenticate as itself, as an app installation, or on behalf of a user.

* [Authenticating as a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-as-a-github-app)

  You can authenticate as a GitHub App in order to generate an installation access token or manage your app.

* [Authenticating as a GitHub App installation](/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-as-a-github-app-installation)

  You can make your GitHub App authenticate as an installation in order to make API requests that affect resources owned by the account where the app is installed.

* [Authenticating with a GitHub App on behalf of a user](/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-with-a-github-app-on-behalf-of-a-user)

  Your GitHub App can perform actions on behalf of a user, like creating an issue, posting a comment, or creating a deployment.

* [Managing private keys for GitHub Apps](/en/apps/creating-github-apps/authenticating-with-a-github-app/managing-private-keys-for-github-apps)

  You can manage private keys to authenticate with your GitHub App.

* [Generating a JSON Web Token (JWT) for a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-json-web-token-jwt-for-a-github-app)

  Learn how to create a JSON Web Token (JWT) to authenticate to certain REST API endpoints with your GitHub App.

* [Generating an installation access token for a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-an-installation-access-token-for-a-github-app)

  Learn how to generate an installation access token for your GitHub App.

* [Generating a user access token for a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-user-access-token-for-a-github-app)

  You can generate a user access token for your GitHub App in order to attribute app activity to a user.

* [Refreshing user access tokens](/en/apps/creating-github-apps/authenticating-with-a-github-app/refreshing-user-access-tokens)

  To enforce regular token rotation and reduce the impact of a compromised token, you can configure your GitHub App to use user access tokens that expire.

* [Making authenticated API requests with a GitHub App in a GitHub Actions workflow](/en/apps/creating-github-apps/authenticating-with-a-github-app/making-authenticated-api-requests-with-a-github-app-in-a-github-actions-workflow)

  You can use an installation access token from a GitHub App to make authenticated API requests in a GitHub Actions workflow. You can also pass the token to a custom action to enable the action to make authenticated API requests.

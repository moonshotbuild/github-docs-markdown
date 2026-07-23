---
source_path: "/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-on-actions"
title: "Troubleshooting Dependabot on GitHub Actions"
intro: "This article provides troubleshooting information for issues you may encounter when using Dependabot with GitHub Actions."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Reference"
    href: "/en/code-security/reference"
  - title: "Supply chain security"
    href: "/en/code-security/reference/supply-chain-security"
  - title: "Troubleshoot Dependabot"
    href: "/en/code-security/reference/supply-chain-security/troubleshoot-dependabot"
  - title: "Dependabot on Actions"
    href: "/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-on-actions"
---

# Troubleshooting Dependabot on GitHub Actions

This article provides troubleshooting information for issues you may encounter when using Dependabot with GitHub Actions.

## Troubleshooting failures when Dependabot triggers existing workflows

After you set up Dependabot updates for GitHub.com, you may see failures when existing workflows are triggered by Dependabot events.

By default, GitHub Actions workflow runs that are triggered by Dependabot from `push`, `pull_request`, `pull_request_review`, or `pull_request_review_comment` events are treated as if they were opened from a repository fork. Unlike workflows triggered by other actors, this means they receive a read-only `GITHUB_TOKEN` and do not have access to any secrets that are normally available. This will cause any workflows that attempt to write to the repository to fail when they are triggered by Dependabot.

There are three ways to resolve this problem:

1. You can update your workflows so that they are no longer triggered by Dependabot using an expression like: `if: github.actor != 'dependabot[bot]'`. For more information, see [Evaluate expressions in workflows and actions](/en/actions/reference/workflows-and-actions/expressions).
2. You can modify your workflows to use a two-step process that includes `pull_request_target` which does not have these limitations. For more information, see [Troubleshooting Dependabot on GitHub Actions](/en/code-security/reference/supply-chain-security/troubleshoot-dependabot/dependabot-on-actions#restrictions-when-dependabot-triggers-events).
3. You can provide workflows triggered by Dependabot access to secrets and allow the `permissions` term to increase the default scope of the `GITHUB_TOKEN`.

Some troubleshooting advice is provided in this article. You can also see [Workflow syntax for GitHub Actions](/en/actions/reference/workflows-and-actions/workflow-syntax#jobsjob_idpermissions).

### Accessing secrets

When a Dependabot event triggers a workflow, the only secrets available to the workflow are Dependabot secrets. GitHub Actions secrets are **not available**. You must therefore store any secrets that are used by a workflow triggered by Dependabot events as Dependabot secrets. For more information, see [Configuring access to private registries for Dependabot](/en/code-security/how-tos/secure-your-supply-chain/manage-your-dependency-security/configure-access-to-private-registries#storing-credentials-for-dependabot-to-use).

Dependabot secrets are added to the `secrets` context and referenced using exactly the same syntax as secrets for GitHub Actions. For more information, see [Using secrets in GitHub Actions](/en/actions/how-tos/write-workflows/choose-what-workflows-do/use-secrets#using-encrypted-secrets-in-a-workflow).

If you have a workflow that will be triggered by Dependabot and also by other actors, the simplest solution is to store the token with the permissions required in an action and in a Dependabot secret with identical names. Then the workflow can include a single call to these secrets. If the secret for Dependabot has a different name, use conditions to specify the correct secrets for different actors to use.

For examples that use conditions, see [Automating Dependabot with GitHub Actions](/en/code-security/tutorials/secure-your-dependencies/automate-dependabot-with-actions).

To access a private container registry on AWS with a user name and password, a workflow must include a secret for `username` and `password`.

In this example, when Dependabot triggers the workflow, the Dependabot secrets with the names `READONLY_AWS_ACCESS_KEY_ID` and `READONLY_AWS_ACCESS_KEY` are used. If another actor triggers the workflow, the actions secrets with those names are used.

```yaml copy
# This workflow uses actions that are not certified by GitHub.
# They are provided by a third-party and are governed by
# separate terms of service, privacy policy, and support
# documentation.
name: CI
on:
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v6

      - name: Login to private container registry for dependencies
        uses: docker/login-action@3b4c5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f0a1b2c
        with:
          registry: https://1234567890.dkr.ecr.us-east-1.amazonaws.com
          username: ${{ secrets.READONLY_AWS_ACCESS_KEY_ID }}
          password: ${{ secrets.READONLY_AWS_ACCESS_KEY }}

      - name: Build the Docker image
        run: docker build . --file Dockerfile --tag my-image-name:$(date +%s)
```

### Changing `GITHUB_TOKEN` permissions

By default, GitHub Actions workflows triggered by Dependabot get a `GITHUB_TOKEN` with read-only permissions. You can use the `permissions` key in your workflow to increase the access for the token:

```yaml copy
name: CI
on: pull_request

# Set the access for individual scopes, or use permissions: write-all
permissions:
  pull-requests: write
  issues: write
  ...

jobs:
  ...
```

For more information, see [Use GITHUB\_TOKEN for authentication in workflows](/en/actions/tutorials/authenticate-with-github_token#modifying-the-permissions-for-the-github_token).

## Manually re-running a workflow

When you manually re-run a Dependabot workflow, it will run with the same privileges as before even if the user who initiated the rerun has different privileges. For more information, see [Re-running workflows and jobs](/en/actions/how-tos/manage-workflow-runs/re-run-workflows-and-jobs).

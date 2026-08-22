---
source_path: "/en/copilot/how-tos/github-copilot-app/use-byok-models"
title: "Using your own LLM models in the GitHub Copilot app"
intro: "Connect a model from an external provider of your choice by supplying your own API key, then use the model in agent sessions."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "GitHub Copilot app"
    href: "/en/copilot/how-tos/github-copilot-app"
  - title: "Use your own model provider"
    href: "/en/copilot/how-tos/github-copilot-app/use-byok-models"
---

# Using your own LLM models in the GitHub Copilot app

Connect a model from an external provider of your choice by supplying your own API key, then use the model in agent sessions.

> \[!NOTE]
> Support to use your own model provider in the GitHub Copilot app is in public preview and subject to change.

You can configure the GitHub Copilot app to use your own LLM provider, also called BYOK (Bring Your Own Key), instead of GitHub-hosted models. You can set up your model provider when you first open the app or later in app settings.

You must sign in with a GitHub account to use the app, but you do not need a Copilot plan if you use your own model provider. If you do have a Copilot plan, you can use both your own model provider and GitHub-hosted models in the same app.

> \[!NOTE]
> This article is for users who want to configure their own LLM provider settings on their local machine. To set up custom models for users in an organization or enterprise, see [Enabling custom models for GitHub Copilot in your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/enable-custom-models) and [Enabling custom models for GitHub Copilot in your enterprise](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/enable-custom-models).

## Supported providers

GitHub Copilot app supports these model providers:

* OpenAI
* Azure OpenAI
* Microsoft Foundry
* Anthropic
* Ollama
* Foundry Local
* LM Studio
* Any OpenAI-compatible HTTP endpoint

## Prerequisites

* The GitHub Copilot app is installed. For setup steps, see [Getting started with the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/getting-started).
* You have any required credentials, such as API key, for your model provider.

## Set up a model provider

If you are setting up the app for the first time and do not have a Copilot plan, you can choose to set up your own model provider during onboarding.

To add or update a model provider later:

1. Open the GitHub Copilot app.
2. Open app settings, then click **Model providers**.
3. Click **Add provider**.
4. Select your provider.
5. Enter the provider details. This varies by provider but may include the display name, base URL, and API key.
6. Click **Add provider** to save the provider.

After you add a provider, its models appear in the model picker alongside GitHub-hosted models. You can select the model and use it in a session. For more information, see [Working with agent sessions in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/agent-sessions).

Provider credentials are stored in the system credential store and are never displayed in the UI.

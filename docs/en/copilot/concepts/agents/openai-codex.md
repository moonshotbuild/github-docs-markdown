---
source_path: "/en/copilot/concepts/agents/openai-codex"
title: "OpenAI Codex"
intro: "Use the OpenAI Codex coding agent and Visual Studio Code extension powered by Copilot."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "Concepts"
    href: "/en/copilot/concepts"
  - title: "Agents"
    href: "/en/copilot/concepts/agents"
  - title: "OpenAI Codex"
    href: "/en/copilot/concepts/agents/openai-codex"
---

# OpenAI Codex

Use the OpenAI Codex coding agent and Visual Studio Code extension powered by Copilot.

> \[!NOTE] OpenAI Codex integration is currently in public preview.

## Introduction

The OpenAI Codex coding agent and the VS Code OpenAI Codex integration use the Codex SDK and can be powered by your existing Copilot subscription. For more information about how OpenAI Codex works, see the [OpenAI Codex documentation](https://developers.openai.com/codex).

## OpenAI Codex coding agent

Before you can assign tasks to OpenAI Codex coding agent, it must be enabled. See [Managing GitHub Copilot policies as an individual subscriber](/en/copilot/how-tos/manage-your-account/manage-policies#enabling-or-disabling-third-party-coding-agents-in-your-repositories).

To learn more about using third-party agents on GitHub, see [About third-party coding agents](/en/copilot/concepts/agents/about-third-party-coding-agents).

### Supported models

When starting a task with the OpenAI Codex coding agent, you can select the AI model used by the agent. The following models are available:

* Auto
* GPT-5.3-Codex
* GPT-5.4
* GPT-5.4 nano

If you select **Auto**, Copilot auto model selection will select the best model based on availability and to help reduce rate limiting. For more information, see [About Copilot auto model selection](/en/copilot/concepts/models/auto-model-selection).

## VS Code extension

> \[!NOTE] The "Sign in with Copilot" option in the OpenAI Codex VS Code extension is only available to GitHub Copilot Pro+ and Copilot Max subscribers.

Use "Sign in with Copilot" when launching the extension. Copilot Pro+ and Copilot Max users can see this integration in the [Agent Sessions view](https://code.visualstudio.com/docs/copilot/chat/chat-sessions#_agent-sessions-view) in VS Code Insiders along with progress on their running tasks. All usage is subject to GitHub rate limits and billing. See [Requests in GitHub Copilot (legacy)](/en/copilot/reference/copilot-billing/request-based-billing-legacy/copilot-requests#premium-features).

### Model availability

A subset of available models may only be available in the OpenAI Codex extension. Model availability and visibility is not governed by Copilot model configuration policies.

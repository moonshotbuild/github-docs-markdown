---
source_path: "/en/copilot/concepts/agent-capabilities/about-agents/about-third-party-coding-agents"
title: "Third-party coding agents"
intro: "You can use third-party coding agents alongside Copilot to work asynchronously on your development tasks on GitHub."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "Concepts"
    href: "/en/copilot/concepts"
  - title: "Agent capabilities"
    href: "/en/copilot/concepts/agent-capabilities"
  - title: "About agents"
    href: "/en/copilot/concepts/agent-capabilities/about-agents"
  - title: "Third-party coding agents"
    href: "/en/copilot/concepts/agent-capabilities/about-agents/about-third-party-coding-agents"
---

# Third-party coding agents

You can use third-party coding agents alongside Copilot to work asynchronously on your development tasks on GitHub.

> [!NOTE] Third-party coding agents are currently in public preview.

## Introduction

You can use third-party coding agents alongside Copilot to work asynchronously on your development tasks. You can assign an existing issue or give a prompt to an agent, which will work on the required changes and create artifact, such as a pull request. When the agent finishes, it will tell you, and a pull request was created it will request a review from you. You can then leave comments asking the agent to iterate.

Coding agents are subject to the same security protections, mitigations, and limitations as Copilot. To learn more about how you can use coding agents, see [GitHub Copilot on GitHub.com and GitHub Mobile](/en/copilot/concepts/copilot-surfaces/copilot-on-github).

### Where you can use coding agents

You can kick off tasks with coding agents in the following locations:

* **The Agents tab**: In the Agents tab of a repository (`https://github.com/OWNER/REPO_NAME/agents`), click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> under the prompt box to select an agent, then kick off a new task and watch the agent get to work.
* **Issues**: Assign the agent to an existing issue in a repository.
* **Pull requests**: Mention `@AGENT_NAME` in a comment on an existing pull request to ask it to make changes.
* On [**GitHub Mobile**](/en/copilot/how-tos/copilot-on-github/chat-with-copilot/chat-in-mobile): From the **Home** view, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-plus" aria-label="plus" role="img"><path d="M7.75 2a.75.75 0 0 1 .75.75V7h4.25a.75.75 0 0 1 0 1.5H8.5v4.25a.75.75 0 0 1-1.5 0V8.5H2.75a.75.75 0 0 1 0-1.5H7V2.75A.75.75 0 0 1 7.75 2Z"></path></svg> to start a new agent session.
* In [**Visual Studio Code**](https://code.visualstudio.com/docs/copilot/agents/overview#_create-an-agent-session): Start a new session in the chat view, or delegate an existing session to a different agent.

### Making coding agents available

Before you can assign tasks to coding agents on GitHub, they must be enabled in your account settings, your organization policies, or the "Agents" section of an enterprise's AI controls.

* For **GitHub Copilot Pro, GitHub Copilot Pro+, and GitHub Copilot Max subscribers**, see [Managing GitHub Copilot policies as an individual subscriber](/en/copilot/how-tos/manage-your-account/manage-policies).
* For **GitHub Copilot Business and GitHub Copilot Enterprise subscribers**, see [Managing policies and features for GitHub Copilot in your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies) or [Managing policies and features for GitHub Copilot in your enterprise](/en/enterprise-cloud@latest/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies).

These policies do not apply to **local** agents in Visual Studio Code. To configure agent settings in Visual Studio Code, see [Types of agents](https://code.visualstudio.com/docs/copilot/agents/overview#_types-of-agents) in the Visual Studio Code documentation. To adjust enterprise agent settings in Visual Studio Code, see [Enable or disable the use of agents](https://code.visualstudio.com/docs/enterprise/ai-settings#_enable-or-disable-the-use-of-agents) in the Visual Studio Code documentation.

## Supported coding agents

When starting a task with a third-party agent, you can select the AI model used by the agent. You may find that different models perform better, or provide more useful responses, depending on the type of task. For help deciding which model to use, see [AI model comparison](/en/copilot/reference/ai-models/model-comparison).

The following third-party agents are supported on GitHub.

### Anthropic Claude

> [!NOTE]
> The Anthropic Claude coding agent is currently in public preview.

The Anthropic Claude coding agent uses the Claude Agent SDK and can be powered by your existing Copilot subscription. For information about Anthropic Claude, see the [Anthropic Claude documentation](https://platform.claude.com/docs/en/agent-sdk/overview).

#### Anthropic Claude supported models

* Auto
* Claude Sonnet 4.6
* Claude Sonnet 5
* Claude Opus 4.8
* Claude Opus 4.8 (fast mode) (preview)
* Claude Opus 5
* Claude Fable 5.1

If you select **Auto**, it will choose one of the available models listed above. **Auto** in Anthropic Claude coding agent does **not** leverage Copilot auto model selection.

### OpenAI Codex

> [!NOTE]
> OpenAI Codex integration is currently in public preview.

The OpenAI Codex coding agent and the VS Code OpenAI Codex integration use the Codex SDK and can be powered by your existing Copilot subscription. For more information about how OpenAI Codex works, see the [OpenAI Codex documentation](https://developers.openai.com/codex).

#### OpenAI Codex supported models

* Auto
* GPT-5.3-Codex
* GPT-5.4 nano

If you select **Auto**, it will choose one of the available models listed above. **Auto** in OpenAI Codex coding agent does **not** leverage Copilot auto model selection.

#### VS Code extension

> [!NOTE]
> The "Sign in with Copilot" option in the OpenAI Codex VS Code extension is only available to GitHub Copilot Pro+ and Copilot Max subscribers.

Use "Sign in with Copilot" when launching the extension. You can see this integration in the [Agent Sessions view](https://code.visualstudio.com/docs/copilot/chat/chat-sessions#_agent-sessions-view) in VS Code Insiders along with progress on their running tasks. All usage is subject to GitHub rate limits and billing.

A subset of available models may only be available in the OpenAI Codex extension. Model availability and visibility is not governed by Copilot model configuration policies.

## Security validation

When a third-party coding agent creates or modifies code, GitHub automatically scans the generated code for security issues and attempts to resolve them before the pull request is finalized. This reduces the likelihood of the agent introducing problems such as hardcoded secrets, insecure dependencies, and other vulnerabilities.

The following tools and processes scan for security issues:

* **CodeQL code scanning** identifies code security issues.
* **Secret scanning** detects sensitive information such as API keys, tokens, and other secrets.
* Newly introduced dependencies are checked against the **GitHub Advisory Database** for malware advisories and CVSS-rated High or Critical vulnerabilities.

Security validation does not require a GitHub Advanced Security license.

## Usage costs

Coding agents consume **GitHub Actions minutes** and **AI credits**. Each agent session consumes AI credits based on the model used and the number of tokens processed.

Within your included GitHub Actions minutes and AI credits, you can use agents without incurring additional costs. See [Usage-based billing for organizations and enterprises](/en/copilot/concepts/billing-and-usage/organizations-and-enterprises/billing).

## Partner agents

When enabling partner agents in your user or organization Copilot settings, a GitHub App will be installed for the corresponding agent.

* **Allow Claude coding agent** will install `anthropic code agent`
* **Allow Codex coding agent** will install `openai code agent`

Actions taken by these GitHub Apps will be visible in your audit log, but the GitHub Apps themselves will not be visible in your account's list of GitHub App installations.

## Next steps

* To start managing agents, see [Managing agent sessions](/en/copilot/how-tos/copilot-on-github/use-copilot-agents/manage-and-track-agents).
* To learn how AI models are hosted and served, see [Hosting of models for GitHub Copilot](/en/copilot/reference/ai-models/model-hosting).

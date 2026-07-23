---
source_path: "/en/copilot/how-tos/github-copilot-app/agent-sessions"
title: "Working with agent sessions in the GitHub Copilot app"
intro: "Run multiple isolated agent sessions simultaneously, each with its own branch, and steer them using different session modes, models, and tools."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "GitHub Copilot app"
    href: "/en/copilot/how-tos/github-copilot-app"
  - title: "Agent sessions"
    href: "/en/copilot/how-tos/github-copilot-app/agent-sessions"
---

# Working with agent sessions in the GitHub Copilot app

Run multiple isolated agent sessions simultaneously, each with its own branch, and steer them using different session modes, models, and tools.

## Starting a session

Each session in the GitHub Copilot app runs in its own isolated workspace, so you can run multiple sessions in parallel and make progress on several tasks without conflicts.

1. In the sidebar next to **Sessions**, click **+** to start a new session.
2. Choose a project—you can use a folder already on your machine, choose from GitHub, or clone from a Git URL for repositories hosted outside GitHub (for example, on Azure DevOps) or for private repositories without app access.
3. From the dropdown under the prompt box, choose where the session should run: in a new working tree, in your local repository, or in a cloud sandbox. Cloud sandboxes for Copilot (public preview) are fully isolated environments hosted by GitHub.
4. Select a session mode, model, and reasoning effort from the dropdowns below the prompt field. If you choose **Auto** for the model, the app selects the optimal model for your task based on task complexity.
5. Describe the task in the prompt field. You can reference issues with `#`, add files with `@`, or use `/` for commands.

The agent starts working. Your active sessions appear in the sidebar grouped by repository—click any session to switch to it.

## Choosing a session mode

The session mode controls how much autonomy the agent has. You can set the mode from the dropdown below the prompt field and change it at any time.

* **Interactive**: You and the agent work together. The agent suggests changes and waits for your input before proceeding.
* **Plan**: The agent creates a plan first. You review and approve the plan before the agent executes it.
* **Autopilot**: The agent works fully autonomously—writing code, running tests, and iterating without waiting for input.

## Choosing a model

You can select a model and reasoning effort from the dropdowns below the prompt field. Higher reasoning effort gives the agent more time to think through complex problems but may take longer. You can change both settings at any time during a session.

If you choose **Auto** in the model picker, the app automatically selects the optimal model for your task based on task complexity. After the session starts, the picker next to **Auto** shows which model handled each response. For more information, see [About Copilot auto model selection](/en/copilot/concepts/auto-model-selection).

If you configured your own model provider in the app, those models also appear in the picker. For setup steps, see [Using your own LLM models in the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/use-byok-models).

Hover over the <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-info" aria-label="the info icon" role="img"><path d="M0 8a8 8 0 1 1 16 0A8 8 0 0 1 0 8Zm8-6.5a6.5 6.5 0 1 0 0 13 6.5 6.5 0 0 0 0-13ZM6.5 7.75A.75.75 0 0 1 7.25 7h1a.75.75 0 0 1 .75.75v2.75h.25a.75.75 0 0 1 0 1.5h-2a.75.75 0 0 1 0-1.5h.25v-2h-.25a.75.75 0 0 1-.75-.75ZM8 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path></svg> icon in the model picker to see model details.

## Using quick chats

**Quick chats** in the sidebar opens a conversation mode without creating a dedicated branch or worktree. Use it for brainstorming, asking questions, or exploring ideas before starting a session. Your chat history is saved and listed by conversation name.

## Using `/security-review` in app sessions

> \[!NOTE]
> The `/security-review` slash command is currently in public preview and subject to change.

You can run the `/security-review` slash command in an active agent session to review your current workstream changes for high-confidence vulnerabilities. The command returns prioritized findings with severity and confidence scores, plus suggested fixes you can apply and verify in the same session.

1. Open an active session that has in-progress code changes.
2. In the prompt box, type `/security-review` and press <kbd>Enter</kbd>.
3. Review the findings, then update your code changes as needed.

This lightweight, on-demand review complements GitHub code scanning, Dependabot, and secret scanning by giving you an initial check on your local changes before opening a pull request.

## Using the rubber duck agent

The rubber duck agent is a built-in agent that acts as a constructive critic, reviewing your current plan, implementation, or tests and returning concrete feedback. The agent runs on a different model from the one driving your current session.

When rubber duck is enabled, Copilot can consult it automatically at key points while it works. The main session agent passes work to the rubber duck agent, receives the critique, then decides how to apply that feedback before continuing.

> \[!NOTE]
> The rubber duck agent is currently only available if the main agent is using a Claude or GPT large language model.

You can also manually ask Copilot to get a review from the rubber duck agent.

1. Open an active session.
2. In the prompt box, type `/rubber-duck` and ask for a critique of your current plan, implementation, or tests.

For more information on the rubber duck agent, see [About the rubber duck agent](/en/copilot/concepts/agents/copilot-cli/rubber-duck).

## Using `/chronicle` with app sessions

Because the GitHub Copilot app is built on GitHub Copilot CLI, you can use Copilot CLI session history features such as `/chronicle` to get insights from work you did in the app and in other Copilot CLI sessions.

For example, you can use `/chronicle standup` to summarize recent work. For more information, see [Using GitHub Copilot CLI session data](/en/copilot/how-tos/copilot-cli/use-copilot-cli/chronicle).

## Using voice dictation

You can use voice dictation to speak prompts in a session instead of typing them.

Before you can use voice dictation, you need to configure it in the app settings.

1. Open the app settings, then select the **Voice dictation** tab.
2. Choose a keyboard shortcut.
3. Allow microphone access in your operating system settings.
4. Download a local transcription model.

After setup, use your shortcut to start and stop voice transcription. The app inserts transcribed text into the prompt box so you can review or edit it before sending.

## Keyboard shortcuts

The GitHub Copilot app supports keyboard shortcuts to help you navigate sessions, switch between workspaces, and perform common actions. To see available shortcuts, open the app, go to **Help**, then **Keyboard Shortcuts**.

You can also start a session directly in the app using deep links from markdown files, third-party tools, or scripts. For more information, see [Using deep links to open the GitHub Copilot app](/en/copilot/how-tos/github-copilot-app/open-with-deep-links).

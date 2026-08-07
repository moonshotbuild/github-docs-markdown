---
source_path: "/en/copilot/how-tos/copilot-sdk/features"
title: "Features"
intro: "These guides cover the capabilities you can add to your Copilot SDK application. Each guide includes examples in supported languages (TypeScript, Python, Go, .NET, Java, and Rust) where available."
product: "GitHub Copilot"
document_type: "subcategory"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Copilot SDK"
    href: "/en/copilot/how-tos/copilot-sdk"
  - title: "Features"
    href: "/en/copilot/how-tos/copilot-sdk/features"
---

# Features

These guides cover the capabilities you can add to your Copilot SDK application. Each guide includes examples in supported languages (TypeScript, Python, Go, .NET, Java, and Rust) where available.

## Links

* [The agent loop](/en/copilot/how-tos/copilot-sdk/features/agent-loop)

  How the Copilot CLI processes a user message end-to-end: from prompt to session.idle.

* [Cloud sessions](/en/copilot/how-tos/copilot-sdk/features/cloud-sessions)

  Cloud sessions run Copilot work on GitHub-hosted compute through Mission Control. Use them when your app should create a session that executes remotely instead of starting a local Copilot CLI session on the user's machine or your server.

* [Custom agents and sub-agent orchestration](/en/copilot/how-tos/copilot-sdk/features/custom-agents)

  Define specialized agents with scoped tools and prompts, then let Copilot orchestrate them as sub-agents within a single session. For dispatching multiple sub-agents in parallel, see Fleet mode.

* [Fleet mode](/en/copilot/how-tos/copilot-sdk/features/fleet-mode)

  Fleet mode is Copilot's parallel orchestration pattern for work that can be split across independent sub-agents. In the runtime research notes, fleet mode is described as "the runtime's built-in pattern for dispatching multiple sub-agents in parallel via the task tool, with SQL todos as the shared coordination state." Use it when one parent session should coordinate several workers, collect their results, and continue the conversation with the combined context.

* [Working with hooks](/en/copilot/how-tos/copilot-sdk/features/hooks)

  Hooks let you plug custom logic into every stage of a Copilot session—from the moment it starts, through each user prompt and tool call, to the moment it ends. This guide walks through practical use cases so you can ship permissions, auditing, notifications, and more without modifying the core agent behavior.

* [Image input](/en/copilot/how-tos/copilot-sdk/features/image-input)

  Send images to Copilot sessions as attachments. There are two ways to attach images:

* [Using MCP servers with the GitHub Copilot SDK](/en/copilot/how-tos/copilot-sdk/features/mcp)

  The Copilot SDK can integrate with MCP servers (Model Context Protocol) to extend the assistant's capabilities with external tools. MCP servers run as separate processes and expose tools (functions) that Copilot can invoke during conversations.

* [Plugin directories](/en/copilot/how-tos/copilot-sdk/features/plugin-directories)

  A plugin is a directory that bundles SDK extensions — skills, hooks, MCP servers, custom agents, and LSP configuration — behind a single manifest. Pointing the SDK at a plugin directory loads everything the plugin contributes, so you can ship reusable capability packs without writing per-extension wiring in every host application.

* [Remote sessions](/en/copilot/how-tos/copilot-sdk/features/remote-sessions)

  Remote sessions let users access their Copilot session from GitHub web and mobile via Mission Control. When enabled, the SDK connects each session to Mission Control, producing a URL that can be shared as a link or QR code.

* [Session limits](/en/copilot/how-tos/copilot-sdk/features/session-limits)

  Session limits let an application set an AI Credits budget for a Copilot session. Use sessionLimits when creating or resuming a session to set a soft cap for the current accounting window.

* [Session resume and persistence](/en/copilot/how-tos/copilot-sdk/features/session-persistence)

  This guide walks you through the SDK's session persistence capabilities—how to pause work, resume it later, and manage sessions in production environments.

* [Custom skills](/en/copilot/how-tos/copilot-sdk/features/skills)

  Skills are reusable prompt modules that extend Copilot's capabilities. Load skills from directories to give Copilot specialized abilities for specific domains or workflows.

* [Steering and queueing](/en/copilot/how-tos/copilot-sdk/features/steering-and-queueing)

  Two interaction patterns let users send messages while the agent is already working: steering redirects the agent mid-turn, and queueing buffers messages for sequential processing after the current turn completes.

* [Streaming session events](/en/copilot/how-tos/copilot-sdk/features/streaming-events)

  Every action the Copilot agent takes—thinking, writing code, running tools—is emitted as a session event you can subscribe to. This guide is a field-level reference for each event type so you know exactly what data to expect without reading the SDK source.

* [Usage and billing metrics](/en/copilot/how-tos/copilot-sdk/features/usage-and-billing)

  This guide shows how to read token counts, context-window utilization, AI credit cost, and account quota from a Copilot SDK application. Examples are shown for TypeScript, Python, Go, .NET, Java, and Rust.

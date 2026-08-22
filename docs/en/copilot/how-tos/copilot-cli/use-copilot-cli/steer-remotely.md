---
source_path: "/en/copilot/how-tos/copilot-cli/use-copilot-cli/steer-remotely"
title: "Steering a GitHub Copilot CLI session from another device"
intro: "Enable remote control for a Copilot CLI session so you can monitor progress, respond to prompts, and continue working from GitHub.com or GitHub Mobile."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Copilot CLI"
    href: "/en/copilot/how-tos/copilot-cli"
  - title: "Use Copilot CLI"
    href: "/en/copilot/how-tos/copilot-cli/use-copilot-cli"
  - title: "Steer a session remotely"
    href: "/en/copilot/how-tos/copilot-cli/use-copilot-cli/steer-remotely"
---

# Steering a GitHub Copilot CLI session from another device

Enable remote control for a Copilot CLI session so you can monitor progress, respond to prompts, and continue working from GitHub.com or GitHub Mobile.

Remote control lets you connect to a running Copilot CLI session from any browser or from GitHub Mobile. You can view session output, respond to permission requests, and continue working in the session without being at the machine where the session is running.

This article explains how to enable and use remote control. For more conceptual information, see [About remote control of GitHub Copilot CLI sessions](/en/copilot/concepts/agents/copilot-cli/about-remote-control).

Remote access is different from session syncing. Your Copilot CLI sessions are synced to your GitHub account by default, and synced sessions appear as view-only on GitHub.com and GitHub Mobile. These sessions are not steerable. To steer a session remotely, you must enable remote control. For more information about session syncing, see [About GitHub Copilot CLI session data](/en/copilot/concepts/agents/copilot-cli/chronicle#session-syncing).

## Prerequisites

* The machine where the CLI session is running must be online, with the session actively running in a terminal.

  > \[!TIP]
  > Use the `/keep-alive` slash command to prevent your machine from going to sleep while you're away. See [Preventing your machine from going to sleep](#preventing-your-machine-from-going-to-sleep).

* Remote control does not require a Git repository hosted on GitHub.com. You can enable remote control from directories that are not themselves Git repositories, including parent directories containing multiple repositories, and from repositories hosted somewhere other than GitHub.com. Sessions started outside of a GitHub repository appear unassociated with any repository ("no repository") and are only listed on your agents page at [github.com/copilot/agents](https://github.com/copilot/agents). Sessions started inside a GitHub repository also appear on that repository's **Agents** tab.

  In some cases, the CLI may still be unable to resolve the working directory's repository—for example, if a Git remote is configured but inaccessible. When this happens, remote control is disabled and the CLI displays a "Remote session disabled" message.

## Enabling remote control for a session

You can enable remote control in several ways:

* With a slash command during an interactive session.
* With a command-line option when you start Copilot CLI.
* By configuring the CLI to enable remote control by default for all interactive sessions.
* From JetBrains IDE settings before you start a session.

### Using the `/remote` slash command

If you are already in an interactive session and want to enable remote control, enter:

```copilot copy
/remote on
```

The CLI connects to GitHub.com and displays details for accessing the session remotely—see [Accessing a session from GitHub.com](#accessing-a-session-from-githubcom) and [Accessing a session from GitHub Mobile](#accessing-a-session-from-github-mobile) later in this article.

You can use the `/remote` slash command without an argument to check the current remote control status, or to redisplay the remote access details if remote control is currently enabled. If you want to end the remote connection for the current session, enter `/remote off`.

### Using the `--remote` command-line option

If you think you may want to access a session remotely, you can start the CLI with the `--remote` command-line option. This avoids the need to remember to use the `/remote` slash command during the session.

```bash copy
copilot --remote
```

Details for accessing the session remotely are displayed when the interactive session starts and can be displayed again at any time by using the `/remote` slash command.

### Configuring remote control to always be enabled

If you always want your interactive CLI sessions to be remotely accessible, add the following to your Copilot settings file (typically located at `~/.copilot/settings.json`):

```json copy
{
  "remoteSessions": true
}
```

To override this setting for a particular session, use the `--no-remote` option when you start the session:

```bash copy
copilot --no-remote
```

> \[!NOTE]
> The command-line options `--remote` and `--no-remote` always take precedence over the `remote` setting in the settings file.

### Using JetBrains IDE settings

If you use Copilot CLI from a JetBrains IDE, you can enable remote control from the IDE before you start a session.

1. In your JetBrains IDE, click the **File** menu (Windows), or the name of the application in the menu bar (macOS), then click **Settings**.
2. In the left sidebar click **Tools**, click **GitHub Copilot**, then click **Chat**.
3. Select **Enable Copilot CLI Remote**.
4. Start an interactive Copilot CLI session from the IDE.

When this setting is enabled, you can use `/remote` in the session at any time to view the current remote control status or redisplay the links and QR code for accessing the session remotely.

## Accessing a session from GitHub.com

When you enable remote control, the CLI displays a link to the session on GitHub.com.

Use the link to access the session in your default web browser. You must be signed in to GitHub with the same account that started the CLI session.

You can also access the session without the link:

1. Log on to GitHub.com on any computer.

2. In the top-left corner of GitHub, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-three-bars" aria-label="Open menu" role="img"><path d="M1 2.75A.75.75 0 0 1 1.75 2h12.5a.75.75 0 0 1 0 1.5H1.75A.75.75 0 0 1 1 2.75Zm0 5A.75.75 0 0 1 1.75 7h12.5a.75.75 0 0 1 0 1.5H1.75A.75.75 0 0 1 1 7.75ZM1.75 12h12.5a.75.75 0 0 1 0 1.5H1.75a.75.75 0 0 1 0-1.5Z"></path></svg>.

3. Click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> Copilot**.

   Your CLI session is listed under "Recent agent sessions."

4. Optionally, use the **Type** filter at the top right of the list to show only Copilot CLI sessions.

5. Click your Copilot CLI session to open it.

If you started the session from a local copy of a GitHub repository, you can also access the session from the **Agents** tab of that repository on GitHub.com.

> \[!IMPORTANT]
> Remotely accessible sessions are user-specific: you can only access your own Copilot CLI sessions. Other GitHub users cannot access your sessions.

## Accessing a session from GitHub Mobile

A Copilot CLI session is available in GitHub Mobile as soon as you enable remote control. To find your session in GitHub Mobile:

1. Tap the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> Copilot** button in the bottom right corner of the screen.

   The session is listed under "Agent sessions."

2. Tap the session to open it.

### Use a QR code to quickly open a session on your phone

1. In an interactive session, enter the `/remote` slash command to redisplay the remote session details.

2. Press <kbd>Ctrl</kbd>+<kbd>E</kbd> to toggle on/off display of a QR code.

   > \[!NOTE]
   > This keyboard shortcut expands/collapses all details in the session conversation, not just the QR code. It only works if the input field is currently empty.

3. Scan the QR code with your phone to go directly to the session in GitHub Mobile.

## Preventing your machine from going to sleep

You can use the `/keep-alive` slash command to prevent your machine from going to sleep. This allows you to maintain the remote connection and continue interacting with the session from GitHub.com or GitHub Mobile.

In an interactive session, enter `/keep-alive OPTION`, where `OPTION` is one of:

* `on`: Prevents the machine from going to sleep while the CLI session is active.
* `off`: Allows the machine to go to sleep as normal.
* `busy`: Prevents the machine from going to sleep only while Copilot is working on a task. Once the agent completes a task the machine can go to sleep as normal. The machine will not go to sleep if Copilot is waiting for you to respond to a request for input from you.
* `NUMBERm`, `NUMBERh`, or `NUMBERd` (for example, `30m`, `8h`, `1d`): Prevents the machine from going to sleep for a specific number of minutes, hours, or days. If a bare number is provided without a suffix, it is treated as minutes.

Without passing an `OPTION`, the `/keep-alive` command displays the current keep-alive status.

## Reviewing previous sessions

You can view old Copilot CLI sessions on GitHub.com or in GitHub Mobile.

1. Go to your list of recent agent sessions on GitHub.com or in GitHub Mobile. See [Accessing a session from github.com](#accessing-a-session-from-githubcom) and [Accessing a session from GitHub Mobile](#accessing-a-session-from-github-mobile) earlier in this article.
2. Click or tap the session you want to review.

On GitHub.com, a message tells you the `copilot --resume` command to use if you want to resume the session. Enter this command in your terminal on the machine where you ran that session.

## Resuming a session

When you use `copilot --continue` or `copilot --resume` to resume a CLI session for which remote control was enabled, remote control is automatically re-enabled.

## Preventing remote control

Remote control is disabled by default, but may be enabled in your Copilot settings file (typically `~/.copilot/settings.json`). You can ensure a session is not remotely controllable by:

* **For a single session**: Start the CLI with `--no-remote` to prevent remote control for that session, regardless of your settings file value.
* **Permanently**: Remove the `"remoteSessions": true` setting from `~/.copilot/settings.json`, or set it to `false`.

Enterprise owners can also restrict remote control of sessions hosted on your device using enterprise managed settings, regardless of your personal settings. Depending on the configured policy, remote control of sessions on your device may be disabled entirely, or only available to a controlling client that is SSO-authorized for specific organizations. This doesn't affect your ability to remotely control your own sessions hosted on other devices. See [Enterprise managed settings](/en/copilot/reference/enterprise-administrators/enterprise-managed-settings).

## Further reading

* [Copilot CLI sessions in Visual Studio Code](https://code.visualstudio.com/docs/copilot/agents/copilot-cli) in the VS Code documentation.

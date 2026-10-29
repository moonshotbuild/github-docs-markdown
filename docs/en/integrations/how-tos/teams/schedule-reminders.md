---
source_path: "/en/integrations/how-tos/teams/schedule-reminders"
title: "Scheduling pull request reminders in Teams"
intro: "Set up reminders for pending pull request reviews in Teams."
product: "Integrations"
document_type: "article"
breadcrumbs:
  - title: "Integrations"
    href: "/en/integrations"
  - title: "How-tos"
    href: "/en/integrations/how-tos"
  - title: "Teams"
    href: "/en/integrations/how-tos/teams"
  - title: "Schedule reminders"
    href: "/en/integrations/how-tos/teams/schedule-reminders"
---

# Scheduling pull request reminders in Teams

Set up reminders for pending pull request reviews in Teams.

You can schedule reminders for pending pull request reviews in Microsoft Teams channels or in the GitHub personal app. Reminders are available for organizations, not personal accounts.

The combined GitHub app preserves your scheduled reminders when you update from GitHub Notifications. You don't need to recreate them to use Copilot.

Reminders and agent settings are separate. Use the `schedule` commands in this article to configure review reminders, and use `@GitHub settings` to choose repositories for Copilot. Reminders are available in channels and the personal app, not in group chats.

## Scheduling reminders in a channel

1. In a Teams channel, run `@GitHub schedule ORGANIZATION`.
2. Select **Create new reminder**.
3. Configure the days, times, timezone, and repository or team filters for the reminder.
4. Save the reminder.

To edit or remove reminders for the organization, run `@GitHub schedule ORGANIZATION` again. To list all reminders configured in the channel, run `@GitHub schedule list`.

## Scheduling reminders in the personal app

1. Open the GitHub personal app in Teams.
2. Run `schedule ORGANIZATION`.
3. Select **Create new reminder** and configure your reminder settings.
4. Save the reminder.

In the personal app, you can list reminders with `schedule list`.

> [!NOTE] To configure reminders for an organization, you must be a member of the organization and have write access to at least one repository.

## Following up on a reminder with Copilot

You can use a pull request link from a reminder as context for a new task. For example:

```text
@GitHub Summarize the changes in PULL-REQUEST-URL and identify what needs review.
```

Replace `PULL-REQUEST-URL` with the pull request link. Asking Copilot for an explanation or follow-up work doesn't change the reminder configuration. To start or steer an agent session, you need write access to every repository selected for that session. See [Integrating Copilot cloud agent with Teams](/en/copilot/how-tos/copilot-integrations/integrate-cloud-agent-with-teams).

## Further reading

* [Customizing notifications for GitHub in Teams](/en/integrations/how-tos/teams/customize-notifications)
* [Command reference for the GitHub integration in Teams](/en/integrations/reference/teams-command-reference)

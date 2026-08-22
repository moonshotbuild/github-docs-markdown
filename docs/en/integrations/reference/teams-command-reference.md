---
source_path: "/en/integrations/reference/teams-command-reference"
title: "Command reference for the GitHub integration in Teams"
intro: "Review the commands you can use with the GitHub integration in Teams."
product: "Integrations"
document_type: "article"
breadcrumbs:
  - title: "Integrations"
    href: "/en/integrations"
  - title: "Reference"
    href: "/en/integrations/reference"
  - title: "Teams command reference"
    href: "/en/integrations/reference/teams-command-reference"
---

# Command reference for the GitHub integration in Teams

Review the commands you can use with the GitHub integration in Teams.

Use these commands in a Microsoft Teams channel by prefixing them with `@GitHub`. In the GitHub personal app, omit the prefix.

| Command                                    | Description                                                     |
| ------------------------------------------ | --------------------------------------------------------------- |
| `@GitHub help`                             | Display help documentation.                                     |
| `@GitHub signin`                           | Connect your GitHub account.                                    |
| `@GitHub subscribe OWNER/REPO`             | Subscribe a channel to a repository.                            |
| `@GitHub subscribe OWNER/REPO [feature]`   | Subscribe a channel to specific notification features.          |
| `@GitHub subscribe list`                   | List subscriptions in the channel.                              |
| `@GitHub subscribe list features`          | List subscriptions and subscribed features in the channel.      |
| `@GitHub unsubscribe OWNER/REPO`           | Unsubscribe a channel from a repository.                        |
| `@GitHub unsubscribe OWNER/REPO [feature]` | Unsubscribe a channel from specific features.                   |
| `@GitHub schedule ORGANIZATION`            | List and manage reminders for the organization in this channel. |
| `@GitHub schedule list`                    | List all reminders configured in this channel.                  |
| `@GitHub signout`                          | Disconnect your GitHub account and remove subscriptions.        |

For the list of supported notification features, see [Customizing notifications for GitHub in Teams](/en/integrations/how-tos/teams/customize-notifications).

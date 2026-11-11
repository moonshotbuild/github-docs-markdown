---
source_path: "/en/rest/agent-automations/agent-automations"
title: "REST API endpoints for agent automations"
intro: "Use the REST API to manage agent automations."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Agent automations"
    href: "/en/rest/agent-automations"
  - title: "Agent automations"
    href: "/en/rest/agent-automations/agent-automations"
---

# REST API endpoints for agent automations

Use the REST API to manage agent automations.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## List automations for user

```
GET /agents/automations
```

Note

This endpoint is in public preview and is subject to change.

Lists automations created by the authenticated user across repositories they can read.
This includes both personal and shared automations created by the caller, but excludes
shared automations created by another user.
Use the repository-scoped list operation for those automations. The type filter
only narrows this creator-scoped collection.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "List automations for user"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

GitHub App installation access tokens are not supported for this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`page`** (integer)
  The page number of the results to fetch.
  Default: `1`

- **`per_page`** (integer)
  The number of results per page (max 100).
  Default: `30`

- **`type`** (string)
  Filter automations by type. personal returns automations owned by their creator, shared returns automations owned by the repository. Omit to return both.
  Can be one of: `personal`, `shared`

### HTTP response status codes

- **200** - Automations retrieved successfully

- **400** - Bad request

- **401** - Authentication required

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/automations
```

**Response schema (Status: 200):**

Array of objects:
  * `tools`: array of string
  * `id`: required, string
  * `repository`: required, object:
    * `id`: required, integer, format: int64
    * `owner`: required, string
    * `name`: required, string
  * `name`: required, string
  * `enabled`: boolean
  * `type`: string, enum: `personal`, `shared`, read-only
  * `require_actor_write_permission`: boolean, default: `false`
  * `model`: string
  * `reasoning_effort`: string
  * `triggers`: object:
    * `interval`: object:
      * `cadence`: required, array of string, enum: `hourly`, `daily`, `weekly`
      * `hour_utc`: integer, minimum: 0, maximum: 23
      * `day_of_week`: integer, minimum: 0, maximum: 6
      * `minute_utc`: integer, enum: `0`, `15`, `30`, `45`, default: `0`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_opened`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_labeled`: object:
      * `query`: string, minLength: 1
      * `labels`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `workflow_run`: object:
      * `workflows`: required, array of string, minLength: 1
      * `conclusions`: required, array of string, enum: `failure`
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_opened`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_synchronize`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_merged`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_comment`: object:
      * `query`: string, minLength: 1
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_comment`: object:
      * `comment_types`: required, array of string, enum: `timeline_comment`, `review_comment`
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_opened`: object:
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_updated`: object:
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_comment`: object:
      * `comment_types`: array of string, enum: `comment`, `reply`
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_assigned`: object:
      * `query`: string, minLength: 1
      * `assignees`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_assigned`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `assignees`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `sub_issue_added`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_ready_for_review`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_labeled`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `labels`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_merge_conflict`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_submitted`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `states`: required, array of string, enum: `approved`, `changes_requested`, `commented`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_requested`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_closed`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_reopened`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_closed`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_reopened`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_converted_to_draft`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_dismissed`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_thread_resolved`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_thread_unresolved`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `automation_completed`: object:
      * `automation_ids`: required, array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `automation_failed`: object:
      * `automation_ids`: required, array of string
      * `reasons`: array of string, enum: `reported`, `crashed`, `timed_out`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `code_scanning_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `secret_scanning_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `dependabot_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
  * `created_at`: required, string, format: date-time
  * `updated_at`: required, string, format: date-time
  * `created_by`: required, object:
    * `id`: integer, format: int64

## List automations for a repository

```
GET /agents/repos/{owner}/{repo}/automations
```

Note

This endpoint is in public preview and is subject to change.

Returns a paginated list of automations for a repository, including shared
automations and personal automations created by the caller.
total_count is the number of caller-visible automations matching the supplied
filters across all pages. Use the type field to distinguish personal and shared
automations.
GitHub App installation access tokens can list shared automations.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (read). Personal automations require a user token.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "List automations for a repository"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`page`** (integer)
  The page number of the results to fetch.
  Default: `1`

- **`per_page`** (integer)
  The number of results per page (max 100).
  Default: `30`

- **`type`** (string)
  Filter automations by type. personal returns automations owned by their creator, shared returns automations owned by the repository. Omit to return both.
  Can be one of: `personal`, `shared`

### HTTP response status codes

- **200** - Automations retrieved successfully

- **400** - Bad request

- **401** - Authentication required

- **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations
```

**Response schema (Status: 200):**

* `automations`: required, array of objects:
  * `tools`: array of string
  * `id`: required, string
  * `name`: required, string
  * `enabled`: boolean
  * `type`: string, enum: `personal`, `shared`, read-only
  * `require_actor_write_permission`: boolean, default: `false`
  * `model`: string
  * `reasoning_effort`: string
  * `triggers`: object:
    * `interval`: object:
      * `cadence`: required, array of string, enum: `hourly`, `daily`, `weekly`
      * `hour_utc`: integer, minimum: 0, maximum: 23
      * `day_of_week`: integer, minimum: 0, maximum: 6
      * `minute_utc`: integer, enum: `0`, `15`, `30`, `45`, default: `0`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_opened`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_labeled`: object:
      * `query`: string, minLength: 1
      * `labels`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `workflow_run`: object:
      * `workflows`: required, array of string, minLength: 1
      * `conclusions`: required, array of string, enum: `failure`
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_opened`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_synchronize`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_merged`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_comment`: object:
      * `query`: string, minLength: 1
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_comment`: object:
      * `comment_types`: required, array of string, enum: `timeline_comment`, `review_comment`
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_opened`: object:
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_updated`: object:
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_comment`: object:
      * `comment_types`: array of string, enum: `comment`, `reply`
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_assigned`: object:
      * `query`: string, minLength: 1
      * `assignees`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_assigned`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `assignees`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `sub_issue_added`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_ready_for_review`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_labeled`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `labels`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_merge_conflict`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_submitted`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `states`: required, array of string, enum: `approved`, `changes_requested`, `commented`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_requested`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_closed`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_reopened`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_closed`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_reopened`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_converted_to_draft`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_dismissed`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_thread_resolved`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_thread_unresolved`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `automation_completed`: object:
      * `automation_ids`: required, array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `automation_failed`: object:
      * `automation_ids`: required, array of string
      * `reasons`: array of string, enum: `reported`, `crashed`, `timed_out`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `code_scanning_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `secret_scanning_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `dependabot_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
  * `created_at`: required, string, format: date-time
  * `updated_at`: required, string, format: date-time
  * `created_by`: required, object:
    * `id`: integer, format: int64
* `total_count`: required, integer, format: int32

## Create an automation for a repository

```
POST /agents/repos/{owner}/{repo}/automations
```

Note

This endpoint is in public preview and is subject to change.

Creates a new automation in a repository. Personal automations are private to
their creator. Shared automations are visible to anyone with read access to
the repository and manageable by anyone with write access to the repository.
GitHub App installation access tokens can create shared automations by setting
type to shared. The installation must belong to the repository owner and
the token must have "Agent tasks"
repository permissions (write). Personal automations require a user token.
For installation tokens, created_by identifies the App's bot account.
To call this endpoint, you must have write access to the repository and the
"Allow automations" setting must be enabled for the repository.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "Create an automation for a repository"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (write)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

#### Body parameters

- **`name`** (string) (required)
  The name of the automation.

- **`triggers`** (object)
  Trigger configuration for the automation.
  - **`interval`** (object)
    - **`cadence`** (array of strings) (required)
      One or more schedules on which the Automation runs.
      Supported values are: hourly, daily, weekly
    - **`hour_utc`** (integer)
      UTC hour anchor (0 through 23) for daily and weekly schedules. Omitted daily and weekly values default to 0 (midnight UTC).
    - **`day_of_week`** (integer)
      UTC weekday anchor for weekly schedules, where 0 is Sunday and 6 is Saturday. Omitted weekly values default to Monday (1).
    - **`minute_utc`** (integer)
      UTC minute anchor for daily and weekly schedules. Omitted daily and weekly values default to 0. Must be omitted whenever cadence includes hourly.
      Default: `0`
      Can be one of: `0`, `15`, `30`, `45`
    - **`write_scope`** (string)
      Has no effect: scheduled runs can change any resource in the repository, and an organization or repository policy requiring trigger-scoped writes does not apply to them.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_opened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_labeled`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`labels`** (array of strings)
      Label names matched case-insensitively against the label added by the event. Omit or use an empty array to match every added label.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`workflow_run`** (object)
    - **`workflows`** (array of strings) (required)
      Workflow names matched against the name in each workflow YAML file.
    - **`conclusions`** (array of strings) (required)
      Workflow conclusions to match. The current trigger supports failure.
      Supported values are: failure
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_opened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_synchronize`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_merged`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_comment`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_comment`** (object)
    - **`comment_types`** (array of strings) (required)
      Pull request conversation and inline review comment types to match.
      Supported values are: timeline_comment, review_comment
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`discussion_opened`** (object)
    - **`categories`** (array of strings)
      Discussion category names matched case-insensitively.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`discussion_updated`** (object)
    - **`categories`** (array of strings)
      Discussion category names matched case-insensitively.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`discussion_comment`** (object)
    - **`comment_types`** (array of strings)
      Top-level discussion comments and replies to match. Omit to match both.
      Supported values are: comment, reply
    - **`categories`** (array of strings)
      Discussion category names matched case-insensitively.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_assigned`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`assignees`** (array of strings)
      Affected assignee logins matched case-insensitively.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_assigned`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`assignees`** (array of strings)
      Affected assignee logins matched case-insensitively.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`sub_issue_added`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_ready_for_review`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_labeled`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`labels`** (array of strings)
      Label names matched case-insensitively against the label added by the event. Omit or use an empty array to match every added label.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_merge_conflict`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_submitted`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`states`** (array of strings) (required)
      Submitted review states to match.
      Supported values are: approved, changes_requested, commented
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_requested`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_closed`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_reopened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_closed`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_reopened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_converted_to_draft`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_dismissed`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_thread_resolved`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_thread_unresolved`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`automation_completed`** (object)
    - **`automation_ids`** (array of strings) (required)
      Upstream Automation IDs in the same repository.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`automation_failed`** (object)
    - **`automation_ids`** (array of strings) (required)
      Upstream Automation IDs in the same repository. An Automation cannot list itself, and a user-owned Automation can only be listed by its creator's user-owned Automations.
    - **`reasons`** (array of strings)
      Failure reasons to match. Omit to match only reported failures.
      Supported values are: reported, crashed, timed_out
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`code_scanning_alert`** (object)
    Runs on the default branch when a security alert of this kind is created in the repository. These are system events without an issue, pull request, or human actor, and cannot be run manually.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`secret_scanning_alert`** (object)
    Runs on the default branch when a security alert of this kind is created in the repository. These are system events without an issue, pull request, or human actor, and cannot be run manually.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`dependabot_alert`** (object)
    Runs on the default branch when a security alert of this kind is created in the repository. These are system events without an issue, pull request, or human actor, and cannot be run manually.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.

- **`prompt`** (string) (required)
  The prompt for the automation.

- **`model`** (string)
  The model to use for sessions triggered by this automation. Omit or leave empty to let the platform select the model.

- **`reasoning_effort`** (string)
  The reasoning effort to use for sessions triggered by this automation. Omit or leave empty to use the model's default.

- **`tools`** (array of strings)
  The tools available to the automation.

- **`enabled`** (boolean)
  Whether the automation should be created enabled. Defaults to true when omitted.
  Default: `true`

- **`type`** (string)
  The type of automation, fixed at creation. personal keeps it private to its creator and its runs act as that user. shared makes it belong to the repository, visible to anyone with read access to the repository and maintainable by anyone with write access to the repository, and its runs act as the Copilot app rather than as a person. shared is rejected when repository ownership is not available for the repository. Supported values: personal, shared. Defaults to personal.
  Default: `personal`
  Can be one of: `personal`, `shared`

- **`require_actor_write_permission`** (boolean)
  When true, event-triggered runs require the event actor to have repo write permission, even when the org's allow_read_access_triggers policy is enabled. When policy validation is enabled, explicitly setting false returns 422 if effective organization or repository policy disallows read-access triggers. If omitted, defaults to false when policy permits read-access triggers, otherwise true. The actor requirement does not apply to interval-scheduled runs, which always run as the automation owner.

- **`continuous_history`** (boolean)
  When true, runs of this automation build on the session history of its previous runs, and runs of the same automation are serialized. Not tracked in revision history. Defaults to false.

### HTTP response status codes

- **201** - Automation created successfully

- **400** - Bad request

- **401** - Authentication required

- **403** - Insufficient permissions

- **404** - Resource not found

- **422** - Validation Failed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X POST \
  https://api.github.com/agents/repos/OWNER/REPO/automations \
  -d '{
  "name": "Issue triage",
  "type": "personal",
  "triggers": {
    "issue_opened": {
      "query": "is:open"
    }
  },
  "prompt": "Inspect the new issue and suggest labels, priority, and next steps.",
  "tools": [
    "github/get_file_contents",
    "github/issue_read"
  ],
  "model": "gpt-6-sol",
  "reasoning_effort": "high"
}'
```

**Response schema (Status: 201):**

* `id`: required, string
* `name`: required, string
* `enabled`: boolean
* `type`: string, enum: `personal`, `shared`, read-only
* `require_actor_write_permission`: boolean, default: `false`
* `continuous_history`: boolean, default: `false`
* `triggers`: object:
  * `interval`: object:
    * `cadence`: required, array of string, enum: `hourly`, `daily`, `weekly`
    * `hour_utc`: integer, minimum: 0, maximum: 23
    * `day_of_week`: integer, minimum: 0, maximum: 6
    * `minute_utc`: integer, enum: `0`, `15`, `30`, `45`, default: `0`
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `issue_opened`: object:
    * `query`: string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `issue_labeled`: object:
    * `query`: string, minLength: 1
    * `labels`: array of string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `workflow_run`: object:
    * `workflows`: required, array of string, minLength: 1
    * `conclusions`: required, array of string, enum: `failure`
    * `query`: string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_opened`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_synchronize`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_merged`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `issue_comment`: object:
    * `query`: string, minLength: 1
    * `body_substring`: string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_comment`: object:
    * `comment_types`: required, array of string, enum: `timeline_comment`, `review_comment`
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `body_substring`: string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `discussion_opened`: object:
    * `categories`: array of string
    * `body_substring`: string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `discussion_updated`: object:
    * `categories`: array of string
    * `body_substring`: string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `discussion_comment`: object:
    * `comment_types`: array of string, enum: `comment`, `reply`
    * `categories`: array of string
    * `body_substring`: string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `issue_assigned`: object:
    * `query`: string, minLength: 1
    * `assignees`: array of string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_assigned`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `assignees`: array of string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `sub_issue_added`: object:
    * `query`: string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_ready_for_review`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_labeled`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `labels`: array of string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_merge_conflict`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_review_submitted`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `states`: required, array of string, enum: `approved`, `changes_requested`, `commented`
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_review_requested`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `issue_closed`: object:
    * `query`: string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `issue_reopened`: object:
    * `query`: string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_closed`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_reopened`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_converted_to_draft`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_review_dismissed`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_review_thread_resolved`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `pull_request_review_thread_unresolved`: object:
    * `query`: string, minLength: 1
    * `paths`: array of string, minLength: 1
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `automation_completed`: object:
    * `automation_ids`: required, array of string
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `automation_failed`: object:
    * `automation_ids`: required, array of string
    * `reasons`: array of string, enum: `reported`, `crashed`, `timed_out`
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `code_scanning_alert`: object:
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `secret_scanning_alert`: object:
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
  * `dependabot_alert`: object:
    * `write_scope`: string, enum: `trigger`, `repository`
    * `allow_copilot_triggers`: boolean
* `prompt`: required, string
* `tools`: array of string
* `model`: string
* `reasoning_effort`: string
* `created_at`: required, string, format: date-time
* `updated_at`: required, string, format: date-time
* `created_by`: required, object:
  * `id`: integer, format: int64

## List available automation tools for a repository

```
GET /agents/repos/{owner}/{repo}/automations/available-tools
```

Note

This endpoint is in public preview and is subject to change.

Lists available tools for automations in a repository, including both
GitHub-provided tools and tools provided by custom MCP servers.
GitHub-provided tools are returned in named groups, with a name and
description provided for each tool.
MCP entries describe configured tool selection, not live discovery or runtime
availability. An explicit allowlist is returned in tools, with each id in
<server-name>/<tool-name> format, for example sentry/list_issues. An allowlist of
["*"] is returned as supports_wildcard: true with an empty tools array. Server URLs,
authentication headers, environment variables, and credentials are never returned.
For MCP tools, a list of configured MCP servers is provided, along with
the tools allowlisted for each server. Where supports_wildcard is true,
any tool that exists on the server can be used.
GitHub App installation access tokens can list available automation tools.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (read).
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "List available automation tools for a repository"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

### HTTP response status codes

- **200** - Repository automation tool catalog retrieved successfully

- **401** - Authentication required

- **404** - Repository not found, inaccessible, or automations unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations/available-tools
```

**Response schema (Status: 200):**

* `tool_groups`: required, array of objects:
  * `id`: required, string
  * `title`: required, string
  * `tools`: required, array of objects:
    * `id`: required, string
    * `title`: required, string
    * `description`: required, string
    * `scope`: string, enum: `read`, `write`
* `mcp_servers`: required, array of objects:
  * `name`: required, string
  * `tools`: required, array of objects:
    * `id`: required, string
  * `supports_wildcard`: required, boolean

## List available automation triggers for a repository

```
GET /agents/repos/{owner}/{repo}/automations/available-triggers
```

Note

This endpoint is in public preview and is subject to change.

Lists available triggers for automations in a repository.
Each available trigger includes a title and description that can be presented
in user interfaces, plus a machine-readable schema of filters supported by the
trigger.
GitHub App installation access tokens can list available automation triggers.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (read).
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "List available automation triggers for a repository"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

### HTTP response status codes

- **200** - Available automation triggers retrieved successfully

- **401** - Authentication required

- **404** - Repository not found, inaccessible, or automations unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations/available-triggers
```

**Response schema (Status: 200):**

Array of objects:
  * `id`: required, string
  * `title`: required, string
  * `description`: required, string
  * `fields`: required, array of objects:
    * `id`: required, string
    * `label`: required, string
    * `required`: required, boolean
    * `description`: string
    * `schema`: required, one of:
      * **object**
        * `type`: required, string, enum: `string`
        * `enum`: array of string
        * `minLength`: integer, minimum: 0
      * **object**
        * `type`: required, string, enum: `array`
        * `items`: required, object:
          * `type`: required, string, enum: `string`
          * `enum`: array of string
          * `minLength`: integer, minimum: 0
        * `minItems`: integer, minimum: 0
        * `maxItems`: integer, minimum: 0
        * `uniqueItems`: boolean
      * **object**
        * `type`: required, string, enum: `integer`
        * `enum`: array of integer
        * `minimum`: integer
        * `maximum`: integer

## Get an automation

```
GET /agents/repos/{owner}/{repo}/automations/{automation_id}
```

Note

This endpoint is in public preview and is subject to change.

Fetches a repository automation by ID. The automation must be a personal
automation belonging to you or a shared automation.
Shared automations are visible to anyone with read access to the repository.
The created_by field identifies the creator and is distinct from the automation's
type.
GitHub App installation access tokens can access shared automations.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (read). Personal automations require a user token.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "Get an automation"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

### HTTP response status codes

- **200** - Automation retrieved successfully

- **400** - Bad request

- **401** - Authentication required

- **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID
```

**Response schema (Status: 200):**

Same response schema as [Create an automation for a repository](#create-an-automation-for-a-repository).

## Update an automation

```
PATCH /agents/repos/{owner}/{repo}/automations/{automation_id}
```

Note

This endpoint is in public preview and is subject to change.

Updates an existing automation in a repository. The automation
must be a personal automation belonging to you or a shared automation.
Omitted fields are left unchanged. The automation's type is immutable.
GitHub App installation access tokens can update shared automations.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (write). Personal automations require a user token.
To call this endpoint, you must have write access to the repository and the
"Allow automations" setting must be enabled for the repository.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "Update an automation"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (write)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

#### Body parameters

- **`name`** (string)
  The name of the automation.

- **`enabled`** (boolean)
  Set to true to enable, false to disable. Omit to leave unchanged.

- **`require_actor_write_permission`** (boolean)
  When true, event-triggered runs require the event actor to have repo write permission, even when the org's allow_read_access_triggers policy is enabled. When policy validation is enabled, explicitly setting false returns 422 if effective organization or repository policy disallows read-access triggers. The actor requirement does not apply to interval-scheduled runs, which always run as the automation owner. Omit to leave unchanged.

- **`continuous_history`** (boolean)
  When true, runs of this automation build on the session history of its previous runs, and runs of the same automation are serialized. Not tracked in revision history. Omit to leave unchanged.

- **`model`** (string)
  The model to use for sessions triggered by this automation. Omit to leave unchanged. Send an empty string to clear the override and let the platform select the model.

- **`reasoning_effort`** (string)
  The reasoning effort to use for sessions triggered by this automation. Omit to leave unchanged. Send an empty string to clear the override and use the model's default.

- **`triggers`** (object)
  Trigger configuration for the automation.
  - **`interval`** (object)
    - **`cadence`** (array of strings) (required)
      One or more schedules on which the Automation runs.
      Supported values are: hourly, daily, weekly
    - **`hour_utc`** (integer)
      UTC hour anchor (0 through 23) for daily and weekly schedules. Omitted daily and weekly values default to 0 (midnight UTC).
    - **`day_of_week`** (integer)
      UTC weekday anchor for weekly schedules, where 0 is Sunday and 6 is Saturday. Omitted weekly values default to Monday (1).
    - **`minute_utc`** (integer)
      UTC minute anchor for daily and weekly schedules. Omitted daily and weekly values default to 0. Must be omitted whenever cadence includes hourly.
      Default: `0`
      Can be one of: `0`, `15`, `30`, `45`
    - **`write_scope`** (string)
      Has no effect: scheduled runs can change any resource in the repository, and an organization or repository policy requiring trigger-scoped writes does not apply to them.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_opened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_labeled`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`labels`** (array of strings)
      Label names matched case-insensitively against the label added by the event. Omit or use an empty array to match every added label.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`workflow_run`** (object)
    - **`workflows`** (array of strings) (required)
      Workflow names matched against the name in each workflow YAML file.
    - **`conclusions`** (array of strings) (required)
      Workflow conclusions to match. The current trigger supports failure.
      Supported values are: failure
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_opened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_synchronize`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_merged`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_comment`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_comment`** (object)
    - **`comment_types`** (array of strings) (required)
      Pull request conversation and inline review comment types to match.
      Supported values are: timeline_comment, review_comment
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`discussion_opened`** (object)
    - **`categories`** (array of strings)
      Discussion category names matched case-insensitively.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`discussion_updated`** (object)
    - **`categories`** (array of strings)
      Discussion category names matched case-insensitively.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`discussion_comment`** (object)
    - **`comment_types`** (array of strings)
      Top-level discussion comments and replies to match. Omit to match both.
      Supported values are: comment, reply
    - **`categories`** (array of strings)
      Discussion category names matched case-insensitively.
    - **`body_substring`** (string)
      A case-insensitive substring matched against the event body.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_assigned`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`assignees`** (array of strings)
      Affected assignee logins matched case-insensitively.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_assigned`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`assignees`** (array of strings)
      Affected assignee logins matched case-insensitively.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`sub_issue_added`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_ready_for_review`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_labeled`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`labels`** (array of strings)
      Label names matched case-insensitively against the label added by the event. Omit or use an empty array to match every added label.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_merge_conflict`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_submitted`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`states`** (array of strings) (required)
      Submitted review states to match.
      Supported values are: approved, changes_requested, commented
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_requested`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_closed`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`issue_reopened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_closed`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_reopened`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_converted_to_draft`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_dismissed`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_thread_resolved`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`pull_request_review_thread_unresolved`** (object)
    - **`query`** (string)
      A GitHub issue or pull request search query.
    - **`paths`** (array of strings)
      Gitignore-style changed-file path globs.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`automation_completed`** (object)
    - **`automation_ids`** (array of strings) (required)
      Upstream Automation IDs in the same repository.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`automation_failed`** (object)
    - **`automation_ids`** (array of strings) (required)
      Upstream Automation IDs in the same repository. An Automation cannot list itself, and a user-owned Automation can only be listed by its creator's user-owned Automations.
    - **`reasons`** (array of strings)
      Failure reasons to match. Omit to match only reported failures.
      Supported values are: reported, crashed, timed_out
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`code_scanning_alert`** (object)
    Runs on the default branch when a security alert of this kind is created in the repository. These are system events without an issue, pull request, or human actor, and cannot be run manually.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`secret_scanning_alert`** (object)
    Runs on the default branch when a security alert of this kind is created in the repository. These are system events without an issue, pull request, or human actor, and cannot be run manually.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.
  - **`dependabot_alert`** (object)
    Runs on the default branch when a security alert of this kind is created in the repository. These are system events without an issue, pull request, or human actor, and cannot be run manually.
    - **`write_scope`** (string)
      Sets the write scope for this trigger's runs. Omit to inherit the automation's effective scope (default trigger). Organization or repository policy may restrict the effective scope to trigger. Explicitly setting repository on create or edit returns 422 when policy validation is enabled and that policy applies.
      Can be one of: `trigger`, `repository`
    - **`allow_copilot_triggers`** (boolean)
      When true, events Copilot creates, including from other automations and Copilot sessions, can start this automation through this trigger. Defaults to false. The Copilot coding agent app cannot turn it on: creating a trigger with true, or changing it from false to true, returns 422.

- **`prompt`** (string)
  The prompt for the automation.

- **`tools`** (array of strings)
  The tools available to the automation. Send an empty array to clear all tools.

### HTTP response status codes

- **200** - Automation updated successfully

- **400** - Bad request

- **401** - Authentication required

- **404** - Resource not found

- **422** - Validation Failed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID \
  -d '{
  "name": "Issue triage and prioritization",
  "enabled": true,
  "model": "gpt-5.4",
  "reasoning_effort": "high",
  "triggers": {
    "issue_opened": {
      "query": "is:open label:auto-triage"
    }
  }
}'
```

**Response schema (Status: 200):**

Same response schema as [Create an automation for a repository](#create-an-automation-for-a-repository).

## Delete an automation

```
DELETE /agents/repos/{owner}/{repo}/automations/{automation_id}
```

Note

This endpoint is in public preview and is subject to change.

Deletes an automation in a repository. The automation must be a personal
automation belonging to you or a shared automation.
Data dedicated to the automation is also deleted when present and may remain
recoverable for a limited period according to the configured retention policy.
GitHub App installation access tokens can delete shared automations.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (write). Personal automations require a user token.
To call this endpoint, you must have write access to the repository and the
"Allow automations" setting must be enabled for the repository.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "Delete an automation"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (write)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

### HTTP response status codes

- **204** - Automation deleted successfully

- **400** - Bad request

- **401** - Authentication required

- **404** - Resource not found

- **503** - Automation deletion is temporarily unavailable and can be retried.

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID
```

**Response schema (Status: 204):**

## List revisions for an automation

```
GET /agents/repos/{owner}/{repo}/automations/{automation_id}/revisions
```

Note

This endpoint is in public preview and is subject to change.

Returns a list of revisions for an automation, ordered from newest to oldest.
Access follows the automation's own ownership rules: a user-owned automation's
history is readable only by its creator, and a repository-owned automation's
history follows repository read access. History remains readable after the
automation is deleted.
Follow the opaque cursor in the rel="next" link from the Link header to
continue when more revisions are available.
Fine-grained access tokens for "List revisions for an automation"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

GitHub App installation access tokens are not supported for this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

- **`cursor`** (string)
  Opaque cursor identifying where to continue reading revision history,
  taken from the next link of a previous response. Omit to start from
  the most recent revision.

- **`per_page`** (integer)
  The number of results per page (max 100).
  Default: `30`

### HTTP response status codes

- **200** - Revision history retrieved successfully

- **400** - Bad request

- **401** - Authentication required

- **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID/revisions
```

**Response schema (Status: 200):**

* `revisions`: required, array of objects:
  * `id`: required, string
  * `automation_id`: required, string
  * `revision_number`: required, integer, format: int64
  * `change_type`: required, string, enum: `created`, `edited`, `enabled`, `disabled`, `deleted`, `rolled_back`, `unknown`
  * `creator`: all of:
    * **object**
      * `id`: integer, format: int64
  * `editor`: all of:
    * **object**
      * `id`: integer, format: int64
  * `editor_type`: string, enum: `user`, `system`, `unknown`
  * `changed_at`: required, string, format: date-time
  * `restored_from_revision_id`: string
  * `snapshot`: object:
    * `id`: required, string
    * `name`: required, string
    * `enabled`: boolean
    * `type`: string, enum: `personal`, `shared`, read-only
    * `require_actor_write_permission`: boolean, default: `false`
    * `triggers`: object:
      * `interval`: object:
        * `cadence`: required, array of string, enum: `hourly`, `daily`, `weekly`
        * `hour_utc`: integer, minimum: 0, maximum: 23
        * `day_of_week`: integer, minimum: 0, maximum: 6
        * `minute_utc`: integer, enum: `0`, `15`, `30`, `45`, default: `0`
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `issue_opened`: object:
        * `query`: string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `issue_labeled`: object:
        * `query`: string, minLength: 1
        * `labels`: array of string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `workflow_run`: object:
        * `workflows`: required, array of string, minLength: 1
        * `conclusions`: required, array of string, enum: `failure`
        * `query`: string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_opened`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_synchronize`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_merged`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `issue_comment`: object:
        * `query`: string, minLength: 1
        * `body_substring`: string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_comment`: object:
        * `comment_types`: required, array of string, enum: `timeline_comment`, `review_comment`
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `body_substring`: string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `discussion_opened`: object:
        * `categories`: array of string
        * `body_substring`: string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `discussion_updated`: object:
        * `categories`: array of string
        * `body_substring`: string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `discussion_comment`: object:
        * `comment_types`: array of string, enum: `comment`, `reply`
        * `categories`: array of string
        * `body_substring`: string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `issue_assigned`: object:
        * `query`: string, minLength: 1
        * `assignees`: array of string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_assigned`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `assignees`: array of string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `sub_issue_added`: object:
        * `query`: string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_ready_for_review`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_labeled`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `labels`: array of string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_merge_conflict`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_review_submitted`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `states`: required, array of string, enum: `approved`, `changes_requested`, `commented`
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_review_requested`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `issue_closed`: object:
        * `query`: string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `issue_reopened`: object:
        * `query`: string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_closed`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_reopened`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_converted_to_draft`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_review_dismissed`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_review_thread_resolved`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `pull_request_review_thread_unresolved`: object:
        * `query`: string, minLength: 1
        * `paths`: array of string, minLength: 1
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `automation_completed`: object:
        * `automation_ids`: required, array of string
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `automation_failed`: object:
        * `automation_ids`: required, array of string
        * `reasons`: array of string, enum: `reported`, `crashed`, `timed_out`
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `code_scanning_alert`: object:
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `secret_scanning_alert`: object:
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
      * `dependabot_alert`: object:
        * `write_scope`: string, enum: `trigger`, `repository`
        * `allow_copilot_triggers`: boolean
    * `prompt`: required, string
    * `tools`: array of string
    * `model`: string
    * `reasoning_effort`: string
    * `created_at`: required, string, format: date-time
    * `updated_at`: required, string, format: date-time
    * `created_by`: required, object:
      * `id`: integer, format: int64

## Get an automation revision

```
GET /agents/repos/{owner}/{repo}/automations/{automation_id}/revisions/{revision_id}
```

Note

This endpoint is in public preview and is subject to change.

Returns a specific revision of an automation, including its configuration after that change.
Access follows the automation's own ownership rules: a user-owned automation's
history is readable only by its creator, and a repository-owned automation's
history follows repository read access. History remains readable after the
automation is deleted.
A revision ID belonging to a different automation returns 404.
Fine-grained access tokens for "Get an automation revision"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

GitHub App installation access tokens are not supported for this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

- **`revision_id`** (string) (required)
  The unique identifier of the automation revision.

### HTTP response status codes

- **200** - Revision retrieved successfully

- **401** - Authentication required

- **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID/revisions/REVISION_ID
```

**Response schema (Status: 200):**

* `id`: required, string
* `automation_id`: required, string
* `revision_number`: required, integer, format: int64
* `change_type`: required, string, enum: `created`, `edited`, `enabled`, `disabled`, `deleted`, `rolled_back`, `unknown`
* `creator`: all of:
  * **object**
    * `id`: integer, format: int64
* `editor`: all of:
  * **object**
    * `id`: integer, format: int64
* `editor_type`: string, enum: `user`, `system`, `unknown`
* `changed_at`: required, string, format: date-time
* `restored_from_revision_id`: string
* `snapshot`: object:
  * `id`: required, string
  * `name`: required, string
  * `enabled`: boolean
  * `type`: string, enum: `personal`, `shared`, read-only
  * `require_actor_write_permission`: boolean, default: `false`
  * `triggers`: object:
    * `interval`: object:
      * `cadence`: required, array of string, enum: `hourly`, `daily`, `weekly`
      * `hour_utc`: integer, minimum: 0, maximum: 23
      * `day_of_week`: integer, minimum: 0, maximum: 6
      * `minute_utc`: integer, enum: `0`, `15`, `30`, `45`, default: `0`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_opened`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_labeled`: object:
      * `query`: string, minLength: 1
      * `labels`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `workflow_run`: object:
      * `workflows`: required, array of string, minLength: 1
      * `conclusions`: required, array of string, enum: `failure`
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_opened`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_synchronize`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_merged`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_comment`: object:
      * `query`: string, minLength: 1
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_comment`: object:
      * `comment_types`: required, array of string, enum: `timeline_comment`, `review_comment`
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_opened`: object:
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_updated`: object:
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `discussion_comment`: object:
      * `comment_types`: array of string, enum: `comment`, `reply`
      * `categories`: array of string
      * `body_substring`: string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_assigned`: object:
      * `query`: string, minLength: 1
      * `assignees`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_assigned`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `assignees`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `sub_issue_added`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_ready_for_review`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_labeled`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `labels`: array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_merge_conflict`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_submitted`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `states`: required, array of string, enum: `approved`, `changes_requested`, `commented`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_requested`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_closed`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `issue_reopened`: object:
      * `query`: string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_closed`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_reopened`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_converted_to_draft`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_dismissed`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_thread_resolved`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `pull_request_review_thread_unresolved`: object:
      * `query`: string, minLength: 1
      * `paths`: array of string, minLength: 1
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `automation_completed`: object:
      * `automation_ids`: required, array of string
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `automation_failed`: object:
      * `automation_ids`: required, array of string
      * `reasons`: array of string, enum: `reported`, `crashed`, `timed_out`
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `code_scanning_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `secret_scanning_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
    * `dependabot_alert`: object:
      * `write_scope`: string, enum: `trigger`, `repository`
      * `allow_copilot_triggers`: boolean
  * `prompt`: required, string
  * `tools`: array of string
  * `model`: string
  * `reasoning_effort`: string
  * `created_at`: required, string, format: date-time
  * `updated_at`: required, string, format: date-time
  * `created_by`: required, object:
    * `id`: integer, format: int64

## List tasks for an automation in a repository

```
GET /agents/repos/{owner}/{repo}/automations/{automation_id}/tasks
```

Note

This endpoint is in public preview and is subject to change.

Returns a paginated list of tasks created by an automation in the specified
repository. The automation must belong to that exact repository.
User-owned automation history is visible only to the automation's creator.
Repository-owned automation history is visible to callers with read access to
repository automations. Deleted and unlisted tasks are excluded. Tasks produced
by private-session agents are excluded unless the caller created the task, is a
task collaborator, or the task is shared.
A missing repository, an inaccessible repository, or an automation that does not
belong to the specified repository returns 404 without revealing which condition
occurred.
GitHub App installation access tokens can list tasks for shared automations.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (read). Personal automations require a user token.
Fine-grained access tokens for "List tasks for an automation in a repository"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

- **`per_page`** (integer)
  The number of results per page (max 100).
  Default: `30`

- **`page`** (integer)
  The page number of the results to fetch.
  Default: `1`

- **`sort`** (string)
  The field to sort results by. Can be updated_at or created_at.
  Default: `updated_at`
  Can be one of: `updated_at`, `created_at`

- **`direction`** (string)
  The direction to sort results. Can be asc or desc.
  Default: `desc`
  Can be one of: `asc`, `desc`

- **`state`** (string)
  Comma-separated list of task states to filter by. Can be any combination of: queued, in_progress, completed, failed, idle, waiting_for_user, timed_out, cancelled.

- **`is_archived`** (boolean)
  Filter by archived status. When true, returns only archived tasks. When false or omitted, returns only non-archived tasks. Defaults to false.
  Default: `false`

### HTTP response status codes

- **200** - Automation task history retrieved successfully

- **401** - Authentication required

- **404** - Repository or automation not found, inaccessible, or unavailable

- **422** - Validation failed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID/tasks
```

**Response schema (Status: 200):**

* `tasks`: required, array of objects:
  * `id`: required, string
  * `url`: string
  * `html_url`: string
  * `name`: string
  * `clients`: array of objects:
    * `integration_id`: required, string
    * `slug`: required, string
    * `creator`: required, boolean
  * `creator`: one of:
    * **object**
      * `id`: integer, format: int64
  * `creator_type`: string, enum: `user`, `organization`
  * `user_collaborators`: array of objects:
    * `id`: integer, format: int64
  * `owner`: object:
    * `id`: integer, format: int64
  * `repository`: object:
    * `id`: integer, format: int64
  * `state`: required, string, enum: `queued`, `in_progress`, `completed`, `failed`, `idle`, `waiting_for_user`, `timed_out`, `cancelled`
  * `session_count`: integer, format: int32
  * `artifacts`: array of objects:
    * `provider`: required, string, enum: `github`
    * `type`: required, string, enum: `pull`, `branch`
    * `data`: required, one of:
      * **object**
        * `id`: required, integer, format: int64
        * `global_id`: string
      * **object**
        * `head_ref`: required, string
        * `base_ref`: required, string
  * `archived_at`: string or null, format: date-time
  * `updated_at`: string, format: date-time
  * `created_at`: required, string, format: date-time
  * `custom_agent`: object:
    * `id`: string

## Run an automation

```
POST /agents/repos/{owner}/{repo}/automations/{automation_id}/tasks
```

Note

This endpoint is in public preview and is subject to change.

Runs an automation in a repository. Set event to manual and optionally include
context of up to 10,000 characters, which will be injected into the automation's
prompt.
The repository must have the "Allow automations" setting enabled, and the automation
must be a personal automation belonging to you or a shared automation.
GitHub App installation access tokens can run shared automations.
The installation must belong to the repository owner and the token must have
"Agent tasks" repository permissions (write). Personal automations require a user token.
A successful response accepts the run request and includes a preallocated
task_id. User tokens can fetch it with the "Get a task by repo" Agent tasks
API. GitHub App installation tokens can list tasks for the automation in the
repository and match the returned task_id. The response does not confirm
execution or task creation. Task creation is asynchronous, so fetching the
task immediately may return 404 Not Found, and downstream skips or failures
can prevent its creation.
To call this endpoint, you must have write access to the repository.
To call this endpoint, OAuth app tokens and personal access tokens (classic)
need the repo scope.
Fine-grained access tokens for "Run an automation"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
GitHub App installation access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (write)

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository. The name is not case sensitive.

- **`automation_id`** (string) (required)
  The unique identifier of the automation.

#### Body parameters

- **`event`** (string) (required)
  The event to trigger. Only manual is supported.
  Can be one of: `manual`

- **`context`** (string)
  Additional context for this automation run, up to 10,000 characters. Supported only when event is manual. The context supplements the automation's configured instructions.

### HTTP response status codes

- **202** - Automation run request accepted for asynchronous processing

- **400** - Bad request

- **401** - Authentication required

- **403** - Insufficient permissions

- **404** - Resource not found

- **409** - Automation usage limit reached for the current period

- **422** - Validation failed

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X POST \
  https://api.github.com/agents/repos/OWNER/REPO/automations/AUTOMATION_ID/tasks \
  -d '{
  "event": "manual",
  "context": "New Sentry issue detected: https://contoso.sentry.io/issues/7796648726"
}'
```

**Response schema (Status: 202):**

* `task_id`: required, string
* `automation_id`: required, string
* `event`: required, string, enum: `manual`

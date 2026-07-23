---
source_path: "/en/rest/agent-tasks/agent-tasks"
title: "REST API endpoints for agent tasks"
intro: "Use the REST API to start and manage Copilot cloud agent tasks"
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Agent tasks"
    href: "/en/rest/agent-tasks"
  - title: "Agent tasks"
    href: "/en/rest/agent-tasks/agent-tasks"
---

# REST API endpoints for agent tasks

Use the REST API to start and manage Copilot cloud agent tasks

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## List tasks for repository

```
GET /agents/repos/{owner}/{repo}/tasks
```

Note

This endpoint is in public preview and is subject to change.

Returns a list of tasks for a specific repository
Fine-grained access tokens for "List tasks for repository"
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

- **`since`** (string)
  Only show tasks updated at or after this time (ISO 8601 timestamp)

- **`creator_id`** (array)
  Filter tasks by creator user ID. Accepts one or more user IDs.

### HTTP response status codes

- **200** - Tasks retrieved successfully

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
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/tasks
```

**Response schema (Status: 200):**

* `tasks`: required, array of objects:
  * `id`: required, string
  * `url`: string
  * `html_url`: string
  * `name`: string
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
* `total_active_count`: integer, format: int32
* `total_archived_count`: integer, format: int32

## Start a task

```
POST /agents/repos/{owner}/{repo}/tasks
```

Note

This endpoint is in public preview and is subject to change.

Starts a new Copilot cloud agent task for a repository.
This endpoint is only available to users with a Copilot Business or Copilot Enterprise subscription.
Fine-grained access tokens for "Start a task"
This endpoint works with the following fine-grained token types:

GitHub App user access tokens
Fine-grained personal access tokens

The fine-grained token must have the following permission set:

"Agent tasks" repository permissions (read and write)

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

#### Body parameters

- **`prompt`** (string) (required)
  The user's prompt for the agent

- **`model`** (string)
  The model to use for this task. The allowed models may change over time and depend on the user's GitHub Copilot plan and organization policies. Currently supported values: claude-sonnet-4.6, claude-opus-4.6, gpt-5.2-codex, gpt-5.3-codex, gpt-5.4, claude-sonnet-4.5, claude-opus-4.5

- **`custom_agent`** (string)
  Optional identifier for a custom agent to use for this task. Use the custom agent's filename without the extension - for example, for a .github/agents/performance-optimizer.agent.md custom agent, use performance-optimizer.

- **`create_pull_request`** (boolean)
  Whether to create a PR.
  Default: `false`

- **`base_ref`** (string)
  Base ref for new branch/PR

- **`head_ref`** (string)
  Head ref for existing branch/PR. If provided with base_ref, the agent looks up open PR context for head_ref targeting base_ref and commits to head_ref instead of creating a new branch.

### HTTP response status codes

- **201** - Task created successfully

- **400** - Problems parsing JSON

- **401** - Authentication required

- **403** - Insufficient permissions

- **422** - Validation Failed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X POST \
  https://api.github.com/agents/repos/OWNER/REPO/tasks \
  -d '{
  "prompt": "Fix the login button on the homepage",
  "base_ref": "main"
}'
```

**Response schema (Status: 201):**

* `id`: required, string
* `url`: string
* `html_url`: string
* `name`: string
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

#### Task with a custom agent

**Request:**

```curl
curl -L \
  -X POST \
  https://api.github.com/agents/repos/OWNER/REPO/tasks \
  -d '{
  "prompt": "Fix the login button on the homepage",
  "base_ref": "main",
  "custom_agent": "my-custom-agent"
}'
```

**Response schema (Status: 201):**

* `id`: required, string
* `url`: string
* `html_url`: string
* `name`: string
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

## Get a task by repo

```
GET /agents/repos/{owner}/{repo}/tasks/{task_id}
```

Note

This endpoint is in public preview and is subject to change.

Returns a task by ID scoped to an owner/repo path
Fine-grained access tokens for "Get a task by repo"
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

- **`task_id`** (string) (required)
  The unique identifier of the task.

### HTTP response status codes

- **200** - Task retrieved successfully

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
  -X GET \
  https://api.github.com/agents/repos/OWNER/REPO/tasks/TASK_ID
```

**Response schema (Status: 200):**

* all of:
  * **object**
    * `id`: required, string
    * `url`: string
    * `html_url`: string
    * `name`: string
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
  * **object**
    * `sessions`: array of objects:
      * `id`: required, string
      * `name`: string
      * `user`: object:
        * `id`: integer, format: int64
      * `owner`: object:
        * `id`: integer, format: int64
      * `repository`: object:
        * `id`: integer, format: int64
      * `task_id`: string
      * `state`: required, string, enum: `queued`, `in_progress`, `completed`, `failed`, `idle`, `waiting_for_user`, `timed_out`, `cancelled`
      * `created_at`: required, string, format: date-time
      * `updated_at`: string, format: date-time
      * `completed_at`: string, format: date-time
      * `prompt`: string
      * `head_ref`: string
      * `base_ref`: string
      * `model`: string
      * `usage`: object:
        * `type`: required, string, enum: `ai_credits`, `premium_requests`
        * `amount`: required, number, format: double
      * `error`: object:
        * `message`: string

## List tasks

```
GET /agents/tasks
```

Note

This endpoint is in public preview and is subject to change.

Returns a list of tasks for the authenticated user
Fine-grained access tokens for "List tasks"
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

- **`since`** (string)
  Only show tasks updated at or after this time (ISO 8601 timestamp)

### HTTP response status codes

- **200** - Tasks retrieved successfully

- **400** - Bad request

- **401** - Authentication required

- **403** - Insufficient permissions

- **422** - Validation Failed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/tasks
```

**Response schema (Status: 200):**

Same response schema as [List tasks for repository](#list-tasks-for-repository).

## Get a task by ID

```
GET /agents/tasks/{task_id}
```

Note

This endpoint is in public preview and is subject to change.

Returns a task by ID with its associated sessions
Fine-grained access tokens for "Get a task by ID"
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

- **`task_id`** (string) (required)
  The unique identifier of the task.

### HTTP response status codes

- **200** - Task retrieved successfully

- **400** - Problems parsing request

- **401** - Authentication required

- **403** - Insufficient permissions

- **404** - Resource not found

- **422** - Validation Failed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/agents/tasks/TASK_ID
```

**Response schema (Status: 200):**

Same response schema as [Get a task by repo](#get-a-task-by-repo).

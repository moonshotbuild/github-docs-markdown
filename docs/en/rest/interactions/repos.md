---
source_path: "/en/rest/interactions/repos"
title: "REST API endpoints for repository interactions"
intro: "Use the REST API to temporarily restrict which type of user can comment, open issues, or create pull requests in a public repository."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Interactions"
    href: "/en/rest/interactions"
  - title: "Repository"
    href: "/en/rest/interactions/repos"
---

# REST API endpoints for repository interactions

Use the REST API to temporarily restrict which type of user can comment, open issues, or create pull requests in a public repository.

## About repository interactions

People with owner or admin access can use the REST API to temporarily restrict which type of user can comment, open issues, or create pull requests in a public repository. When restrictions are enabled, only the specified type of GitHub user will be able to participate in interactions. Restrictions automatically expire after a defined duration. Here's more about the types of GitHub users:

* **Existing users:** When you limit interactions to `existing_users`, new users with accounts less than 24 hours old who have not previously contributed and are not collaborators will be temporarily restricted in the repository.
* **Contributors only:** When you limit interactions to `contributors_only`, users who have not previously contributed and are not collaborators will be temporarily restricted in the repository.
* **Collaborators only:** When you limit interactions to `collaborators_only`, users who are not collaborators will be temporarily restricted in the repository.

If an interaction limit is enabled for the user or organization that owns the repository, the limit cannot be changed for the individual repository. Instead, use the [User](/en/rest/interactions/user) or [Organization](/en/rest/interactions/orgs) interactions endpoints to change the interaction limit.

> \[!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## Get interaction restrictions for a repository

```
GET /repos/{owner}/{repo}/interaction-limits
```

Shows which type of GitHub user can interact with this repository and when the restriction expires. If there are no restrictions, you will see an empty response.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

### HTTP response status codes

* **200** - OK

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/interaction-limits
```

**Response schema (Status: 200):**

* any of:
  * **Interaction Limits**
    * `limit`: required, string, enum: `existing_users`, `contributors_only`, `collaborators_only`
    * `origin`: required, string
    * `expires_at`: required, string, format: date-time
  * **object**

## Set interaction restrictions for a repository

```
PUT /repos/{owner}/{repo}/interaction-limits
```

Temporarily restricts interactions to a certain type of GitHub user within the given repository. You must have owner or admin access to set these restrictions. If an interaction limit is set for the user or organization that owns this repository, you will receive a 409 Conflict response and will not be able to use this endpoint to change the interaction limit for a single repository.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

#### Body parameters

* **`limit`** (string) (required)
  The type of GitHub user that can comment, open issues, or create pull requests while the interaction limit is in effect.
  Can be one of: `existing_users`, `contributors_only`, `collaborators_only`

* **`expiry`** (string)
  The duration of the interaction restriction. Default: one\_day.
  Can be one of: `one_day`, `three_days`, `one_week`, `one_month`, `six_months`

### HTTP response status codes

* **200** - OK

* **409** - Conflict

### Code examples

#### Example request body

**Request:**

```curl
curl -L \
  -X PUT \
  https://api.github.com/repos/OWNER/REPO/interaction-limits \
  -d '{
  "limit": "collaborators_only",
  "expiry": "one_day"
}'
```

**Response schema (Status: 200):**

* `limit`: required, string, enum: `existing_users`, `contributors_only`, `collaborators_only`
* `origin`: required, string
* `expires_at`: required, string, format: date-time

## Remove interaction restrictions for a repository

```
DELETE /repos/{owner}/{repo}/interaction-limits
```

Removes all interaction restrictions from the given repository. You must have owner or admin access to remove restrictions. If the interaction limit is set for the user or organization that owns this repository, you will receive a 409 Conflict response and will not be able to use this endpoint to change the interaction limit for a single repository.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

### HTTP response status codes

* **204** - No Content

* **409** - Conflict

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/repos/OWNER/REPO/interaction-limits
```

**Response schema (Status: 204):**

## Get pull request creation cap bypass list for a repository

```
GET /repos/{owner}/{repo}/interaction-limits/pulls/bypass-list
```

Lists the users that are on the pull request creation cap bypass list for a
repository. Users on this list can create pull requests regardless of any
configured pull request creation cap.
Only users with maintainer permissions can view the bypass list.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

### HTTP response status codes

* **200** - OK

* **403** - Forbidden

* **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/interaction-limits/pulls/bypass-list
```

**Response schema (Status: 200):**

Array of `Simple User`:

* `name`: string or null
* `email`: string or null
* `login`: required, string
* `id`: required, integer, format: int64
* `node_id`: required, string
* `avatar_url`: required, string, format: uri
* `gravatar_id`: required, string or null
* `url`: required, string, format: uri
* `html_url`: required, string, format: uri
* `followers_url`: required, string, format: uri
* `following_url`: required, string
* `gists_url`: required, string
* `starred_url`: required, string
* `subscriptions_url`: required, string, format: uri
* `organizations_url`: required, string, format: uri
* `repos_url`: required, string, format: uri
* `events_url`: required, string
* `received_events_url`: required, string, format: uri
* `type`: required, string
* `site_admin`: required, boolean
* `starred_at`: string
* `user_view_type`: string

## Add users to the pull request creation cap bypass list for a repository

```
PUT /repos/{owner}/{repo}/interaction-limits/pulls/bypass-list
```

Adds users to the pull request creation cap bypass list for a repository.
Users on this list can create pull requests regardless of any configured
pull request creation cap.
Only users with maintainer permissions can modify the bypass list.
You can add a maximum of 100 users per request.
The bypass list can only hold a maximum of 100 users.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

#### Body parameters

* **`users`** (array of strings) (required)
  A list of user logins to add or remove from the bypass list.

### HTTP response status codes

* **204** - No Content

* **403** - Forbidden

* **404** - Resource not found

* **422** - Validation failed, or the endpoint has been spammed.

### Code examples

#### Example request body

**Request:**

```curl
curl -L \
  -X PUT \
  https://api.github.com/repos/OWNER/REPO/interaction-limits/pulls/bypass-list \
  -d '{
  "users": [
    "octocat",
    "monalisa"
  ]
}'
```

**Response schema (Status: 204):**

## Remove users from the pull request creation cap bypass list for a repository

```
DELETE /repos/{owner}/{repo}/interaction-limits/pulls/bypass-list
```

Removes users from the pull request creation cap bypass list for a repository.
Removed users will be subject to any configured pull request creation cap.
Only users with maintainer permissions can modify the bypass list.
You can remove a maximum of 100 users per request.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

#### Body parameters

* **`users`** (array of strings) (required)
  A list of user logins to add or remove from the bypass list.

### HTTP response status codes

* **204** - No Content

* **403** - Forbidden

* **404** - Resource not found

* **422** - Validation failed, or the endpoint has been spammed.

### Code examples

#### Example request body

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/repos/OWNER/REPO/interaction-limits/pulls/bypass-list \
  -d '{
  "users": [
    "octocat"
  ]
}'
```

**Response schema (Status: 204):**

## Get pull request creation cap for a repository

```
GET /repos/{owner}/{repo}/interaction-limits/pulls/creation-cap
```

Gets the pull request creation cap configuration for a repository.
The cap limits the number of open pull requests a user can have at one time.
Only users with admin access to the repository can view the cap configuration.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

### HTTP response status codes

* **200** - OK

* **403** - Forbidden

* **404** - Resource not found

* **405** - Method Not Allowed

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/interaction-limits/pulls/creation-cap
```

**Response schema (Status: 200):**

* `enabled`: required, boolean
* `max_open_pull_requests`: required, integer, minimum: 1, maximum: 1000

## Update pull request creation cap for a repository

```
PATCH /repos/{owner}/{repo}/interaction-limits/pulls/creation-cap
```

Updates the pull request creation cap for a repository. The cap limits the number
of open pull requests a user can have at one time.
Only users with admin access to the repository can configure the cap.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

* **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

#### Body parameters

* **`enabled`** (boolean) (required)
  Whether the pull request creation cap is enabled

* **`max_open_pull_requests`** (integer)
  The maximum number of open pull requests a user can have at one time

### HTTP response status codes

* **200** - OK

* **403** - Forbidden

* **404** - Resource not found

* **405** - Method Not Allowed

* **422** - Validation failed, or the endpoint has been spammed.

### Code examples

#### Example request body

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/repos/OWNER/REPO/interaction-limits/pulls/creation-cap \
  -d '{
  "enabled": true,
  "max_open_pull_requests": 1
}'
```

**Response schema (Status: 200):**

Same response schema as [Get pull request creation cap for a repository](#get-pull-request-creation-cap-for-a-repository).

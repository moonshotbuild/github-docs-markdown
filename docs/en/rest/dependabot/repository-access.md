---
source_path: "/en/rest/dependabot/repository-access"
title: "REST API endpoints for Dependabot repository access"
intro: "Use the REST API to manage which repositories Dependabot can access within an organization."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Dependabot"
    href: "/en/rest/dependabot"
  - title: "Repository access"
    href: "/en/rest/dependabot/repository-access"
---

# REST API endpoints for Dependabot repository access

Use the REST API to manage which repositories Dependabot can access within an organization.

## About Dependabot repository access

You can list repositories that Dependabot already has access to and set a default repository access level for Dependabot.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## Lists the repositories Dependabot can access in an enterprise

```
GET /enterprises/{enterprise}/dependabot/repository-access
```

Lists repositories that enterprise admins have allowed Dependabot to access when updating dependencies across organizations in the enterprise.
The authenticated user must be an enterprise owner to use this endpoint.
Note

The "Enterprise administration" fine-grained permission is not available to callers. To use this API, you must use an OAuth app token or a personal access token (classic).

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`enterprise`** (string) (required)
  The slug version of the enterprise name.

- **`page`** (integer)
  The page number of results to fetch.
  Default: `1`

- **`per_page`** (integer)
  Number of results per page.
  Default: `30`

### HTTP response status codes

- **200** - OK

- **403** - Forbidden

- **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/enterprises/ENTERPRISE/dependabot/repository-access
```

**Response schema (Status: 200):**

* `default_level`: string or null, enum: `public`, `internal`, `null`
* `accessible_repositories`: array of items:
  * any of:
    * **null**
    * **Simple Repository**
      * `id`: required, integer, format: int64
      * `node_id`: required, string
      * `name`: required, string
      * `full_name`: required, string
      * `owner`: required, `Simple User`:
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
      * `private`: required, boolean
      * `html_url`: required, string, format: uri
      * `description`: required, string or null
      * `fork`: required, boolean
      * `url`: required, string, format: uri
      * `archive_url`: required, string
      * `assignees_url`: required, string
      * `blobs_url`: required, string
      * `branches_url`: required, string
      * `collaborators_url`: required, string
      * `comments_url`: required, string
      * `commits_url`: required, string
      * `compare_url`: required, string
      * `contents_url`: required, string
      * `contributors_url`: required, string, format: uri
      * `deployments_url`: required, string, format: uri
      * `downloads_url`: required, string, format: uri
      * `events_url`: required, string, format: uri
      * `forks_url`: required, string, format: uri
      * `git_commits_url`: required, string
      * `git_refs_url`: required, string
      * `git_tags_url`: required, string
      * `issue_comment_url`: required, string
      * `issue_events_url`: required, string
      * `issues_url`: required, string
      * `keys_url`: required, string
      * `labels_url`: required, string
      * `languages_url`: required, string, format: uri
      * `merges_url`: required, string, format: uri
      * `milestones_url`: required, string
      * `notifications_url`: required, string
      * `pulls_url`: required, string
      * `releases_url`: required, string
      * `stargazers_url`: required, string, format: uri
      * `statuses_url`: required, string
      * `subscribers_url`: required, string, format: uri
      * `subscription_url`: required, string, format: uri
      * `tags_url`: required, string, format: uri
      * `teams_url`: required, string, format: uri
      * `trees_url`: required, string
      * `hooks_url`: required, string, format: uri

## Updates Dependabot's repository access list for an enterprise

```
PATCH /enterprises/{enterprise}/dependabot/repository-access
```

Updates repositories according to the list of repositories that enterprise admins have given Dependabot access to when they've updated dependencies across organizations in the enterprise.
The authenticated user must be an enterprise owner to use this endpoint.
Example request body:
{
  "repository_ids_to_add": [123, 456],
  "repository_ids_to_remove": [789]
}

Note

The "Enterprise administration" fine-grained permission is not available to callers. To use this API, you must use an OAuth app token or a personal access token (classic).

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`enterprise`** (string) (required)
  The slug version of the enterprise name.

#### Body parameters

- **`repository_ids_to_add`** (array of integers)
  List of repository IDs to add.

- **`repository_ids_to_remove`** (array of integers)
  List of repository IDs to remove.

### HTTP response status codes

- **204** - No Content

- **403** - Forbidden

- **404** - Resource not found

### Code examples

#### Example with a 'succeeded' status.

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/enterprises/ENTERPRISE/dependabot/repository-access
```

**Response schema (Status: 204):**

## Set the default repository access level for Dependabot in an enterprise

```
PUT /enterprises/{enterprise}/dependabot/repository-access/default-level
```

Sets the default level of repository access Dependabot will have while performing an update across organizations in the enterprise. Available values are:

'public' - Dependabot will only have access to public repositories, unless access is explicitly granted to non-public repositories.
'internal' - Dependabot will only have access to public and internal repositories, unless access is explicitly granted to private repositories.

The authenticated user must be an enterprise owner to use this endpoint.
Note

The "Enterprise administration" fine-grained permission is not available to callers. To use this API, you must use an OAuth app token or a personal access token (classic).

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`enterprise`** (string) (required)
  The slug version of the enterprise name.

#### Body parameters

- **`default_level`** (string) (required)
  The default repository access level for Dependabot updates.
  Can be one of: `public`, `internal`

### HTTP response status codes

- **204** - No Content

- **403** - Forbidden

- **404** - Resource not found

### Code examples

#### Example with a 'succeeded' status.

**Request:**

```curl
curl -L \
  -X PUT \
  https://api.github.com/enterprises/ENTERPRISE/dependabot/repository-access/default-level \
  -d '{
  "default_level": "public"
}'
```

**Response schema (Status: 204):**

## Lists the repositories Dependabot can access in an organization

```
GET /orgs/{org}/dependabot/repository-access
```

Lists repositories that organization admins have allowed Dependabot to access when updating dependencies.
Note

This operation supports both server-to-server and user-to-server access.
Unauthorized users will not see the existence of this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`page`** (integer)
  The page number of results to fetch.
  Default: `1`

- **`per_page`** (integer)
  Number of results per page.
  Default: `30`

### HTTP response status codes

- **200** - OK

- **403** - Forbidden

- **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/orgs/ORG/dependabot/repository-access
```

**Response schema (Status: 200):**

Same response schema as [Lists the repositories Dependabot can access in an enterprise](#lists-the-repositories-dependabot-can-access-in-an-enterprise).

## Updates Dependabot's repository access list for an organization

```
PATCH /orgs/{org}/dependabot/repository-access
```

Updates repositories according to the list of repositories that organization admins have given Dependabot access to when they've updated dependencies.
Note

This operation supports both server-to-server and user-to-server access.
Unauthorized users will not see the existence of this endpoint.

OAuth app tokens and personal access tokens (classic) need the write:org scope to use this endpoint.
Example request body:
{
  "repository_ids_to_add": [123, 456],
  "repository_ids_to_remove": [789]
}

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

#### Body parameters

- **`repository_ids_to_add`** (array of integers)
  List of repository IDs to add.

- **`repository_ids_to_remove`** (array of integers)
  List of repository IDs to remove.

### HTTP response status codes

- **204** - No Content

- **403** - Forbidden

- **404** - Resource not found

### Code examples

#### Example with a 'succeeded' status.

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/orgs/ORG/dependabot/repository-access
```

**Response schema (Status: 204):**

## Set the default repository access level for Dependabot

```
PUT /orgs/{org}/dependabot/repository-access/default-level
```

Sets the default level of repository access Dependabot will have while performing an update.  Available values are:

'public' - Dependabot will only have access to public repositories, unless access is explicitly granted to non-public repositories.
'internal' - Dependabot will only have access to public and internal repositories, unless access is explicitly granted to private repositories.

Unauthorized users will not see the existence of this endpoint.
This operation supports both server-to-server and user-to-server access.
OAuth app tokens and personal access tokens (classic) need the write:org scope to use this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

#### Body parameters

- **`default_level`** (string) (required)
  The default repository access level for Dependabot updates.
  Can be one of: `public`, `internal`

### HTTP response status codes

- **204** - No Content

- **403** - Forbidden

- **404** - Resource not found

### Code examples

#### Example with a 'succeeded' status.

**Request:**

```curl
curl -L \
  -X PUT \
  https://api.github.com/orgs/ORG/dependabot/repository-access/default-level \
  -d '{
  "default_level": "public"
}'
```

**Response schema (Status: 204):**

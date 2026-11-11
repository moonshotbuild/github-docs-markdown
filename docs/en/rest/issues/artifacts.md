---
source_path: "/en/rest/issues/artifacts"
title: "REST API endpoints for issue artifacts"
intro: "Use the REST API to manage issue artifacts."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Issues"
    href: "/en/rest/issues"
  - title: "Artifacts"
    href: "/en/rest/issues/artifacts"
---

# REST API endpoints for issue artifacts

Use the REST API to manage issue artifacts.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## List issue artifacts

```
GET /repos/{owner}/{repo}/issues/{issue_number}/artifacts
```

Lists artifacts attached to an issue. Results are ordered by artifact number.
The type parameter filters the response to artifacts of one type.
Results can be requested by page. The page defaults to 1; the page size
defaults to 30 and can be set from 1 to 100.
The response is a bare array and does not include pagination metadata such as
a Link header, a total count, or the service's has_next_page signal.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

- **`issue_number`** (integer) (required)
  The number that identifies the issue.

- **`type`** (string)
  The artifact type to return.
  Can be one of: `generic`, `link`, `plan`, `embedded_html`

- **`per_page`** (integer)
  The number of results per page (max 100). For more information, see "Using pagination in the REST API."
  Default: `30`

- **`page`** (integer)
  The page number of the results to fetch. For more information, see "Using pagination in the REST API."
  Default: `1`

### HTTP response status codes

- **200** - A list of artifacts attached to the issue.

- **404** - Resource not found

- **410** - Gone

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/issues/ISSUE_NUMBER/artifacts
```

**Response schema (Status: 200):**

Array of `Issue artifact`:
  * `id`: required, integer, format: int64
  * `html_url`: string, format: uri
  * `number`: required, integer
  * `type`: required, string
  * `name`: required, string
  * `body`: required, string
  * `body_html`: required, string or null
  * `description`: required, string
  * `creator`: required, object or null:
    * `login`: required, string
    * `id`: required, integer, format: int64
  * `updated_by_actor`: required, object or null:
    * `login`: required, string
    * `id`: required, integer, format: int64
  * `created_at`: required, string or null, format: date-time
  * `updated_at`: required, string or null, format: date-time

## Create an issue artifact

```
POST /repos/{owner}/{repo}/issues/{issue_number}/artifacts
```

Creates an artifact attached to an issue.
The artifact type defaults to generic when omitted. Creating an artifact
requires permission to update the issue.
The request can return 403 if the repository is read-only or locked, or a
GitHub App installation has only issues: read permission.
To create an HTML artifact, set type to embedded_html and provide the HTML source
in body. Open the returned html_url to inspect the source, then select
Preview to view the rendered artifact. Select Show source to return
to the HTML source.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

- **`issue_number`** (integer) (required)
  The number that identifies the issue.

#### Body parameters

- **`type`** (string)
  The artifact type.
  Default: `generic`
  Can be one of: `generic`, `link`, `plan`, `embedded_html`

- **`name`** (string) (required)
  The human-readable name of the artifact.

- **`body`** (string) (required)
  The artifact content. For embedded_html artifacts, provide the HTML source.

### HTTP response status codes

- **201** - The created artifact.

- **403** - Forbidden

- **404** - Resource not found

- **410** - Gone

- **422** - Validation failed, or the endpoint has been spammed.

- **429** - Artifact writes are temporarily throttled. Retry after the indicated delay.

- **500** - Internal Error

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X POST \
  https://api.github.com/repos/OWNER/REPO/issues/ISSUE_NUMBER/artifacts \
  -d '{
  "type": "generic",
  "name": "Research notes",
  "body": "## Findings\n\nThe API supports issue artifacts."
}'
```

**Response schema (Status: 201):**

* `id`: required, integer, format: int64
* `html_url`: string, format: uri
* `number`: required, integer
* `type`: required, string
* `name`: required, string
* `body`: required, string
* `body_html`: required, string or null
* `description`: required, string
* `creator`: required, object or null:
  * `login`: required, string
  * `id`: required, integer, format: int64
* `updated_by_actor`: required, object or null:
  * `login`: required, string
  * `id`: required, integer, format: int64
* `created_at`: required, string or null, format: date-time
* `updated_at`: required, string or null, format: date-time

## Get an issue artifact

```
GET /repos/{owner}/{repo}/issues/{issue_number}/artifacts/{artifact_number}
```

Returns an artifact attached to an issue by its per-issue artifact number,
along with its version history ordered from newest to oldest.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

- **`issue_number`** (integer) (required)
  The number that identifies the issue.

- **`artifact_number`** (integer) (required)
  The artifact number within the issue.

- **`per_page`** (integer)
  The number of results per page (max 100). For more information, see "Using pagination in the REST API."
  Default: `30`

- **`page`** (integer)
  The page number of the results to fetch. For more information, see "Using pagination in the REST API."
  Default: `1`

### HTTP response status codes

- **200** - The requested artifact.

- **301** - Moved permanently

- **404** - Resource not found

- **410** - Gone

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/repos/OWNER/REPO/issues/ISSUE_NUMBER/artifacts/ARTIFACT_NUMBER
```

**Response schema (Status: 200):**

* one of:
  * **Issue artifact**
    * `id`: required, integer, format: int64
    * `html_url`: string, format: uri
    * `number`: required, integer
    * `type`: required, string
    * `name`: required, string
    * `body`: required, string
    * `body_html`: required, string or null
    * `description`: required, string
    * `creator`: required, object or null:
      * `login`: required, string
      * `id`: required, integer, format: int64
    * `updated_by_actor`: required, object or null:
      * `login`: required, string
      * `id`: required, integer, format: int64
    * `created_at`: required, string or null, format: date-time
    * `updated_at`: required, string or null, format: date-time
  * **object**
    * `artifact`: required, `Issue artifact` (see above)
    * `has_next_page`: required, boolean
    * `total_count`: required, integer, minimum: 0
    * `versions`: required, array of objects:
      * `version`: required, integer
      * `name`: required, string
      * `body`: required, string
      * `body_html`: required, string or null
      * `created_at`: required, string or null, format: date-time
      * `actor`: required, object or null:
        * `login`: required, string
        * `id`: required, integer, format: int64

## Update an issue artifact

```
PATCH /repos/{owner}/{repo}/issues/{issue_number}/artifacts/{artifact_number}
```

Updates the name, body, or both for an artifact attached to an issue.
Updating an artifact requires permission to update the issue.
The request can return 403 if the repository is read-only or locked, or a
GitHub App installation has only issues: read permission.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

- **`issue_number`** (integer) (required)
  The number that identifies the issue.

- **`artifact_number`** (integer) (required)
  The artifact number within the issue.

#### Body parameters

- **`name`** (string)
  The new human-readable name of the artifact.

- **`body`** (string)
  The new artifact content.

### HTTP response status codes

- **200** - The updated artifact.

- **403** - Forbidden

- **404** - Resource not found

- **410** - Gone

- **422** - Validation failed, or the endpoint has been spammed.

- **429** - Artifact writes are temporarily throttled. Retry after the indicated delay.

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/repos/OWNER/REPO/issues/ISSUE_NUMBER/artifacts/ARTIFACT_NUMBER \
  -d '{
  "name": "Revised implementation plan",
  "body": "## Plan\n\nBuild and validate the feature."
}'
```

**Response schema (Status: 200):**

Same response schema as [Create an issue artifact](#create-an-issue-artifact).

## Delete an issue artifact

```
DELETE /repos/{owner}/{repo}/issues/{issue_number}/artifacts/{artifact_number}
```

Permanently deletes an artifact attached to an issue.
Deleting an artifact requires permission to update the issue.
The request can return 403 if the repository is read-only or locked, or a
GitHub App installation has only issues: read permission.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`owner`** (string) (required)
  The account owner of the repository. The name is not case sensitive.

- **`repo`** (string) (required)
  The name of the repository without the .git extension. The name is not case sensitive.

- **`issue_number`** (integer) (required)
  The number that identifies the issue.

- **`artifact_number`** (integer) (required)
  The artifact number within the issue.

### HTTP response status codes

- **204** - The artifact was deleted successfully. No content is returned.

- **403** - Forbidden

- **404** - Resource not found

- **410** - Gone

- **429** - Artifact writes are temporarily throttled. Retry after the indicated delay.

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/repos/OWNER/REPO/issues/ISSUE_NUMBER/artifacts/ARTIFACT_NUMBER
```

**Response schema (Status: 204):**

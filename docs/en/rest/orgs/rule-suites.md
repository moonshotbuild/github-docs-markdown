---
source_path: "/en/rest/orgs/rule-suites"
title: "REST API endpoints for rule suites"
intro: "Use the REST API to manage rule suites for organizations."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Organizations"
    href: "/en/rest/orgs"
  - title: "Rule suites"
    href: "/en/rest/orgs/rule-suites"
---

# REST API endpoints for rule suites

Use the REST API to manage rule suites for organizations.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## List organization rule suites

```
GET /orgs/{org}/rulesets/rule-suites
```

Lists suites of rule evaluations at the organization level.
For more information, see "Managing rulesets for repositories in your organization."

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`ref`** (string)
  The name of the ref. Cannot contain wildcard characters. Optionally prefix with refs/heads/ to limit to branches or refs/tags/ to limit to tags. Omit the prefix to search across all refs. When specified, only rule evaluations triggered for this ref will be returned.

- **`repository_name`** (string)
  The name of the repository to filter on.

- **`time_period`** (string)
  The time period to filter by.
For example, day will filter for rule suites that occurred in the past 24 hours, and week will filter for rule suites that occurred in the past 7 days (168 hours).
  Default: `day`
  Can be one of: `hour`, `day`, `week`, `month`

- **`actor_name`** (string)
  The handle for the GitHub user account to filter on. When specified, only rule evaluations triggered by this actor will be returned.

- **`rule_suite_result`** (string)
  The rule suite results to filter on. When specified, only suites with this result will be returned.
  Default: `all`
  Can be one of: `pass`, `fail`, `bypass`, `all`

- **`evaluate_status`** (string)
  The evaluate status to filter on. When specified, only rule suites resulting from rulesets with the specified evaluate status will be returned.

all - all rule suites will be returned.
active - only rule suites resulting from rulesets in active (non-evaluate) mode will be returned.
evaluate - only rule suites resulting from rulesets in evaluate mode will be returned.
  Default: `all`
  Can be one of: `all`, `active`, `evaluate`

- **`per_page`** (integer)
  The number of results per page (max 100). For more information, see "Using pagination in the REST API."
  Default: `30`

- **`page`** (integer)
  The page number of the results to fetch. For more information, see "Using pagination in the REST API."
  Default: `1`

### HTTP response status codes

- **200** - OK

- **404** - Resource not found

- **500** - Internal Error

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/orgs/ORG/rulesets/rule-suites
```

**Response schema (Status: 200):**

Array of objects:
  * `id`: integer
  * `actor_id`: integer
  * `actor_name`: string
  * `before_sha`: string
  * `after_sha`: string
  * `ref`: string
  * `repository_id`: integer
  * `repository_name`: string
  * `pushed_at`: string, format: date-time
  * `result`: string, enum: `pass`, `fail`, `bypass`
  * `evaluation_result`: string, enum: `pass`, `fail`, `bypass`

## Get an organization rule suite

```
GET /orgs/{org}/rulesets/rule-suites/{rule_suite_id}
```

Gets information about a suite of rule evaluations from within an organization.
For more information, see "Managing rulesets for repositories in your organization."

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`rule_suite_id`** (integer) (required)
  The unique identifier of the rule suite result.
To get this ID, you can use GET /repos/{owner}/{repo}/rulesets/rule-suites
for repositories and GET /orgs/{org}/rulesets/rule-suites
for organizations.

### HTTP response status codes

- **200** - OK

- **404** - Resource not found

- **500** - Internal Error

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/orgs/ORG/rulesets/rule-suites/RULE_SUITE_ID
```

**Response schema (Status: 200):**

* `id`: integer
* `actor_id`: integer or null
* `actor_name`: string or null
* `before_sha`: string
* `after_sha`: string
* `ref`: string
* `repository_id`: integer
* `repository_name`: string
* `pushed_at`: string, format: date-time
* `result`: string, enum: `pass`, `fail`, `bypass`
* `evaluation_result`: string or null, enum: `pass`, `fail`, `bypass`, `null`
* `rule_evaluations`: array of objects:
  * `rule_source`: object:
    * `type`: string
    * `id`: integer or null
    * `name`: string or null
  * `enforcement`: string, enum: `active`, `evaluate`, `deleted ruleset`
  * `result`: string, enum: `pass`, `fail`
  * `rule_type`: string
  * `details`: string or null

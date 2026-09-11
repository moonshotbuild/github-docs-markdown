---
source_path: "/en/rest/code-scanning/ai-scan"
title: "REST API endpoints for AI Scan"
intro: "Use the REST API to get and update AI Scan settings for an organization."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Code scanning"
    href: "/en/rest/code-scanning"
  - title: "AI Scan"
    href: "/en/rest/code-scanning/ai-scan"
---

# REST API endpoints for AI Scan

Use the REST API to get and update AI Scan settings for an organization.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## Get the AI Scan setting for an organization

```
GET /orgs/{org}/code-scanning/ai-scan
```

Note

This endpoint is in public preview and is subject to change.

Gets the AI Scan setting stored on an organization.
The response reports the value stored on the organization. Organization respects enterprise policy.
The authenticated user must be an owner or security manager for the organization to use this endpoint.
OAuth app tokens and personal access tokens (classic) need the admin:org, repo, or write:org scope to use this endpoint. Organization owners can use admin:org or repo; security managers need write:org.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

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
  https://api.github.com/orgs/ORG/code-scanning/ai-scan
```

**Response schema (Status: 200):**

* `pr_scan`: required, string, enum: `enabled`, `disabled`

## Update the AI Scan setting for an organization

```
PATCH /orgs/{org}/code-scanning/ai-scan
```

Note

This endpoint is in public preview and is subject to change.

Updates the AI Scan setting stored on an organization.
The organization respects the enterprise policy, so enabling is rejected when the enterprise disallows AI Scan.
OAuth app tokens and personal access tokens (classic) need the admin:org, repo, or write:org scope to use this endpoint. Organization owners can use admin:org or repo; security managers need write:org.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

#### Body parameters

- **`pr_scan`** (string)
  Whether AI Scan is enabled for the organization. Organization respects enterprise policy. Disabled organizations prevent repositories from enabling AI Scan. Enabled organizations enable AI Scan for their repositories, but individual repositories can opt out.
  Can be one of: `enabled`, `disabled`

### HTTP response status codes

- **200** - OK

- **403** - Forbidden

- **404** - Resource not found

- **422** - Validation failed, or the endpoint has been spammed.

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/orgs/ORG/code-scanning/ai-scan \
  -d '{
  "pr_scan": "enabled"
}'
```

**Response schema (Status: 200):**

Same response schema as [Get the AI Scan setting for an organization](#get-the-ai-scan-setting-for-an-organization).

---
source_path: "/en/rest/copilot/copilot-team-customizations"
title: "REST API endpoints for Copilot team customizations"
intro: "Use the REST API to manage Copilot customizations for a team."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Copilot"
    href: "/en/rest/copilot"
  - title: "Copilot team customizations"
    href: "/en/rest/copilot/copilot-team-customizations"
---

# REST API endpoints for Copilot team customizations

Use the REST API to manage Copilot customizations for a team.

## About Copilot team customizations

A Copilot customization document defines the plugins and plugin marketplaces available to members of an organization team. GitHub stores one document for each team. You can create and manage the document on the team's **Customize Copilot** tab, or with these endpoints.

The customization document supports these top-level keys:

* `pluginAssignments`: Plugins available to the team, keyed by `PLUGIN@MARKETPLACE`. Each plugin is enabled by default.
* `extraKnownMarketplaces`: Additional plugin marketplaces available to the team, keyed by marketplace name.

The request and response examples below show a plugin and its marketplace.

## Access requirements

The authenticated user must be an organization owner or a maintainer of the team. For an enterprise team assigned to the organization, including one synced with an identity provider group, the authenticated user must be an organization owner. The required scopes and permissions are in addition to these role requirements.

| Token type | Read customizations | Replace or delete customizations |
| --- | --- | --- |
| Personal access token (classic) or OAuth app token | `read:org` or `admin:org` scope | `admin:org` scope |
| Fine-grained personal access token or GitHub App user access token | Organization "Copilot agent settings" permission with read access | Organization "Copilot agent settings" permission with write access |

## Creating and updating customizations

To create a team's customization document, send the complete document as the JSON request body to the `PUT` endpoint. Do not wrap it in another object. A successful request returns `200 OK` with the submitted document.

The `PUT` endpoint replaces the entire document. It does not merge the request with existing customizations. Any plugin or marketplace omitted from the request is removed from the stored document.

To edit an existing document:

1. Get the team's current customization document using the `GET` endpoint.
1. Edit the document, retaining every plugin and marketplace you want to keep.
1. Send the complete document to the `PUT` endpoint.

Reading a document before replacing it does not prevent another edit between requests.

The `GET` endpoint returns `404 Not Found` when the team has no document. A `404` can also mean the team is not accessible to the authenticated user.

To remove the team's customization document, use the `DELETE` endpoint. It returns `204 No Content` even if the document does not exist. This does not delete the team.

Invalid documents return `422 Unprocessable Entity` with the reason. A concurrent edit can cause a write or delete to return `409 Conflict`.

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## Get Copilot customizations for a team

```
GET /orgs/{org}/teams/{team_slug}/copilot/customizations
```

Note

This endpoint is in public preview and is subject to change.

Gets the GitHub-managed Copilot customizations of a team.
The authenticated user must be an organization owner or a team maintainer. Teams that keep their
customizations in a repository return 409.
OAuth app tokens and personal access tokens (classic) need the admin:org or read:org scope to use this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`team_slug`** (string) (required)
  The slug of the team name.

### HTTP response status codes

- **200** - OK

- **401** - Requires authentication

- **403** - Forbidden

- **404** - Resource not found

- **409** - Conflict

- **422** - Validation failed, or the endpoint has been spammed.

- **500** - Internal Error

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/orgs/ORG/teams/TEAM_SLUG/copilot/customizations
```

**Response schema (Status: 200):**

* `pluginAssignments`: object, additional properties: object
* `extraKnownMarketplaces`: object, additional properties: object

## Set Copilot customizations for a team

```
PUT /orgs/{org}/teams/{team_slug}/copilot/customizations
```

Note

This endpoint is in public preview and is subject to change.

Replaces the GitHub-managed Copilot customizations of a team, creating them on the first write.
The authenticated user must be an organization owner or a team maintainer. Teams that keep their
customizations in a repository return 409. Documents that fail validation return 422 with the reason.
OAuth app tokens and personal access tokens (classic) need the admin:org scope to use this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`team_slug`** (string) (required)
  The slug of the team name.

#### Body parameters

- **`pluginAssignments`** (object)
  Plugins assigned to the team, keyed by PLUGIN@MARKETPLACE.
  - **`key`** (object)
    A user-defined key to represent an item in pluginAssignments.
    - **`state`** (string)
      The assignment state.
      Can be one of: `defaultEnabled`

- **`extraKnownMarketplaces`** (object)
  Additional plugin marketplaces available to the team, keyed by marketplace name.
  - **`key`** (object)
    A user-defined key to represent an item in extraKnownMarketplaces.

### HTTP response status codes

- **200** - OK

- **401** - Requires authentication

- **403** - Forbidden

- **404** - Resource not found

- **409** - Conflict

- **422** - Validation failed, or the endpoint has been spammed.

- **500** - Internal Error

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X PUT \
  https://api.github.com/orgs/ORG/teams/TEAM_SLUG/copilot/customizations \
  -d '{
  "pluginAssignments": {
    "code-review@acme-marketplace": {
      "state": "defaultEnabled"
    }
  },
  "extraKnownMarketplaces": {
    "acme-marketplace": {
      "source": {
        "source": "github",
        "repo": "acme/copilot-marketplace"
      }
    }
  }
}'
```

**Response schema (Status: 200):**

Same response schema as [Get Copilot customizations for a team](#get-copilot-customizations-for-a-team).

## Delete Copilot customizations for a team

```
DELETE /orgs/{org}/teams/{team_slug}/copilot/customizations
```

Note

This endpoint is in public preview and is subject to change.

Deletes the GitHub-managed Copilot customizations of a team. Deleting customizations that don't exist succeeds.
The authenticated user must be an organization owner or a team maintainer. Teams that keep their
customizations in a repository return 409.
OAuth app tokens and personal access tokens (classic) need the admin:org scope to use this endpoint.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`team_slug`** (string) (required)
  The slug of the team name.

### HTTP response status codes

- **204** - No Content

- **401** - Requires authentication

- **403** - Forbidden

- **404** - Resource not found

- **409** - Conflict

- **422** - Validation failed, or the endpoint has been spammed.

- **500** - Internal Error

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/orgs/ORG/teams/TEAM_SLUG/copilot/customizations
```

**Response schema (Status: 204):**

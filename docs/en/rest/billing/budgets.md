---
source_path: "/en/rest/billing/budgets"
title: "Budgets"
intro: "Use the REST API to get budget information."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Billing"
    href: "/en/rest/billing"
  - title: "Budgets"
    href: "/en/rest/billing/budgets"
---

# Budgets

Use the REST API to get budget information.

> [!IMPORTANT]
> The request body schema below is missing a required field. When `budget_scope` is `user`, you must also include a `user` field set to the GitHub username the budget applies to. If you omit this field, the API returns `HTTP 400: Missing required fields: budget_entity_name`. For user-scoped budgets, `budget_entity_name` can be an empty string.

The following example creates a user-scoped budget that limits a single user's monthly Copilot AI credits to $30 USD:

```json
{
  "budget_amount": 30,
  "prevent_further_usage": true,
  "budget_scope": "user",
  "budget_entity_name": "",
  "budget_type": "BundlePricing",
  "budget_product_sku": "ai_credits",
  "budget_alerting": {
    "will_alert": false,
    "alert_recipients": []
  },
  "user": "USERNAME"
}
```

> [!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## Get all budgets for an organization

```
GET /organizations/{org}/settings/billing/budgets
```

Gets all budgets for an organization. The authenticated user must be an organization admin or billing manager.
Each page returns up to 100 budgets.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`page`** (integer)
  The page number of the results to fetch.
  Default: `1`

- **`per_page`** (integer)
  The number of results per page (max 100).
  Default: `10`

- **`scope`** (string)
  Filter budgets by scope type.

organization: Budgets scoped to the organization.
repository: Budgets scoped to a repository.
multi_user_customer: Universal budgets that apply to all users in the organization.
user: Budgets scoped to an individual user.
  Can be one of: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `user`

- **`user`** (string)
  Filter consumed amount details for budgets by the specified user login.

### HTTP response status codes

- **200** - Response when getting all budgets

- **403** - Forbidden

- **404** - Resource not found

- **500** - Internal Error

### Code examples

#### Example 1: Status Code 200

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/organizations/ORG/settings/billing/budgets
```

**Response schema (Status: 200):**

* `budgets`: required, array of objects:
  * `id`: required, string
  * `budget_type`: required, one of:
    * **string, enum: `SkuPricing`**
    * **string, enum: `ProductPricing`**
  * `budget_amount`: required, integer
  * `prevent_further_usage`: required, boolean
  * `budget_scope`: required, string, enum: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `multi_user_cost_center`, `user`
  * `budget_entity_name`: string
  * `user`: string
  * `consumed_amount`: number
  * `budget_product_sku`: required, string
  * `budget_alerting`: required, object:
    * `will_alert`: required, boolean
    * `alert_recipients`: required, array of string
* `user`: string
* `effective_budget`: object:
  * `id`: required, string
  * `budget_amount`: required, integer
  * `consumed_amount`: required, number
* `has_next_page`: boolean
* `total_count`: integer

#### Example 2: Status Code 200

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/organizations/ORG/settings/billing/budgets
```

**Response schema (Status: 200):**

* `budgets`: required, array of objects:
  * `id`: required, string
  * `budget_type`: required, one of:
    * **string, enum: `SkuPricing`**
    * **string, enum: `ProductPricing`**
  * `budget_amount`: required, integer
  * `prevent_further_usage`: required, boolean
  * `budget_scope`: required, string, enum: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `multi_user_cost_center`, `user`
  * `budget_entity_name`: string
  * `user`: string
  * `consumed_amount`: number
  * `budget_product_sku`: required, string
  * `budget_alerting`: required, object:
    * `will_alert`: required, boolean
    * `alert_recipients`: required, array of string
* `user`: string
* `effective_budget`: object:
  * `id`: required, string
  * `budget_amount`: required, integer
  * `consumed_amount`: required, number
* `has_next_page`: boolean
* `total_count`: integer

## Create a budget for an organization

```
POST /organizations/{org}/settings/billing/budgets
```

Creates a new budget for an organization. The authenticated user must be an
organization admin or billing manager.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

#### Body parameters

- **`budget_amount`** (integer)
  The budget amount in whole dollars. For license-based products, this represents the number of licenses.

- **`prevent_further_usage`** (boolean)
  Whether to prevent additional spending once the budget is exceeded. For user and multi_user_customer scopes, this must be true.

- **`budget_alerting`** (object)
  - **`will_alert`** (boolean)
    Whether alerts are enabled for this budget. Rejected for user-scope as alerting is always disabled for them.
  - **`alert_recipients`** (array of strings)
    Array of user login names who will receive alerts. Rejected for user-scope as alerting is always disabled for them.

- **`budget_scope`** (string)
  The scope of the budget for this organization.

organization: Apply the budget to the organization.
repository: Apply the budget to a specific repository in the organization.
multi_user_customer: Apply a universal budget to all users in the organization.
user: Apply the budget to a single user in the organization.

user and multi_user_customer scopes are only supported when
budget_product_sku is ai_credits or premium_requests.
  Can be one of: `organization`, `repository`, `multi_user_customer`, `user`

- **`budget_entity_name`** (string)
  The name of the entity to apply the budget to
  Default: ``

- **`budget_type`** (string)
  The type of pricing model used by the budget. Determines how budget_product_sku is interpreted.

BundlePricing: Covers all AI credit SKUs. Set budget_product_sku to ai_credits.
ProductPricing: Covers all SKUs that belong to a product. Set budget_product_sku to a product such as actions or packages.
SkuPricing: Covers a single, specific SKU. Set budget_product_sku to a SKU such as actions_linux.

- **`budget_product_sku`** (string)
  A single product or SKU that will be covered in the budget

- **`user`** (string)
  The username of the user for user scope budgets. This field is required when budget_scope is user.

### HTTP response status codes

- **200** - Budget created successfully

- **400** - Bad Request

- **401** - Requires authentication

- **403** - Insufficient permissions

- **404** - Feature not enabled or organization not found

- **422** - Validation failed, or the endpoint has been spammed.

- **500** - Internal server error

### Code examples

#### Create organization budget example

**Request:**

```curl
curl -L \
  -X POST \
  https://api.github.com/organizations/ORG/settings/billing/budgets \
  -d '{
  "budget_amount": 500,
  "prevent_further_usage": true,
  "budget_scope": "organization",
  "budget_entity_name": "",
  "budget_type": "ProductPricing",
  "budget_product_sku": "actions",
  "budget_alerting": {
    "will_alert": false,
    "alert_recipients": []
  }
}'
```

**Response schema (Status: 200):**

* `message`: required, string
* `budget`: required, object:
  * `id`: string
  * `budget_scope`: string, enum: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `multi_user_cost_center`, `user`
  * `budget_entity_name`: string
  * `budget_amount`: integer, minimum: 0
  * `prevent_further_usage`: boolean
  * `budget_product_sku`: string
  * `budget_type`: one of:
    * **string, enum: `ProductPricing`**
    * **string, enum: `SkuPricing`**
  * `budget_alerting`: object:
    * `will_alert`: boolean
    * `alert_recipients`: array of string

## Get a budget by ID for an organization

```
GET /organizations/{org}/settings/billing/budgets/{budget_id}
```

Gets a budget by ID. The authenticated user must be an organization admin or billing manager.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`budget_id`** (string) (required)
  The ID corresponding to the budget.

### HTTP response status codes

- **200** - Response when updating a budget

- **400** - Bad Request

- **403** - Forbidden

- **404** - Resource not found

- **500** - Internal Error

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/organizations/ORG/settings/billing/budgets/BUDGET_ID
```

**Response schema (Status: 200):**

* `id`: required, string
* `budget_scope`: required, string, enum: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `multi_user_cost_center`, `user`
* `budget_entity_name`: required, string
* `user`: string
* `budget_amount`: required, integer
* `prevent_further_usage`: required, boolean
* `budget_product_sku`: required, string
* `budget_type`: required, one of:
  * **string, enum: `ProductPricing`**
  * **string, enum: `SkuPricing`**
* `budget_alerting`: required, object:
  * `will_alert`: boolean
  * `alert_recipients`: array of string

## Update a budget for an organization

```
PATCH /organizations/{org}/settings/billing/budgets/{budget_id}
```

Updates an existing budget for an organization. The authenticated user must be an organization admin or billing manager.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`budget_id`** (string) (required)
  The ID corresponding to the budget.

#### Body parameters

- **`budget_amount`** (integer)
  The budget amount in whole dollars. For license-based products, this represents the number of licenses.

- **`prevent_further_usage`** (boolean)
  Whether to prevent additional spending once the budget is exceeded. For budgets with user or multi_user_customer scope, this must remain true.

- **`budget_alerting`** (object)
  - **`will_alert`** (boolean)
    Whether alerts are enabled for this budget. Ignored for user-scopes as alerting is always disabled for them.
  - **`alert_recipients`** (array of strings)
    Array of user login names who will receive alerts. Ignored for user-scopes as alerting is always disabled for them.

- **`budget_scope`** (string)
  The scope of the budget for this organization.

organization: Apply the budget to the organization.
repository: Apply the budget to a specific repository in the organization.
multi_user_customer: Apply a universal budget to all users in the organization.
user: Apply the budget to a single user in the organization.
  Can be one of: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `user`

- **`budget_entity_name`** (string)
  The name of the entity to apply the budget to

- **`budget_type`** (string)
  The type of pricing model used by the budget. Determines how budget_product_sku is interpreted.

BundlePricing: Covers all AI credit SKUs. Set budget_product_sku to ai_credits.
ProductPricing: Covers all SKUs that belong to a product. Set budget_product_sku to a product such as actions or packages.
SkuPricing: Covers a single, specific SKU. Set budget_product_sku to a SKU such as actions_linux.

- **`budget_product_sku`** (string)
  A single product or SKU that will be covered in the budget

- **`user`** (string)
  The username of the user for user scope budgets.

### HTTP response status codes

- **200** - Budget updated successfully

- **400** - Bad Request

- **401** - Requires authentication

- **403** - Forbidden

- **404** - Budget not found or feature not enabled

- **422** - Validation failed, or the endpoint has been spammed.

- **500** - Internal server error

### Code examples

#### Update budget example

**Request:**

```curl
curl -L \
  -X PATCH \
  https://api.github.com/organizations/ORG/settings/billing/budgets/BUDGET_ID \
  -d '{
  "prevent_further_usage": false,
  "budget_amount": 10,
  "budget_alerting": {
    "will_alert": false,
    "alert_recipients": []
  }
}'
```

**Response schema (Status: 200):**

* `message`: required, string
* `budget`: required, object:
  * `id`: string
  * `budget_scope`: string, enum: `enterprise`, `organization`, `repository`, `cost_center`, `multi_user_customer`, `multi_user_cost_center`, `user`
  * `budget_entity_name`: string
  * `user`: string
  * `consumed_amount`: number
  * `budget_amount`: integer, minimum: 0
  * `prevent_further_usage`: boolean
  * `budget_product_sku`: string
  * `budget_type`: one of:
    * **string, enum: `ProductPricing`**
    * **string, enum: `SkuPricing`**
  * `budget_alerting`: object:
    * `will_alert`: boolean
    * `alert_recipients`: array of string

## Delete a budget for an organization

```
DELETE /organizations/{org}/settings/billing/budgets/{budget_id}
```

Deletes a budget by ID for an organization. The authenticated user must be an organization admin or billing manager.

### Parameters

#### Headers

- **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

- **`org`** (string) (required)
  The organization name. The name is not case sensitive.

- **`budget_id`** (string) (required)
  The ID corresponding to the budget.

### HTTP response status codes

- **200** - Response when deleting a budget

- **400** - Bad Request

- **403** - Forbidden

- **404** - Resource not found

- **500** - Internal Error

- **503** - Service unavailable

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/organizations/ORG/settings/billing/budgets/BUDGET_ID
```

**Response schema (Status: 200):**

* `message`: required, string
* `id`: required, string

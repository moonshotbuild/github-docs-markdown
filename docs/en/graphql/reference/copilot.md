---
source_path: "/en/graphql/reference/copilot"
title: "Copilot"
intro: "Reference documentation for GraphQL schema types in the Copilot category."
product: "GraphQL API"
document_type: "article"
breadcrumbs:
  - title: "GraphQL API"
    href: "/en/graphql"
  - title: "Reference"
    href: "/en/graphql/reference"
  - title: "Copilot"
    href: "/en/graphql/reference/copilot"
---

# Copilot

Reference documentation for GraphQL schema types in the Copilot category.

## Agentic - interface

Copilot Agentic fields in context of the current viewer.

### Fields for `Agentic`

* `viewerCopilotAgentCreatesChannel` (String): Channel value for subscribing to live updates for session creations.
* `viewerCopilotAgentLogUpdatesChannel` (String): Channel value for subscribing to live updates for session log updates.
* `viewerCopilotAgentTaskUpdatesChannel` (String): Channel value for subscribing to live updates for task updates.
* `viewerCopilotAgentUpdatesChannel` (String): Channel value for subscribing to live updates for session updates.

### Implemented by

* User

## CopilotCodeReviewEffort - enum

The effort level for a Copilot code review. For more information, see Review effort level.

### Values for `CopilotCodeReviewEffort`

* `AUTO`: Copilot picks the effort for each pull request.
* `BALANCED`: Balanced effort and depth.
* `LITE`: Lower effort, faster review.
* `MAX`: Highest effort, deepest review.

## CopilotCodeReviewRequestReason - enum

The stable reason a Copilot code review request was denied or conflicted with an existing request.

### Values for `CopilotCodeReviewRequestReason`

* `ACTOR_INELIGIBLE`: The actor is not eligible to request Copilot code reviews.
* `APP_NOT_INSTALLED`: The Copilot code review reviewer app is not installed.
* `LICENSED_ORGANIZATION_UNAVAILABLE`: The organization providing the Copilot license is unavailable.
* `NO_QUOTA_REMAINING`: The actor has no Copilot code review quota remaining.
* `REPOSITORY_INELIGIBLE`: The repository is not eligible for Copilot code reviews.
* `REQUEST_CONFLICT`: A Copilot code review request is already pending for this pull request.

## CopilotEndpoints - object

Copilot endpoint information.

### Fields for `CopilotEndpoints`

* `api` (String!): Copilot API endpoint.
* `exp` (String): Copilot experimentation (edge TAS) endpoint.
* `originTracker` (String!): Copilot origin tracker endpoint.
* `proxy` (String!): Copilot proxy endpoint.
* `telemetry` (String!): Copilot telemetry endpoint.

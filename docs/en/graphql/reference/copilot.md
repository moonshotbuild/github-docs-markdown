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

## CopilotCodeReviewEffortLevel - enum

A Copilot code review effort level. For more information, see Review effort level.

### Values for `CopilotCodeReviewEffortLevel`

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

## CopilotCodeReviewRunnerConfiguredBy - enum

Which configuration an organization's Copilot code review runner values come from.

### Values for `CopilotCodeReviewRunnerConfiguredBy`

* `CODE_REVIEW`: The organization has saved a Copilot code review runner configuration.
* `CODING_AGENT`: The values are inherited from the organization's Copilot coding agent runner configuration.

## CopilotCodeReviewRunnerType - enum

The type of runner Copilot code review uses.

### Values for `CopilotCodeReviewRunnerType`

* `LABELED`: Runners that match the configured labels or runner group.
* `STANDARD`: Standard GitHub-hosted runners.

## CopilotCodeReviewSeverityFilter - enum

Which review comment severities Copilot code review leaves out.

### Values for `CopilotCodeReviewSeverityFilter`

* `LOW`: Leave out low-severity comments.
* `LOW_AND_MEDIUM`: Leave out low- and medium-severity comments.
* `NO_FILTER`: Keep every comment.

## CopilotEndpoints - object

Copilot endpoint information.

### Fields for `CopilotEndpoints`

* `api` (String!): Copilot API endpoint.
* `exp` (String): Copilot experimentation (edge TAS) endpoint.
* `originTracker` (String!): Copilot origin tracker endpoint.
* `proxy` (String!): Copilot proxy endpoint.
* `telemetry` (String!): Copilot telemetry endpoint.

## EnterpriseCopilotCodeReviewPolicy - object

The enterprise's configured Copilot code review policy, not a user's effective policy.

### Fields for `EnterpriseCopilotCodeReviewPolicy`

* `policyState` (EnterpriseCopilotCodeReviewPolicyState): The configured policy. Null if the enterprise has not configured a policy.

## EnterpriseCopilotCodeReviewPolicyState - enum

The configured Copilot code review policy for an enterprise.

### Values for `EnterpriseCopilotCodeReviewPolicyState`

* `CONFIGURED_BY_ORGANIZATION_ADMINS`: Organization administrators configure Copilot code review. Not supported for standalone enterprises.
* `DISABLED_FOR_ALL_ORGANIZATIONS`: Copilot code review is disabled for all organizations.
* `ENABLED_FOR_ALL_ORGANIZATIONS`: Copilot code review is enabled for all organizations.

## OrganizationCopilotCodeReviewDefaultEffort - object

An organization's default Copilot code review effort.

### Fields for `OrganizationCopilotCodeReviewDefaultEffort`

* `configured` (CopilotCodeReviewEffortLevel): The effort stored for the organization. Null if the organization inherits the
default or has stored an effort that is not currently available.
* `editable` (Boolean!): Whether organization administrators can update the setting.
* `effective` (CopilotCodeReviewEffortLevel!): The effort that repositories without their own setting use. When that effort
is not currently available, this reports the fallback effort instead.
* `githubDefault` (CopilotCodeReviewEffortLevel!): The effort the organization inherits when it does not configure one: the
enterprise default when one applies, otherwise GitHub's default.
* `managedBy` (OrganizationCopilotCodeReviewPolicyManager!): Whether the enterprise or the organization controls the setting.

## OrganizationCopilotCodeReviewEffortSetting - enum

The default Copilot code review effort to set for an organization. For more
information, see Review effort level.

### Values for `OrganizationCopilotCodeReviewEffortSetting`

* `AUTO`: Copilot picks the effort for each pull request.
* `BALANCED`: Balanced effort and depth.
* `INHERIT`: Clear the organization's value so repositories inherit the default.
* `LITE`: Lower effort, faster review.
* `MAX`: Highest effort, deepest review.

## OrganizationCopilotCodeReviewPolicy - object

The organization's configured and effective Copilot code review policy.

### Fields for `OrganizationCopilotCodeReviewPolicy`

* `configuredState` (OrganizationCopilotCodeReviewPolicyState): The policy stored for the organization. Null if the organization has not configured a policy.
* `editable` (Boolean!): Whether organization administrators can update the policy.
* `effectiveState` (OrganizationCopilotCodeReviewPolicyState!): The policy that applies to the organization after enterprise policy is considered.
* `managedBy` (OrganizationCopilotCodeReviewPolicyManager!): Whether the enterprise or the organization controls the policy.

## OrganizationCopilotCodeReviewPolicyConflict - enum

Why an organization's Copilot code review policy was not updated.

### Values for `OrganizationCopilotCodeReviewPolicyConflict`

* `POLICY_MANAGED_BY_ENTERPRISE`: The enterprise policy controls the organization's policy.

## OrganizationCopilotCodeReviewPolicyManager - enum

The scope that controls an organization's Copilot code review policy.

### Values for `OrganizationCopilotCodeReviewPolicyManager`

* `ENTERPRISE`: The enterprise policy controls the organization's policy.
* `ORGANIZATION`: Organization administrators control the policy.

## OrganizationCopilotCodeReviewPolicyState - enum

The Copilot code review policy state for an organization.

### Values for `OrganizationCopilotCodeReviewPolicyState`

* `DISABLED`: Copilot code review is disabled.
* `ENABLED`: Copilot code review is enabled.

## OrganizationCopilotCodeReviewRunnerConfiguration - object

The effective runner configuration that Copilot code review uses for an organization.

### Fields for `OrganizationCopilotCodeReviewRunnerConfiguration`

* `allowRepositoryCustomization` (Boolean!): Whether repositories can use their own runner configuration.
* `configuredBy` (CopilotCodeReviewRunnerConfiguredBy!): Which configuration the values come from. CODING_AGENT means they are
inherited from the organization's Copilot coding agent runner configuration.
* `runnerGroupName` (String): The runner group used for a labeled runner, if any.
* `runnerLabels` ([String!]!): The runner labels used for a labeled runner.
* `runnerType` (CopilotCodeReviewRunnerType!): The type of runner.

## OrganizationCopilotCodeReviewSettings - object

An organization's Copilot code review settings.

### Fields for `OrganizationCopilotCodeReviewSettings`

* `availableReviewEfforts` ([CopilotCodeReviewEffortLevel!]!): The review efforts that can currently be set for this organization, in display order.
* `defaultReviewEffort` (OrganizationCopilotCodeReviewDefaultEffort!): The default review effort for repositories that do not choose their own.

## OrganizationCopilotCodeReviewSettingsConflict - enum

Why an organization's Copilot code review settings were not updated.

### Values for `OrganizationCopilotCodeReviewSettingsConflict`

* `SETTING_NOT_EDITABLE`: The organization cannot change a submitted setting.

## RepositoryCopilotCodeReviewEffort - object

A repository's Copilot code review effort.

### Fields for `RepositoryCopilotCodeReviewEffort`

* `configured` (CopilotCodeReviewEffortLevel): The effort stored for the repository. Null if the repository inherits its
effort or has stored an effort that is not currently available.
* `effective` (CopilotCodeReviewEffortLevel!): The effort reviews use when the requester and the pull request do not choose
one. When that effort is not currently available, this reports the effort
reviews would use without it.

## RepositoryCopilotCodeReviewEffortSetting - enum

The Copilot code review effort to set for a repository. For more information,
see Review effort level.

### Values for `RepositoryCopilotCodeReviewEffortSetting`

* `AUTO`: Copilot picks the effort for each pull request.
* `BALANCED`: Balanced effort and depth.
* `INHERIT`: Clear the repository's value so it inherits the effort from its organization, enterprise, or GitHub's default.
* `LITE`: Lower effort, faster review.
* `MAX`: Highest effort, deepest review.

## RepositoryCopilotCodeReviewSettings - object

A repository's Copilot code review settings. These settings tune reviews; they do not enable Copilot code review.

### Fields for `RepositoryCopilotCodeReviewSettings`

* `availableReviewEfforts` ([CopilotCodeReviewEffortLevel!]!): The review efforts that can currently be set for this repository, in display order.
* `customInstructionsEnabled` (Boolean!): Whether reviews use the repository's custom instructions.
* `mcpEnabled` (Boolean!): Whether reviews can use MCP servers.
* `reviewEffort` (RepositoryCopilotCodeReviewEffort!): The repository's review effort.
* `severityFilter` (CopilotCodeReviewSeverityFilter!): Which review comment severities Copilot code review leaves out.

## updateEnterpriseCopilotCodeReviewPolicy - mutation

Updates an enterprise's Copilot code review policy using the existing policy propagation and notification behavior.

### Input fields for `updateEnterpriseCopilotCodeReviewPolicy`

* `input` (UpdateEnterpriseCopilotCodeReviewPolicyInput!): 

### Return fields for `updateEnterpriseCopilotCodeReviewPolicy`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `policy` (EnterpriseCopilotCodeReviewPolicy): The updated enterprise policy.

## UpdateEnterpriseCopilotCodeReviewPolicyInput - input object

Autogenerated input type of UpdateEnterpriseCopilotCodeReviewPolicy.

### Input fields for `UpdateEnterpriseCopilotCodeReviewPolicyInput`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `enterpriseId` (ID!): The ID of the enterprise whose policy to update.
* `policyState` (EnterpriseCopilotCodeReviewPolicyState!): The policy to set. Standalone enterprises cannot delegate to organization administrators.

## updateOrganizationCopilotCodeReviewPolicy - mutation

Updates an organization's Copilot code review policy when the enterprise delegates control to organization administrators.

### Input fields for `updateOrganizationCopilotCodeReviewPolicy`

* `input` (UpdateOrganizationCopilotCodeReviewPolicyInput!): 

### Return fields for `updateOrganizationCopilotCodeReviewPolicy`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `conflict` (OrganizationCopilotCodeReviewPolicyConflict): Why the policy was not updated. Null if the update succeeded.
* `policy` (OrganizationCopilotCodeReviewPolicy): The organization's current policy.

## UpdateOrganizationCopilotCodeReviewPolicyInput - input object

Autogenerated input type of UpdateOrganizationCopilotCodeReviewPolicy.

### Input fields for `UpdateOrganizationCopilotCodeReviewPolicyInput`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `organizationId` (ID!): The ID of the organization whose policy to update.
* `state` (OrganizationCopilotCodeReviewPolicyState!): The policy to set.

## updateOrganizationCopilotCodeReviewRunnerConfiguration - mutation

Sets the runner configuration that Copilot code review uses for an
organization. A LABELED runner requires at least one label or a runner group.
Invalid input does not change the configuration.

### Input fields for `updateOrganizationCopilotCodeReviewRunnerConfiguration`

* `input` (UpdateOrganizationCopilotCodeReviewRunnerConfigurationInput!): 

### Return fields for `updateOrganizationCopilotCodeReviewRunnerConfiguration`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `runnerConfiguration` (OrganizationCopilotCodeReviewRunnerConfiguration): The organization's updated runner configuration.

## UpdateOrganizationCopilotCodeReviewRunnerConfigurationInput - input object

Autogenerated input type of UpdateOrganizationCopilotCodeReviewRunnerConfiguration.

### Input fields for `UpdateOrganizationCopilotCodeReviewRunnerConfigurationInput`

* `allowRepositoryCustomization` (Boolean): Whether repositories can use their own runner configuration. When omitted, the current effective value is kept.
* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `organizationId` (ID!): The ID of the organization whose runner configuration to set.
* `runnerGroupName` (String): The runner group for a labeled runner.
* `runnerLabels` ([String!]): The runner labels for a labeled runner.
* `runnerType` (CopilotCodeReviewRunnerType!): The type of runner.

## updateOrganizationCopilotCodeReviewSettings - mutation

Updates an organization's Copilot code review settings. Omitted settings are not changed.

### Input fields for `updateOrganizationCopilotCodeReviewSettings`

* `input` (UpdateOrganizationCopilotCodeReviewSettingsInput!): 

### Return fields for `updateOrganizationCopilotCodeReviewSettings`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `conflict` (OrganizationCopilotCodeReviewSettingsConflict): Why the settings were not updated. Null if the update succeeded.
* `settings` (OrganizationCopilotCodeReviewSettings): The organization's current settings.

## UpdateOrganizationCopilotCodeReviewSettingsInput - input object

Autogenerated input type of UpdateOrganizationCopilotCodeReviewSettings.

### Input fields for `UpdateOrganizationCopilotCodeReviewSettingsInput`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `defaultReviewEffort` (OrganizationCopilotCodeReviewEffortSetting): The default review effort for repositories that do not choose their own. INHERIT clears the organization's value.
* `organizationId` (ID!): The ID of the organization whose settings to update.

## updateRepositoryCopilotCodeReviewSettings - mutation

Updates a repository's Copilot code review settings. Omitted settings are not changed.

### Input fields for `updateRepositoryCopilotCodeReviewSettings`

* `input` (UpdateRepositoryCopilotCodeReviewSettingsInput!): 

### Return fields for `updateRepositoryCopilotCodeReviewSettings`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `settings` (RepositoryCopilotCodeReviewSettings): The repository's current settings.

## UpdateRepositoryCopilotCodeReviewSettingsInput - input object

Autogenerated input type of UpdateRepositoryCopilotCodeReviewSettings.

### Input fields for `UpdateRepositoryCopilotCodeReviewSettingsInput`

* `clientMutationId` (String): A unique identifier for the client performing the mutation.
* `customInstructionsEnabled` (Boolean): Whether reviews use the repository's custom instructions.
* `mcpEnabled` (Boolean): Whether reviews can use MCP servers.
* `repositoryId` (ID!): The ID of the repository whose settings to update.
* `reviewEffort` (RepositoryCopilotCodeReviewEffortSetting): The review effort for the repository. INHERIT clears the repository's value.
* `severityFilter` (CopilotCodeReviewSeverityFilter): Which review comment severities Copilot code review leaves out.

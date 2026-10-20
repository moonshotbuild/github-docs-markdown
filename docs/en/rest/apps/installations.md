---
source_path: "/en/rest/apps/installations"
title: "REST API endpoints for GitHub App installations"
intro: "Use the REST API to get information about GitHub App installations and perform actions within those installations."
product: "REST API"
document_type: "article"
breadcrumbs:
  - title: "REST API"
    href: "/en/rest"
  - title: "Apps"
    href: "/en/rest/apps"
  - title: "Installations"
    href: "/en/rest/apps/installations"
---

# REST API endpoints for GitHub App installations

Use the REST API to get information about GitHub App installations and perform actions within those installations.

## About GitHub App installations

A GitHub App installation refers to the installation of the app on an organization or user account. For information on how to authenticate as an installation and limit access to specific repositories, see [Authenticating as a GitHub App installation](/en/apps/creating-github-apps/authenticating-with-a-github-app/authenticating-as-a-github-app-installation).

To list all GitHub App installations for an organization, see [REST API endpoints for organizations](/en/rest/orgs/orgs#list-app-installations-for-an-organization).

> \[!NOTE]
> Most endpoints use `Authorization: Bearer <YOUR-TOKEN>` and `Accept: application/vnd.github+json` headers, plus `X-GitHub-Api-Version: 2026-03-10`. Curl examples below omit these standard headers for brevity.

## List repositories accessible to the app installation

```
GET /installation/repositories
```

List repositories that an app installation can access.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`per_page`** (integer)
  The number of results per page (max 100). For more information, see "Using pagination in the REST API."
  Default: `30`

* **`page`** (integer)
  The page number of the results to fetch. For more information, see "Using pagination in the REST API."
  Default: `1`

### HTTP response status codes

* **200** - OK

* **304** - Not modified

* **401** - Requires authentication

* **403** - Forbidden

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/installation/repositories
```

**Response schema (Status: 200):**

* `total_count`: required, integer
* `repositories`: required, array of items:
  * all of:
    * **Repository**
      * `id`: required, integer, format: int64
      * `node_id`: required, string
      * `name`: required, string
      * `full_name`: required, string
      * `license`: required, any of:
        * **null**
        * **License Simple**
          * `key`: required, string
          * `name`: required, string
          * `url`: required, string or null, format: uri
          * `spdx_id`: required, string or null
          * `node_id`: required, string
          * `html_url`: string, format: uri
      * `forks`: required, integer
      * `permissions`: object:
        * `admin`: required, boolean
        * `pull`: required, boolean
        * `triage`: boolean
        * `push`: required, boolean
        * `maintain`: boolean
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
      * `private`: required, boolean, default: `false`
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
      * `git_url`: required, string
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
      * `ssh_url`: required, string
      * `stargazers_url`: required, string, format: uri
      * `statuses_url`: required, string
      * `subscribers_url`: required, string, format: uri
      * `subscription_url`: required, string, format: uri
      * `tags_url`: required, string, format: uri
      * `teams_url`: required, string, format: uri
      * `trees_url`: required, string
      * `clone_url`: required, string
      * `mirror_url`: required, string or null, format: uri
      * `hooks_url`: required, string, format: uri
      * `svn_url`: required, string, format: uri
      * `homepage`: required, string or null, format: uri
      * `language`: required, string or null
      * `forks_count`: required, integer
      * `stargazers_count`: required, integer
      * `watchers_count`: required, integer
      * `size`: required, integer
      * `default_branch`: required, string
      * `open_issues_count`: required, integer
      * `is_template`: boolean, default: `false`
      * `topics`: array of string
      * `has_issues`: required, boolean, default: `true`
      * `has_projects`: required, boolean, default: `true`
      * `has_wiki`: required, boolean, default: `true`
      * `has_pages`: required, boolean
      * `has_discussions`: boolean, default: `false`
      * `has_pull_requests`: boolean, default: `true`
      * `pull_request_creation_policy`: string, enum: `all`, `collaborators_only`
      * `archived`: required, boolean, default: `false`
      * `disabled`: required, boolean
      * `visibility`: string, default: `"public"`
      * `pushed_at`: required, string or null, format: date-time
      * `created_at`: required, string or null, format: date-time
      * `updated_at`: required, string or null, format: date-time
      * `allow_rebase_merge`: boolean, default: `true`
      * `temp_clone_token`: string
      * `allow_squash_merge`: boolean, default: `true`
      * `allow_auto_merge`: boolean, default: `false`
      * `delete_branch_on_merge`: boolean, default: `false`
      * `allow_update_branch`: boolean, default: `false`
      * `squash_merge_commit_title`: string, enum: `PR_TITLE`, `COMMIT_OR_PR_TITLE`
      * `squash_merge_commit_message`: string, enum: `PR_BODY`, `COMMIT_MESSAGES`, `BLANK`
      * `merge_commit_title`: string, enum: `PR_TITLE`, `MERGE_MESSAGE`
      * `merge_commit_message`: string, enum: `PR_BODY`, `PR_TITLE`, `BLANK`
      * `allow_merge_commit`: boolean, default: `true`
      * `allow_forking`: boolean
      * `web_commit_signoff_required`: boolean, default: `false`
      * `open_issues`: required, integer
      * `watchers`: required, integer
      * `starred_at`: string
      * `anonymous_access_enabled`: boolean
      * `code_search_index_status`: object:
        * `lexical_search_ok`: boolean
        * `lexical_commit_sha`: string
    * **object**
      * `custom_properties`: object, additional properties allowed
* `repository_selection`: string

## Revoke an installation access token

```
DELETE /installation/token
```

Revokes the installation token you're using to authenticate as an installation and access this endpoint.
Once an installation token is revoked, the token is invalidated and cannot be used. Other endpoints that require the revoked installation token must have a new installation token to work. You can create a new token using the "Create an installation access token for an app" endpoint.

### HTTP response status codes

* **204** - No Content

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/installation/token
```

**Response schema (Status: 204):**

## List app installations accessible to the user access token

```
GET /user/installations
```

Lists installations of your GitHub App that the authenticated user has explicit permission (:read, :write, or :admin) to access.
The authenticated user has explicit permission to access repositories they own, repositories where they are a collaborator, and repositories that they can access through an organization membership.
You can find the permissions for the installation under the permissions key.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`per_page`** (integer)
  The number of results per page (max 100). For more information, see "Using pagination in the REST API."
  Default: `30`

* **`page`** (integer)
  The page number of the results to fetch. For more information, see "Using pagination in the REST API."
  Default: `1`

### HTTP response status codes

* **200** - You can find the permissions for the installation under the permissions key.

* **304** - Not modified

* **401** - Requires authentication

* **403** - Forbidden

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/user/installations
```

**Response schema (Status: 200):**

* `total_count`: required, integer
* `installations`: required, array of `Installation`:
  * `id`: required, integer
  * `account`: required, any of:
    * **Simple User**
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
    * **Enterprise**
      * `description`: string or null
      * `html_url`: required, string, format: uri
      * `website_url`: string or null, format: uri
      * `id`: required, integer
      * `node_id`: required, string
      * `name`: required, string
      * `slug`: required, string
      * `created_at`: required, string or null, format: date-time
      * `updated_at`: required, string or null, format: date-time
      * `avatar_url`: required, string, format: uri
  * `repository_selection`: required, string, enum: `all`, `selected`
  * `access_tokens_url`: required, string, format: uri
  * `repositories_url`: required, string, format: uri
  * `html_url`: required, string, format: uri
  * `app_id`: required, integer
  * `client_id`: string
  * `target_id`: required, integer
  * `target_type`: required, string
  * `permissions`: required, `App Permissions`:
    * `actions`: string, enum: `read`, `write`
    * `administration`: string, enum: `read`, `write`
    * `artifact_metadata`: string, enum: `read`, `write`
    * `attestations`: string, enum: `read`, `write`
    * `checks`: string, enum: `read`, `write`
    * `code_quality`: string, enum: `read`, `write`
    * `codespaces`: string, enum: `read`, `write`
    * `contents`: string, enum: `read`, `write`
    * `dependabot_secrets`: string, enum: `read`, `write`
    * `deployments`: string, enum: `read`, `write`
    * `discussions`: string, enum: `read`, `write`
    * `environments`: string, enum: `read`, `write`
    * `issues`: string, enum: `read`, `write`
    * `merge_queues`: string, enum: `read`, `write`
    * `metadata`: string, enum: `read`, `write`
    * `packages`: string, enum: `read`, `write`
    * `pages`: string, enum: `read`, `write`
    * `pull_requests`: string, enum: `read`, `write`
    * `repository_custom_properties`: string, enum: `read`, `write`
    * `repository_hooks`: string, enum: `read`, `write`
    * `repository_projects`: string, enum: `read`, `write`, `admin`
    * `secret_scanning_alerts`: string, enum: `read`, `write`
    * `secrets`: string, enum: `read`, `write`
    * `security_events`: string, enum: `read`, `write`
    * `single_file`: string, enum: `read`, `write`
    * `statuses`: string, enum: `read`, `write`
    * `vulnerability_alerts`: string, enum: `read`, `write`
    * `workflows`: string, enum: `write`
    * `custom_properties_for_organizations`: string, enum: `read`, `write`
    * `members`: string, enum: `read`, `write`
    * `organization_administration`: string, enum: `read`, `write`
    * `organization_custom_roles`: string, enum: `read`, `write`
    * `organization_custom_org_roles`: string, enum: `read`, `write`
    * `organization_custom_properties`: string, enum: `read`, `write`, `admin`
    * `organization_copilot_seat_management`: string, enum: `read`, `write`
    * `organization_copilot_agent_settings`: string, enum: `read`, `write`
    * `organization_copilot_requests`: string, enum: `read`
    * `organization_external_properties_for_repos`: string, enum: `read`, `write`, `admin`
    * `organization_announcement_banners`: string, enum: `read`, `write`
    * `organization_events`: string, enum: `read`
    * `organization_hooks`: string, enum: `read`, `write`
    * `organization_personal_access_tokens`: string, enum: `read`, `write`
    * `organization_personal_access_token_requests`: string, enum: `read`, `write`
    * `organization_plan`: string, enum: `read`
    * `organization_projects`: string, enum: `read`, `write`, `admin`
    * `organization_packages`: string, enum: `read`, `write`
    * `organization_secrets`: string, enum: `read`, `write`
    * `organization_self_hosted_runners`: string, enum: `read`, `write`
    * `organization_user_blocking`: string, enum: `read`, `write`
    * `email_addresses`: string, enum: `read`, `write`
    * `followers`: string, enum: `read`, `write`
    * `git_ssh_keys`: string, enum: `read`, `write`
    * `gpg_keys`: string, enum: `read`, `write`
    * `interaction_limits`: string, enum: `read`, `write`
    * `profile`: string, enum: `write`
    * `starring`: string, enum: `read`, `write`
    * `enterprise_custom_properties_for_organizations`: string, enum: `read`, `write`, `admin`
  * `events`: required, array of string
  * `created_at`: required, string, format: date-time
  * `updated_at`: required, string, format: date-time
  * `single_file_name`: required, string or null
  * `has_multiple_single_files`: boolean
  * `single_file_paths`: array of string
  * `app_slug`: required, string
  * `suspended_by`: required, any of:
    * **null**
    * **Simple User** (see above)
  * `suspended_at`: required, string or null, format: date-time
  * `contact_email`: string or null

## List repositories accessible to the user access token

```
GET /user/installations/{installation_id}/repositories
```

List repositories that the authenticated user has explicit permission (:read, :write, or :admin) to access for an installation.
The authenticated user has explicit permission to access repositories they own, repositories where they are a collaborator, and repositories that they can access through an organization membership.
The access the user has to each repository is included in the hash under the permissions key.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`installation_id`** (integer) (required)
  The unique identifier of the installation.

* **`per_page`** (integer)
  The number of results per page (max 100). For more information, see "Using pagination in the REST API."
  Default: `30`

* **`page`** (integer)
  The page number of the results to fetch. For more information, see "Using pagination in the REST API."
  Default: `1`

### HTTP response status codes

* **200** - The access the user has to each repository is included in the hash under the permissions key.

* **304** - Not modified

* **403** - Forbidden

* **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X GET \
  https://api.github.com/user/installations/1/repositories
```

**Response schema (Status: 200):**

* `total_count`: required, integer
* `repository_selection`: string
* `repositories`: required, array of items:
  * all of:
    * **Repository**
      * `id`: required, integer, format: int64
      * `node_id`: required, string
      * `name`: required, string
      * `full_name`: required, string
      * `license`: required, any of:
        * **null**
        * **License Simple**
          * `key`: required, string
          * `name`: required, string
          * `url`: required, string or null, format: uri
          * `spdx_id`: required, string or null
          * `node_id`: required, string
          * `html_url`: string, format: uri
      * `forks`: required, integer
      * `permissions`: object:
        * `admin`: required, boolean
        * `pull`: required, boolean
        * `triage`: boolean
        * `push`: required, boolean
        * `maintain`: boolean
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
      * `private`: required, boolean, default: `false`
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
      * `git_url`: required, string
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
      * `ssh_url`: required, string
      * `stargazers_url`: required, string, format: uri
      * `statuses_url`: required, string
      * `subscribers_url`: required, string, format: uri
      * `subscription_url`: required, string, format: uri
      * `tags_url`: required, string, format: uri
      * `teams_url`: required, string, format: uri
      * `trees_url`: required, string
      * `clone_url`: required, string
      * `mirror_url`: required, string or null, format: uri
      * `hooks_url`: required, string, format: uri
      * `svn_url`: required, string, format: uri
      * `homepage`: required, string or null, format: uri
      * `language`: required, string or null
      * `forks_count`: required, integer
      * `stargazers_count`: required, integer
      * `watchers_count`: required, integer
      * `size`: required, integer
      * `default_branch`: required, string
      * `open_issues_count`: required, integer
      * `is_template`: boolean, default: `false`
      * `topics`: array of string
      * `has_issues`: required, boolean, default: `true`
      * `has_projects`: required, boolean, default: `true`
      * `has_wiki`: required, boolean, default: `true`
      * `has_pages`: required, boolean
      * `has_discussions`: boolean, default: `false`
      * `has_pull_requests`: boolean, default: `true`
      * `pull_request_creation_policy`: string, enum: `all`, `collaborators_only`
      * `archived`: required, boolean, default: `false`
      * `disabled`: required, boolean
      * `visibility`: string, default: `"public"`
      * `pushed_at`: required, string or null, format: date-time
      * `created_at`: required, string or null, format: date-time
      * `updated_at`: required, string or null, format: date-time
      * `allow_rebase_merge`: boolean, default: `true`
      * `temp_clone_token`: string
      * `allow_squash_merge`: boolean, default: `true`
      * `allow_auto_merge`: boolean, default: `false`
      * `delete_branch_on_merge`: boolean, default: `false`
      * `allow_update_branch`: boolean, default: `false`
      * `squash_merge_commit_title`: string, enum: `PR_TITLE`, `COMMIT_OR_PR_TITLE`
      * `squash_merge_commit_message`: string, enum: `PR_BODY`, `COMMIT_MESSAGES`, `BLANK`
      * `merge_commit_title`: string, enum: `PR_TITLE`, `MERGE_MESSAGE`
      * `merge_commit_message`: string, enum: `PR_BODY`, `PR_TITLE`, `BLANK`
      * `allow_merge_commit`: boolean, default: `true`
      * `allow_forking`: boolean
      * `web_commit_signoff_required`: boolean, default: `false`
      * `open_issues`: required, integer
      * `watchers`: required, integer
      * `starred_at`: string
      * `anonymous_access_enabled`: boolean
      * `code_search_index_status`: object:
        * `lexical_search_ok`: boolean
        * `lexical_commit_sha`: string
    * **object**
      * `custom_properties`: object, additional properties allowed

## Add a repository to an app installation

```
PUT /user/installations/{installation_id}/repositories/{repository_id}
```

Add a single repository to an installation. The authenticated user must have admin access to the repository.

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`installation_id`** (integer) (required)
  The unique identifier of the installation.

* **`repository_id`** (integer) (required)
  The unique identifier of the repository.

### HTTP response status codes

* **204** - No Content

* **304** - Not modified

* **403** - Forbidden

* **404** - Resource not found

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X PUT \
  https://api.github.com/user/installations/1/repositories/REPOSITORY_ID
```

**Response schema (Status: 204):**

## Remove a repository from an app installation

```
DELETE /user/installations/{installation_id}/repositories/{repository_id}
```

Remove a single repository from an installation. The authenticated user must have admin access to the repository. The installation must have the repository\_selection of selected.
To use a PAT (classic) with this endpoint, the repo scope is required

### Parameters

#### Headers

* **`accept`** (string)
  Setting to `application/vnd.github+json` is recommended.

#### Path and query parameters

* **`installation_id`** (integer) (required)
  The unique identifier of the installation.

* **`repository_id`** (integer) (required)
  The unique identifier of the repository.

### HTTP response status codes

* **204** - No Content

* **304** - Not modified

* **403** - Forbidden

* **404** - Resource not found

* **422** - Returned when the application is installed on all repositories in the organization, or if this request would remove the last repository that the application has access to in the organization.

### Code examples

#### Example

**Request:**

```curl
curl -L \
  -X DELETE \
  https://api.github.com/user/installations/1/repositories/REPOSITORY_ID
```

**Response schema (Status: 204):**

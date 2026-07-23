---
source_path: "/en/code-security/concepts/secret-security/delegated-bypass"
title: "Delegated bypass for push protection"
intro: "Maintain your secret security while unblocking trusted actors with delegated bypass for push protection."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Concepts"
    href: "/en/code-security/concepts"
  - title: "Secret security"
    href: "/en/code-security/concepts/secret-security"
  - title: "Delegated bypass"
    href: "/en/code-security/concepts/secret-security/delegated-bypass"
---

# Delegated bypass for push protection

Maintain your secret security while unblocking trusted actors with delegated bypass for push protection.

## About delegated bypass for push protection

With delegated bypass for push protection, you can:

* **Grant bypass permissions** to select individuals, roles, and teams, allowing them to push commits that are initially blocked by push protection.
* **Grant exemptions** to select actors, skipping push protection entirely for all of their commits. Exemptions should be granted to trusted automation like migration bots or service accounts that need to push frequent commits with minimal friction.
* **Introduce a review cycle** for bypass requests from all other contributors. Requests expire after 7 days.

Delegated bypass applies to files created, edited, and uploaded on GitHub.

## Users with bypass privileges

The following types of users can always bypass push protection:

* Organization owners
* Security managers
* Users in teams, default roles, or custom roles that have been added to the bypass list
* Users who are assigned (either directly or via a team) a custom role with the "review and manage secret scanning bypass requests" fine-grained permission

## Next steps

To start managing bypass privileges, see [Enabling delegated bypass for push protection](/en/code-security/how-tos/secure-your-secrets/manage-bypass-requests/enable-delegated-bypass).

---
source_path: "/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/code-scanning-at-scale"
title: "Configuring default setup for code scanning at scale"
intro: "You can quickly configure code scanning for repositories across your organization using default setup."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Secure at scale"
    href: "/en/code-security/how-tos/secure-at-scale"
  - title: "Configure organization security"
    href: "/en/code-security/how-tos/secure-at-scale/configure-organization-security"
  - title: "Configure specific tools"
    href: "/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools"
  - title: "Code scanning at scale"
    href: "/en/code-security/how-tos/secure-at-scale/configure-organization-security/configure-specific-tools/code-scanning-at-scale"
---

# Configuring default setup for code scanning at scale

You can quickly configure code scanning for repositories across your organization using default setup.

With default setup for code scanning, you can quickly secure code in repositories across your organization. For more information, see [About setup types for code scanning](/en/code-security/concepts/code-scanning/setup-types).

For repositories that are not suitable for default setup, you can configure advanced setup at the repository level, or at the organization level using a script.

## Prerequisites

A repository must meet all the following criteria to be eligible for default setup:

* Advanced setup for code scanning is not already enabled.
* GitHub Actions is enabled.
* It is publicly visible, or GitHub Code Security is enabled.

## Configuring default setup for all eligible repositories in an organization

You can enable default setup for all eligible repositories in your organization. For more information, see [Enabling security features at scale](/en/code-security/concepts/security-at-scale/organization-security).

### Configuring default setup features

Through your organization's security settings page, you can customize default setup for all eligible repositories, such as extending coverage using model packs. See [Editing your configuration of default setup](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/edit-default-setup).

## Configuring default setup for a subset of repositories in an organization

You can filter for specific repositories you would like to configure default setup for. For more information, see [Applying a custom security configuration](/en/code-security/how-tos/secure-at-scale/configure-organization-security/establish-complete-coverage/apply-custom-configuration).

## Providing default setup access to private registries

When a repository uses code stored in a private registry, default setup needs access to the registry to work effectively. For more information, see [Giving security features access to private registries](/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries).

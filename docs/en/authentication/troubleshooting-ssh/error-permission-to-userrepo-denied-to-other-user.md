---
source_path: "/en/authentication/troubleshooting-ssh/error-permission-to-userrepo-denied-to-other-user"
title: "Error: Permission to user/repo denied to other-user"
intro: "This error means the key you are pushing with is attached to an account which does not have access to the repository."
product: "Authentication"
document_type: "article"
breadcrumbs:
  - title: "Authentication"
    href: "/en/authentication"
  - title: "Troubleshooting SSH"
    href: "/en/authentication/troubleshooting-ssh"
  - title: "Permission denied other-user"
    href: "/en/authentication/troubleshooting-ssh/error-permission-to-userrepo-denied-to-other-user"
---

# Error: Permission to user/repo denied to other-user

This error means the key you are pushing with is attached to an account which does not have access to the repository.

To fix this, the owner of the repository (`user`) needs to add your account (`other-user`) as a collaborator on the repository or to a team that has write access to the repository.

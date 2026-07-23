---
source_path: "/en/authentication/managing-commit-signature-verification"
title: "Managing commit signature verification"
intro: "GitHub will verify GPG, SSH, or S/MIME signatures so other people will know that your commits come from a trusted source. GitHub will automatically sign commits you make using the web interface."
product: "Authentication"
document_type: "category"
breadcrumbs:
  - title: "Authentication"
    href: "/en/authentication"
  - title: "Verify commit signatures"
    href: "/en/authentication/managing-commit-signature-verification"
---

# Managing commit signature verification

GitHub will verify GPG, SSH, or S/MIME signatures so other people will know that your commits come from a trusted source.

## Links

### Sign your commits with GPG

* [About commit signature verification](/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)

  Using GPG, SSH, or S/MIME, you can sign tags and commits locally. These tags or commits are marked as verified on GitHub so other people can be confident that the changes come from a trusted source.

* [Checking for existing GPG keys](/en/authentication/managing-commit-signature-verification/checking-for-existing-gpg-keys)

  Before you generate a GPG key, you can check to see if you have any existing GPG keys.

* [Generating a new GPG key](/en/authentication/managing-commit-signature-verification/generating-a-new-gpg-key)

  If you don't have an existing GPG key, you can generate a new GPG key to use for signing commits and tags.

* [Adding a GPG key to your GitHub account](/en/authentication/managing-commit-signature-verification/adding-a-gpg-key-to-your-github-account)

  To configure your account on GitHub to use your new (or existing) GPG key, you'll also need to add the key to your account.

* [Telling Git about your signing key](/en/authentication/managing-commit-signature-verification/telling-git-about-your-signing-key)

  To sign commits locally, you need to inform Git that there's a GPG, SSH, or X.509 key you'd like to use.

* [Associating an email with your GPG key](/en/authentication/managing-commit-signature-verification/associating-an-email-with-your-gpg-key)

  Your GPG key must be associated with a verified email that matches your committer identity.

* [Signing commits](/en/authentication/managing-commit-signature-verification/signing-commits)

  You can sign commits locally using GPG, SSH, or S/MIME.

---
source_path: "/en/authentication/troubleshooting-commit-signature-verification/using-a-verified-email-address-in-your-gpg-key"
title: "Using a verified email address in your GPG key"
intro: "When verifying a signature, GitHub checks that the committer or tagger email address matches an email address from the GPG key's identities and is a verified email address on the user's account. This ensures that the key belongs to you and that you created the commit or tag."
product: "Authentication"
document_type: "article"
breadcrumbs:
  - title: "Authentication"
    href: "/en/authentication"
  - title: "Troubleshoot verification"
    href: "/en/authentication/troubleshooting-commit-signature-verification"
  - title: "Use verified email in GPG key"
    href: "/en/authentication/troubleshooting-commit-signature-verification/using-a-verified-email-address-in-your-gpg-key"
---

# Using a verified email address in your GPG key

When verifying a signature, GitHub checks that the committer or tagger email address matches an email address from the GPG key's identities and is a verified email address on the user's account. This ensures that the key belongs to you and that you created the commit or tag.

If you need to verify your GitHub email address, see [Verifying your email address](/en/account-and-profile/how-tos/email-preferences/verifying-your-email-address).  If you need to update or add an email address to your GPG key, see [Associating an email with your GPG key](/en/authentication/managing-commit-signature-verification/associating-an-email-with-your-gpg-key).

Commits and tags may contain several email addresses. For commits, there is the author — the person who wrote the code — and the committer — the person who added the commit to the tree. When signing a commit with Git, whether it be during a merge, cherry-pick, or normal `git commit`, the committer email address will be yours, even if the author email address isn't. Tags are more simple: The tagger email address is always the user who created the tag.

If you need to change your committer or tagger email address, see [Setting your commit email address](/en/account-and-profile/how-tos/email-preferences/setting-your-commit-email-address).

## Further reading

* [About commit signature verification](/en/authentication/managing-commit-signature-verification/about-commit-signature-verification)

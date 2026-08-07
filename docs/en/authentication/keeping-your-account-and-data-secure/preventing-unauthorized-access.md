---
source_path: "/en/authentication/keeping-your-account-and-data-secure/preventing-unauthorized-access"
title: "Preventing unauthorized access"
intro: "You may be alerted to a security incident in the media, such as the discovery of the Heartbleed bug, or your computer could be stolen while you're signed in to GitHub. In such cases, changing your password prevents any unintended future access to your account and projects."
product: "Authentication"
document_type: "article"
breadcrumbs:
  - title: "Authentication"
    href: "/en/authentication"
  - title: "Account security"
    href: "/en/authentication/keeping-your-account-and-data-secure"
  - title: "Unauthorized access"
    href: "/en/authentication/keeping-your-account-and-data-secure/preventing-unauthorized-access"
---

# Preventing unauthorized access

You may be alerted to a security incident in the media, such as the discovery of the Heartbleed bug, or your computer could be stolen while you're signed in to GitHub. In such cases, changing your password prevents any unintended future access to your account and projects.

GitHub requires a password to perform sensitive actions, such as adding new SSH keys, authorizing applications, or modifying team members.

After changing your password, you should perform these actions to make sure that your account is secure:

* Enable two-factor authentication on your account so that access requires more than just a password. For more information, see [About two-factor authentication](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/about-two-factor-authentication).

* Add a passkey to your account to enable a secure, passwordless login. Passkeys are phishing-resistant, and they don't require memorization or active management. See [About passkeys](/en/authentication/authenticating-with-a-passkey/about-passkeys).

* Review your SSH keys, deploy keys, and authorized OAuth apps and GitHub Apps and revoke unauthorized or unfamiliar access in your SSH and Applications settings. For more information, see [Reviewing your SSH keys](/en/authentication/keeping-your-account-and-data-secure/reviewing-your-ssh-keys), [Reviewing your deploy keys](/en/authentication/keeping-your-account-and-data-secure/reviewing-your-deploy-keys), [Reviewing your authorized OAuth apps](/en/apps/oauth-apps/using-oauth-apps/reviewing-your-authorized-oauth-apps), and [Reviewing and revoking authorization of GitHub Apps](/en/apps/using-github-apps/reviewing-and-revoking-authorization-of-github-apps).

* If you believe your account may be compromised, you can revoke all your authorizations or delete all your credentials at once. See [Revoking your credentials](/en/authentication/keeping-your-account-and-data-secure/revoking-your-credentials).

* Verify all your email addresses. If an attacker added their email address to your account, it could allow them to force an unintended password reset. For more information, see [Verifying your email address](/en/account-and-profile/how-tos/email-preferences/verifying-your-email-address).

* Review your account's security log. This provides an overview on various configurations made to your repositories. For example, you can ensure that no private repositories were turned public, or that no repositories were transferred. For more information, see [Reviewing your security log](/en/authentication/keeping-your-account-and-data-secure/reviewing-your-security-log).

* Review the webhooks on your repositories. Webhooks could allow an attacker to intercept pushes made to your repository. For more information, see [About webhooks](/en/webhooks/about-webhooks).

* Make sure that no new deploy keys were created. This could enable outside servers access to your projects. For more information, see [Managing deploy keys](/en/authentication/connecting-to-github-with-ssh/managing-deploy-keys#deploy-keys).

* Review recent commits made to your repositories.

* Review the list of collaborators for each repository.

## Troubleshooting

### Account is restricted after suspected compromise

If GitHub detects suspicious activity, your personal account may be temporarily restricted while you can still sign in. During this time, your profile URL, contribution graph, search visibility, or sensitive account actions may be unavailable. Alternatively, we may suspend the account for security reasons. If you’re unable to access your account at all, please contact GitHub Support.

If you see restrictions on your account, complete the following steps to secure your account:

1. Change your GitHub password. For more information, see [Updating your GitHub access credentials](/en/authentication/keeping-your-account-and-data-secure/updating-your-github-access-credentials#changing-an-existing-password).
2. Review your security settings and remove unfamiliar apps, keys, and other credentials.
3. Secure the email account associated with GitHub and make sure you can access it.
4. Check your inbox (and spam folder) for security emails from GitHub and follow any instructions.

If restrictions remain after you secure your account, contact GitHub Support.

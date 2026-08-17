---
source_path: "/en/authentication"
title: "Authentication documentation"
intro: "Authenticate securely to GitHub with passwords, tokens, SSH keys, and more—and keep your account protected."
product: "Authentication"
document_type: "product"
breadcrumbs:
  - title: "Authentication"
    href: "/en/authentication"
---

# Authentication documentation

Authenticate securely to GitHub with passwords, tokens, SSH keys, and more—and keep your account protected.

## Recommended

* [About authentication to GitHub](/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github)

  You can securely access your account's resources by authenticating to GitHub, using different credentials depending on where you authenticate.

* [Connecting to GitHub with SSH](/en/authentication/connecting-to-github-with-ssh)

  You can connect to GitHub using the Secure Shell Protocol (SSH), which provides a secure channel over an unsecured network.

* [Managing commit signature verification](/en/authentication/managing-commit-signature-verification)

  GitHub will verify GPG, SSH, or S/MIME signatures so other people will know that your commits come from a trusted source.

* [Configuring two-factor authentication](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)

  You can choose among multiple options to add a second source of authentication to your account.

* [Signing in with a passkey](/en/authentication/authenticating-with-a-passkey/signing-in-with-a-passkey)

  You can use a passkey to sign in safely and easily to GitHub in your browser, without requiring a password and two-factor authentication. You can also sign in using a passkey on a nearby device.

* [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

  You can use a personal access token in place of a password when authenticating to GitHub in the command line or with the API.

* [Removing sensitive data from a repository](/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)

  Sensitive data can be removed from the history of a repository if you can carefully coordinate with everyone who has cloned it and you are willing to manage the side effects.

* [Recovering your account if you lose your 2FA credentials](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/recovering-your-account-if-you-lose-your-2fa-credentials)

  If you lose access to your two-factor authentication credentials, you can use your recovery codes, or another recovery option, to regain access to your account.

* [Error: Permission denied (publickey)](/en/authentication/troubleshooting-ssh/error-permission-denied-publickey)

  A "Permission denied" error means that the server rejected your connection. There could be several reasons why, and the most common examples are explained below.

## Links

### Getting started

* [About authentication to GitHub](/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github)

  You can securely access your account's resources by authenticating to GitHub, using different credentials depending on where you authenticate.

## Articles

* [About authentication to GitHub](/en/authentication/keeping-your-account-and-data-secure/about-authentication-to-github)

  You can securely access your account's resources by authenticating to GitHub, using different credentials depending on where you authenticate.

* [Creating a strong password](/en/authentication/keeping-your-account-and-data-secure/creating-a-strong-password)

  Secure your account on GitHub with a strong and unique password using a password manager.

* [Switching between accounts](/en/authentication/keeping-your-account-and-data-secure/switching-between-accounts)

  Learn how to switch between multiple accounts.

* [Verifying new devices when signing in](/en/authentication/keeping-your-account-and-data-secure/verifying-new-devices-when-signing-in)

  When you sign in for the first time from a new or unrecognized device without two-factor authentication enabled, GitHub may ask for additional verification to confirm that it is you.

* [Updating your GitHub access credentials](/en/authentication/keeping-your-account-and-data-secure/updating-your-github-access-credentials)

  GitHub credentials include your password, access tokens, SSH keys, and application API tokens used to communicate with GitHub. You can reset all of these access credentials yourself.

* [Managing your personal access tokens](/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens)

  You can use a personal access token in place of a password when authenticating to GitHub in the command line or with the API.

* [Reviewing your SSH keys](/en/authentication/keeping-your-account-and-data-secure/reviewing-your-ssh-keys)

  To keep your credentials secure, you should regularly audit your SSH keys, deploy keys, and review authorized applications that access your account.

* [Reviewing your deploy keys](/en/authentication/keeping-your-account-and-data-secure/reviewing-your-deploy-keys)

  You should review deploy keys to ensure that there aren't any unauthorized (or possibly compromised) keys. You can also approve existing deploy keys that are valid.

* [Token expiration and revocation](/en/authentication/keeping-your-account-and-data-secure/token-expiration-and-revocation)

  Your tokens can expire and can also be revoked by you, applications you have authorized, and GitHub itself.

* [Revoking your credentials](/en/authentication/keeping-your-account-and-data-secure/revoking-your-credentials)

  If you believe your account credentials may be compromised, you can revoke all your authorizations to protect any enterprises you have access to. If you are a member of an enterprise with managed users, you can also choose to delete all your credentials.

* [Reviewing your security log](/en/authentication/keeping-your-account-and-data-secure/reviewing-your-security-log)

  You can review the security log for your personal account to better understand actions you've performed and actions others have performed that involve you.

* [Security log events](/en/authentication/keeping-your-account-and-data-secure/security-log-events)

  Learn about security log events recorded for your personal account.

* [Removing sensitive data from a repository](/en/authentication/keeping-your-account-and-data-secure/removing-sensitive-data-from-a-repository)

  Sensitive data can be removed from the history of a repository *if* you can carefully coordinate with everyone who has cloned it and you are willing to manage the side effects.

* [About anonymized URLs](/en/authentication/keeping-your-account-and-data-secure/about-anonymized-urls)

  If you upload an image or video to GitHub, the URL of the image or video will be modified so your information is not trackable.

* [About GitHub's IP addresses](/en/authentication/keeping-your-account-and-data-secure/about-githubs-ip-addresses)

  GitHub serves applications from multiple IP address ranges, which are available using the API.

* [GitHub's SSH key fingerprints](/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints)

  Public key fingerprints can be used to validate a connection to a remote server.

* [Sudo mode](/en/authentication/keeping-your-account-and-data-secure/sudo-mode)

  To confirm access to your account before you perform a potentially sensitive action, GitHub.com prompts for authentication.

* [Preventing unauthorized access](/en/authentication/keeping-your-account-and-data-secure/preventing-unauthorized-access)

  You may be alerted to a security incident in the media, such as the discovery of the [Heartbleed bug](http://heartbleed.com/), or your computer could be stolen while you're signed in to GitHub. In such cases, changing your password prevents any unintended future access to your account and projects.

* [Viewing and managing your sessions](/en/authentication/keeping-your-account-and-data-secure/viewing-and-managing-your-sessions)

  You can view and revoke your active sessions in your settings.

* [About two-factor authentication](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/about-two-factor-authentication)

  Two-factor authentication (2FA) is an extra layer of security used when logging into websites or apps. With 2FA, you have to log in with your username and password and provide another form of authentication that only you know or have access to.

* [About mandatory two-factor authentication](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/about-mandatory-two-factor-authentication)

  Enable mandatory two-factor authentication to secure your account and maintain access to GitHub.com.

* [Configuring two-factor authentication](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication)

  You can choose among multiple options to add a second source of authentication to your account.

* [Configuring two-factor authentication recovery methods](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/configuring-two-factor-authentication-recovery-methods)

  You can set up a variety of recovery methods to access your account if you lose your two-factor authentication credentials.

* [Accessing GitHub using two-factor authentication](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/accessing-github-using-two-factor-authentication)

  With 2FA enabled, you'll be asked to provide your 2FA authentication code, as well as your password, when you sign in to GitHub.

* [Countries where SMS authentication is supported](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/countries-where-sms-authentication-is-supported)

  Because of delivery success rates, GitHub only supports two-factor authentication via SMS for certain countries.

* [Changing your two-factor authentication method](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/changing-your-two-factor-authentication-method)

  You can change your two-factor authentication (2FA) method without disabling 2FA entirely.

* [Troubleshooting two-factor authentication issues](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/troubleshooting-two-factor-authentication-issues)

  If you are having trouble authenticating with 2FA, you can try troubleshooting your configured authentication methods.

* [Recovering your account if you lose your 2FA credentials](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/recovering-your-account-if-you-lose-your-2fa-credentials)

  If you lose access to your two-factor authentication credentials, you can use your recovery codes, or another recovery option, to regain access to your account.

* [Disabling two-factor authentication for your personal account](/en/authentication/securing-your-account-with-two-factor-authentication-2fa/disabling-two-factor-authentication-for-your-personal-account)

  If you disable two-factor authentication for your personal account, you may lose access to organizations you belong to.

* [About passkeys](/en/authentication/authenticating-with-a-passkey/about-passkeys)

  Passkeys allow you to sign in safely and easily, without requiring a password and two-factor authentication.

* [Managing your passkeys](/en/authentication/authenticating-with-a-passkey/managing-your-passkeys)

  You may be prompted to register a passkey during sign-in, or you can choose to register a new passkey in your account settings. For 2FA users, you can upgrade existing eligible security keys into passkeys.

* [Signing in with a passkey](/en/authentication/authenticating-with-a-passkey/signing-in-with-a-passkey)

  You can use a passkey to sign in safely and easily to GitHub in your browser, without requiring a password and two-factor authentication. You can also sign in using a passkey on a nearby device.

* [Authenticating with single sign-on](/en/authenticating-with-single-sign-on)

  You can authenticate to GitHub with single sign-on (SSO) and view your active sessions.

* [About SSH](/en/authentication/connecting-to-github-with-ssh/about-ssh)

  Using the SSH protocol, you can connect and authenticate to remote servers and services. With SSH keys, you can connect to GitHub without supplying your username and personal access token at each visit. You can also use an SSH key to sign commits.

* [Checking for existing SSH keys](/en/authentication/connecting-to-github-with-ssh/checking-for-existing-ssh-keys)

  Before you generate an SSH key, you can check to see if you have any existing SSH keys.

* [Generating a new SSH key and adding it to the ssh-agent](/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

  After you've checked for existing SSH keys, you can generate a new SSH key to use for authentication, then add it to the ssh-agent.

* [Adding a new SSH key to your GitHub account](/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)

  To configure your account on GitHub.com to use your new (or existing) SSH key, you'll also need to add the key to your account.

* [Testing your SSH connection](/en/authentication/connecting-to-github-with-ssh/testing-your-ssh-connection)

  After you've set up your SSH key and added it to GitHub, you can test your connection.

* [Working with SSH key passphrases](/en/authentication/connecting-to-github-with-ssh/working-with-ssh-key-passphrases)

  You can secure your SSH keys and configure an authentication agent so that you won't have to reenter your passphrase every time you use your SSH keys.

* [Using SSH agent forwarding](/en/authentication/connecting-to-github-with-ssh/using-ssh-agent-forwarding)

  To simplify deploying to a server, you can set up SSH agent forwarding to securely use local SSH keys.

* [Managing deploy keys](/en/authentication/connecting-to-github-with-ssh/managing-deploy-keys)

  Learn different ways to manage SSH keys on your servers when you automate deployment scripts and which way is best for you.

* [Using SSH over the HTTPS port](/en/authentication/troubleshooting-ssh/using-ssh-over-the-https-port)

  Sometimes, firewalls refuse to allow SSH connections entirely. If using HTTPS cloning with credential caching is not an option, you can attempt to clone using an SSH connection made over the HTTPS port. Most firewall rules should allow this, but proxy servers may interfere.

* [Recovering your SSH key passphrase](/en/authentication/troubleshooting-ssh/recovering-your-ssh-key-passphrase)

  If you've lost your SSH key passphrase, depending on the operating system you use, you may either recover it or you may need to generate a new SSH key passphrase.

* [Deleted or missing SSH keys](/en/authentication/troubleshooting-ssh/deleted-or-missing-ssh-keys)

  As a security precaution, GitHub automatically deletes SSH keys that haven't been used in a year.

* [Error: Host key verification failed](/en/authentication/troubleshooting-ssh/error-host-key-verification-failed)

  As a security precaution, SSH keeps track of which hosts it has previously seen.

* [Error: Permission denied (publickey)](/en/authentication/troubleshooting-ssh/error-permission-denied-publickey)

  A "Permission denied" error means that the server rejected your connection. There could be several reasons why, and the most common examples are explained below.

* [Error: Bad file number](/en/authentication/troubleshooting-ssh/error-bad-file-number)

  This error usually means you were unable to connect to the server. Often this is caused by firewalls and proxy servers.

* [Error: Key already in use](/en/authentication/troubleshooting-ssh/error-key-already-in-use)

  This error occurs when you try to add a key that's already been added to another account or repository.

* [Error: Permission to user/repo denied to other-user](/en/authentication/troubleshooting-ssh/error-permission-to-userrepo-denied-to-other-user)

  This error means the key you are pushing with is attached to an account which does not have access to the repository.

* [Error: Permission to user/repo denied to user/other-repo](/en/authentication/troubleshooting-ssh/error-permission-to-userrepo-denied-to-userother-repo)

  This error means the key you are pushing with is attached to another repository as a deploy key, and does not have access to the repository you are trying to push to.

* [Error: Agent admitted failure to sign](/en/authentication/troubleshooting-ssh/error-agent-admitted-failure-to-sign)

  In rare circumstances, connecting to GitHub via SSH on Linux produces the error `"Agent admitted failure to sign using the key"`. Follow these steps to resolve the problem.

* [Error: ssh-add: illegal option -- apple-use-keychain](/en/authentication/troubleshooting-ssh/error-ssh-add-illegal-option----apple-use-keychain)

  This error means your version of `ssh-add` does not support macOS keychain integration, which allows you to store your passphrase in the keychain.

* [Error: SSL certificate problem, verify that the CA cert is OK](/en/authentication/troubleshooting-ssh/error-ssl-certificate-problem-verify-that-the-ca-cert-is-ok)

  This error means your CA root certificate is out of date. If your CA root certificate needs to be updated, you won't be able to push or pull from GitHub repositories.

* [Error: Unknown key type](/en/authentication/troubleshooting-ssh/error-unknown-key-type)

  This error means that the SSH key type you used was unrecognized or is unsupported by your SSH client.

* [Error: We're doing an SSH key audit](/en/authentication/troubleshooting-ssh/error-were-doing-an-ssh-key-audit)

  This error means the SSH key you're using to perform a Git operation is unverified.

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

* [Signing tags](/en/authentication/managing-commit-signature-verification/signing-tags)

  You can sign tags locally using GPG, SSH, or S/MIME.

* [Displaying verification statuses for all of your commits](/en/authentication/managing-commit-signature-verification/displaying-verification-statuses-for-all-of-your-commits)

  You can enable vigilant mode for commit signature verification to mark all of your commits and tags with a signature verification status.

* [Checking your commit and tag signature verification status](/en/authentication/troubleshooting-commit-signature-verification/checking-your-commit-and-tag-signature-verification-status)

  You can check the verification status of your commit and tag signatures on GitHub.

* [Using a verified email address in your GPG key](/en/authentication/troubleshooting-commit-signature-verification/using-a-verified-email-address-in-your-gpg-key)

  When verifying a signature, GitHub checks that the committer or tagger email address matches an email address from the GPG key's identities and is a verified email address on the user's account. This ensures that the key belongs to you and that you created the commit or tag.

---
source_path: "/en/authentication/troubleshooting-ssh"
title: "Troubleshooting SSH"
intro: "When using SSH to connect and authenticate to GitHub, you may need to troubleshoot unexpected issues that may arise."
product: "Authentication"
document_type: "category"
breadcrumbs:
  - title: "Authentication"
    href: "/en/authentication"
  - title: "Troubleshooting SSH"
    href: "/en/authentication/troubleshooting-ssh"
---

# Troubleshooting SSH

When using SSH to connect and authenticate to GitHub, you may need to troubleshoot unexpected issues that may arise.

## Links

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

  In rare circumstances, connecting to GitHub via SSH on Linux produces the error "Agent admitted failure to sign using the key". Follow these steps to resolve the problem.

* [Error: ssh-add: illegal option -- apple-use-keychain](/en/authentication/troubleshooting-ssh/error-ssh-add-illegal-option----apple-use-keychain)

  This error means your version of ssh-add does not support macOS keychain integration, which allows you to store your passphrase in the keychain.

* [Error: SSL certificate problem, verify that the CA cert is OK](/en/authentication/troubleshooting-ssh/error-ssl-certificate-problem-verify-that-the-ca-cert-is-ok)

  This error means your CA root certificate is out of date. If your CA root certificate needs to be updated, you won't be able to push or pull from GitHub repositories.

* [Error: Unknown key type](/en/authentication/troubleshooting-ssh/error-unknown-key-type)

  This error means that the SSH key type you used was unrecognized or is unsupported by your SSH client.

* [Error: We're doing an SSH key audit](/en/authentication/troubleshooting-ssh/error-were-doing-an-ssh-key-audit)

  This error means the SSH key you're using to perform a Git operation is unverified.

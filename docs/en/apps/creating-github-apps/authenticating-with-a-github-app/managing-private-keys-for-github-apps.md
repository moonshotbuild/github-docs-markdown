---
source_path: "/en/apps/creating-github-apps/authenticating-with-a-github-app/managing-private-keys-for-github-apps"
title: "Managing private keys for GitHub Apps"
intro: "You can manage private keys to authenticate with your GitHub App."
product: "Apps"
document_type: "article"
breadcrumbs:
  - title: "Apps"
    href: "/en/apps"
  - title: "Creating GitHub Apps"
    href: "/en/apps/creating-github-apps"
  - title: "Authenticate with a GitHub App"
    href: "/en/apps/creating-github-apps/authenticating-with-a-github-app"
  - title: "Manage private keys"
    href: "/en/apps/creating-github-apps/authenticating-with-a-github-app/managing-private-keys-for-github-apps"
---

# Managing private keys for GitHub Apps

You can manage private keys to authenticate with your GitHub App.

## About private keys for GitHub Apps

After you create a GitHub App, you'll need to generate a private key in order to make requests to the GitHub API as the application itself. For example, you need a private key to sign a JSON Web Token (JWT) in order to request an installation access token. For more information, see [Generating a JSON Web Token (JWT) for a GitHub App](/en/apps/creating-github-apps/authenticating-with-a-github-app/generating-a-json-web-token-jwt-for-a-github-app)

You can create up to 25 private keys for an app. You should use multiple keys in order to rotate keys without downtime in the event of a key compromise. If your application has 25 or more keys, you must delete some before you can create more.

Private keys do not expire and instead need to be manually revoked. For more information about how to revoke or delete a private key, see [Deleting private keys](#deleting-private-keys).

You must keep private keys for GitHub Apps secure. For more information, see [Storing private keys](#storing-private-keys).

To verify that a private key matches a public key, see [Verifying private keys](#verifying-private-keys).

## Generating private keys

To generate a private key:

1. In the upper-right corner of any page on GitHub, click your profile picture.

2. Navigate to your account settings.
   * For an app owned by a personal account, click **Settings**.
   * For an app owned by an organization:
     1. Click **Your organizations**.
     2. To the right of the organization, click **Settings**.

3. In the left sidebar, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-code" aria-label="code" role="img"><path d="m11.28 3.22 4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734L13.94 8l-3.72-3.72a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215Zm-6.56 0a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L2.06 8l3.72 3.72a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L.47 8.53a.75.75 0 0 1 0-1.06Z"></path></svg> Developer settings**.

4. In the left sidebar, click **GitHub Apps**.

5. Next to the GitHub App that you want to generate a private key for, click **Edit**.

6. In the left sidebar, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-key" aria-label="code" role="img"><path d="M10.5 0a5.499 5.499 0 1 1-1.288 10.848l-.932.932a.749.749 0 0 1-.53.22H7v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22H5v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22h-2A1.75 1.75 0 0 1 0 14.25v-2c0-.199.079-.389.22-.53l4.932-4.932A5.5 5.5 0 0 1 10.5 0Zm-4 5.5c-.001.431.069.86.205 1.269a.75.75 0 0 1-.181.768L1.5 12.56v1.69c0 .138.112.25.25.25h1.69l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l1.023-1.025a.75.75 0 0 1 .768-.18A4 4 0 1 0 6.5 5.5ZM11 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path></svg> Credentials**, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-key" aria-label="code" role="img"><path d="M10.5 0a5.499 5.499 0 1 1-1.288 10.848l-.932.932a.749.749 0 0 1-.53.22H7v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22H5v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22h-2A1.75 1.75 0 0 1 0 14.25v-2c0-.199.079-.389.22-.53l4.932-4.932A5.5 5.5 0 0 1 10.5 0Zm-4 5.5c-.001.431.069.86.205 1.269a.75.75 0 0 1-.181.768L1.5 12.56v1.69c0 .138.112.25.25.25h1.69l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l1.023-1.025a.75.75 0 0 1 .768-.18A4 4 0 1 0 6.5 5.5ZM11 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path></svg> Key pairs**.

7. Click **New key**.

8. You will see a private key in PEM format downloaded to your computer. Make sure to store this file because GitHub only stores the public portion of the key. For more information about securely storing your key, see [Storing private keys](#storing-private-keys).

> [!NOTE]
> If you're using a library that requires a specific file format, the PEM file you download will be in `PKCS#1 RSAPrivateKey` format.

## Verifying private keys

GitHub generates a fingerprint for each private and public key pair using the SHA-256 hash function. You can verify that your private key matches the public key stored on GitHub by generating the fingerprint of your private key and comparing it to the fingerprint shown on GitHub.

To verify a private key:

1. Find the fingerprint for the private and public key pair you want to verify in the "Credentials" section of the settings for your GitHub App. For more information, see [Generating private keys](#generating-private-keys).

   ![Screenshot of a private key in a GitHub App settings page.](/assets/images/github-apps/github-apps-private-key-fingerprint-new.png)

2. Generate the fingerprint of your private key (PEM) locally by using the following command:

   ```shell
   openssl rsa -in PATH_TO_PEM_FILE -pubout -outform DER | openssl sha256 -binary | openssl base64
   ```

3. Compare the results of the locally generated fingerprint to the fingerprint you see in GitHub.

## Deleting private keys

You can remove a lost or compromised private key by deleting it, but you must regenerate a new key before you can delete the existing key.

1. In the upper-right corner of any page on GitHub, click your profile picture.
2. Navigate to your account settings.
   * For an app owned by a personal account, click **Settings**.
   * For an app owned by an organization:
     1. Click **Your organizations**.
     2. To the right of the organization, click **Settings**.
3. In the left sidebar, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-code" aria-label="code" role="img"><path d="m11.28 3.22 4.25 4.25a.75.75 0 0 1 0 1.06l-4.25 4.25a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734L13.94 8l-3.72-3.72a.749.749 0 0 1 .326-1.275.749.749 0 0 1 .734.215Zm-6.56 0a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042L2.06 8l3.72 3.72a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215L.47 8.53a.75.75 0 0 1 0-1.06Z"></path></svg> Developer settings**.
4. In the left sidebar, click **GitHub Apps**.
5. Next to the GitHub App that you want to delete a private key for, click **Edit**.
6. In the left sidebar, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-key" aria-label="code" role="img"><path d="M10.5 0a5.499 5.499 0 1 1-1.288 10.848l-.932.932a.749.749 0 0 1-.53.22H7v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22H5v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22h-2A1.75 1.75 0 0 1 0 14.25v-2c0-.199.079-.389.22-.53l4.932-4.932A5.5 5.5 0 0 1 10.5 0Zm-4 5.5c-.001.431.069.86.205 1.269a.75.75 0 0 1-.181.768L1.5 12.56v1.69c0 .138.112.25.25.25h1.69l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l1.023-1.025a.75.75 0 0 1 .768-.18A4 4 0 1 0 6.5 5.5ZM11 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path></svg> Credentials**, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-key" aria-label="code" role="img"><path d="M10.5 0a5.499 5.499 0 1 1-1.288 10.848l-.932.932a.749.749 0 0 1-.53.22H7v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22H5v.75a.749.749 0 0 1-.22.53l-.5.5a.749.749 0 0 1-.53.22h-2A1.75 1.75 0 0 1 0 14.25v-2c0-.199.079-.389.22-.53l4.932-4.932A5.5 5.5 0 0 1 10.5 0Zm-4 5.5c-.001.431.069.86.205 1.269a.75.75 0 0 1-.181.768L1.5 12.56v1.69c0 .138.112.25.25.25h1.69l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l.06-.06v-1.19a.75.75 0 0 1 .75-.75h1.19l1.023-1.025a.75.75 0 0 1 .768-.18A4 4 0 1 0 6.5 5.5ZM11 6a1 1 0 1 1 0-2 1 1 0 0 1 0 2Z"></path></svg> Key pairs**.
7. Under "Key pairs", to the right of the private key you want to delete, click **Delete**.
8. When prompted, confirm you want to delete the private key by clicking **Delete**. If your GitHub App has only one key, you will need to generate a new key before deleting the old key. For more information, see [Generating private keys](#generating-private-keys).

## Storing private keys

The private key is the single most valuable secret for a GitHub App. Consider storing the key in a key vault, such as [Azure Key Vault](https://azure.microsoft.com/en-gb/products/key-vault), and making it sign-only. This helps ensure that you can't lose the private key. Once the private key is uploaded to the key vault, it can never be read from there. It can only be used to sign things, and access to the private key is determined by your infrastructure rules.

Alternatively, you can store the key as an environment variable. This is not as strong as storing the key in a key vault. If an attacker gains access to the environment, they can read the private key and gain persistent authentication as the GitHub App.

You should not hard-code your private key in your app, even if your code is stored in a private repository.

For more information, see [Best practices for creating a GitHub App](/en/apps/creating-github-apps/about-creating-github-apps/best-practices-for-creating-a-github-app).

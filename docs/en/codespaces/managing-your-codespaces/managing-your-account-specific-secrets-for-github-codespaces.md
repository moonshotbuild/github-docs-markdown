---
source_path: "/en/codespaces/managing-your-codespaces/managing-your-account-specific-secrets-for-github-codespaces"
title: "Managing your account-specific secrets for GitHub Codespaces"
intro: "You can store sensitive information, like tokens, that you want to access in your codespaces via environment variables."
product: "Codespaces"
document_type: "article"
breadcrumbs:
  - title: "Codespaces"
    href: "/en/codespaces"
  - title: "Managing your codespaces"
    href: "/en/codespaces/managing-your-codespaces"
  - title: "Codespaces secrets"
    href: "/en/codespaces/managing-your-codespaces/managing-your-account-specific-secrets-for-github-codespaces"
---

# Managing your account-specific secrets for GitHub Codespaces

You can store sensitive information, like tokens, that you want to access in your codespaces via environment variables.

## About secrets for GitHub Codespaces

You can add development environment secrets to your personal account that you want to use in your codespaces. For example, you may want to store and access the following sensitive information as secrets:

* Access tokens to cloud services
* Service principals
* Subscription identifiers
* Credentials for a private image registry (for more information, see [Allowing your codespace to access a private registry](/en/codespaces/reference/allowing-your-codespace-to-access-a-private-registry))

You can choose which repositories should have access to each secret. Then, you can use the secret in any codespace you create for a repository that has access to the secret. To share a secret with a codespace created from a template, you will need to publish the codespace to a repository on GitHub, then give that repository access to the secret.

Once you have created a secret, it will be available when you create a new codespace or restart the codespace. If you've created a secret on GitHub and you want to use it in a currently running codespace, stop the codespace and then restart it. For information about stopping the codespace, see [Using the Visual Studio Code Command Palette in GitHub Codespaces](/en/codespaces/reference/using-the-vs-code-command-palette-in-codespaces#suspending-or-stopping-a-codespace).

### Naming secrets

The following rules apply to secret names:

* Secret names can only contain alphanumeric characters (`[a-z]`, `[A-Z]`, `[0-9]`) or underscores (`_`). Spaces are not allowed.
* Secret names must not start with the `GITHUB_` prefix.
* Secret names must not start with a number.
* Secret names are not case-sensitive.
* Secret names must be unique at the level they are created at. For example, a secret created at the repository level must have a unique name in that repository.

If a secret with the same name exists at multiple levels, the secret at the lowest level takes precedence. For example, if an organization-level secret has the same name as a repository-level secret, then the repository-level secret takes precedence.

### Limits for secrets

You can store up to 100 secrets for GitHub Codespaces.

Secrets are limited to 48 KB in size.

## Adding a secret

1. In the upper-right corner of any page on GitHub, click your profile picture, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="gear" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> Settings**.
2. In the sidebar, under "Code, planning, and automation", click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-codespaces" aria-label="codespaces" role="img"><path d="M0 11.25c0-.966.784-1.75 1.75-1.75h12.5c.966 0 1.75.784 1.75 1.75v3A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25Zm2-9.5C2 .784 2.784 0 3.75 0h8.5C13.216 0 14 .784 14 1.75v5a1.75 1.75 0 0 1-1.75 1.75h-8.5A1.75 1.75 0 0 1 2 6.75Zm1.75-.25a.25.25 0 0 0-.25.25v5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-5a.25.25 0 0 0-.25-.25Zm-2 9.5a.25.25 0 0 0-.25.25v3c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-3a.25.25 0 0 0-.25-.25Z"></path><path d="M7 12.75a.75.75 0 0 1 .75-.75h4.5a.75.75 0 0 1 0 1.5h-4.5a.75.75 0 0 1-.75-.75Zm-4 0a.75.75 0 0 1 .75-.75h.5a.75.75 0 0 1 0 1.5h-.5a.75.75 0 0 1-.75-.75Z"></path></svg> Codespaces**.
3. To the right of "Codespaces secrets", click **New secret**.
4. Under "Name," type a name for your secret.
5. Under "Value", type the value of your secret.
6. Select the "Repository access" drop-down menu, then click a repository you want to have access to the secret. Repeat for every repository you want to have access to the secret.

   ![Screenshot of the "Repository access" dropdown menu. Two repositories are listed in the dropdown menu.](/assets/images/help/codespaces/select-repository-access.png)
7. Click **Add secret**.

## Editing a secret

You can update the value of an existing secret, and you can change which repositories can access a secret.

1. In the upper-right corner of any page on GitHub, click your profile picture, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="gear" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> Settings**.

2. In the sidebar, under "Code, planning, and automation", click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-codespaces" aria-label="codespaces" role="img"><path d="M0 11.25c0-.966.784-1.75 1.75-1.75h12.5c.966 0 1.75.784 1.75 1.75v3A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25Zm2-9.5C2 .784 2.784 0 3.75 0h8.5C13.216 0 14 .784 14 1.75v5a1.75 1.75 0 0 1-1.75 1.75h-8.5A1.75 1.75 0 0 1 2 6.75Zm1.75-.25a.25.25 0 0 0-.25.25v5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-5a.25.25 0 0 0-.25-.25Zm-2 9.5a.25.25 0 0 0-.25.25v3c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-3a.25.25 0 0 0-.25-.25Z"></path><path d="M7 12.75a.75.75 0 0 1 .75-.75h4.5a.75.75 0 0 1 0 1.5h-4.5a.75.75 0 0 1-.75-.75Zm-4 0a.75.75 0 0 1 .75-.75h.5a.75.75 0 0 1 0 1.5h-.5a.75.75 0 0 1-.75-.75Z"></path></svg> Codespaces**.

3. Under "Codespaces secrets," to the right of the secret you want to edit, click **Update**.

4. Under "Value," click the link "**enter a new value**."

   ![Screenshot of the "Codespaces / Update secret" page. The "enter a new value" link is highlighted with a dark orange outline.](/assets/images/help/codespaces/codespaces-secret-update-value-text.png)

5. Under "Value", type the value of your secret.

6. Select the "Repository access" drop-down menu, then click a repository you want to have access to the secret. Repeat for every repository you want to have access to the secret.

   ![Screenshot of the "Repository access" dropdown menu. Two repositories are listed in the dropdown menu.](/assets/images/help/codespaces/select-repository-access.png)

7. Optionally, to remove the secret's access to a repository, deselect the repository.

   ![Screenshot showing a list of two repositories. Each has a selected checkbox.](/assets/images/help/codespaces/codespaces-secret-repository-checkboxes.png)

8. Click **Save changes**.

## Deleting a secret

1. In the upper-right corner of any page on GitHub, click your profile picture, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="gear" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> Settings**.
2. In the sidebar, under "Code, planning, and automation", click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-codespaces" aria-label="codespaces" role="img"><path d="M0 11.25c0-.966.784-1.75 1.75-1.75h12.5c.966 0 1.75.784 1.75 1.75v3A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25Zm2-9.5C2 .784 2.784 0 3.75 0h8.5C13.216 0 14 .784 14 1.75v5a1.75 1.75 0 0 1-1.75 1.75h-8.5A1.75 1.75 0 0 1 2 6.75Zm1.75-.25a.25.25 0 0 0-.25.25v5c0 .138.112.25.25.25h8.5a.25.25 0 0 0 .25-.25v-5a.25.25 0 0 0-.25-.25Zm-2 9.5a.25.25 0 0 0-.25.25v3c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-3a.25.25 0 0 0-.25-.25Z"></path><path d="M7 12.75a.75.75 0 0 1 .75-.75h4.5a.75.75 0 0 1 0 1.5h-4.5a.75.75 0 0 1-.75-.75Zm-4 0a.75.75 0 0 1 .75-.75h.5a.75.75 0 0 1 0 1.5h-.5a.75.75 0 0 1-.75-.75Z"></path></svg> Codespaces**.
3. Under "Codespaces secrets," to the right of the secret you want to delete, click **Delete**.
4. Read the warning, then click **OK**.

## Managing secrets from inside a codespace

The `GITHUB_TOKEN` that GitHub Codespaces provides in a codespace can't manage your account-specific Codespaces secrets. You can't use this token to list, add, update, or delete these secrets, to get the public key used to encrypt them, or to change which repositories can access them. This restriction doesn't affect repository or organization secrets, or how your secrets are added to your codespaces as environment variables.

To manage your account-specific secrets, we recommend using your Codespaces settings in a browser. See [Adding a secret](#adding-a-secret).

If you want to manage these secrets from a codespace terminal, for example with GitHub CLI, you must use a credential that you authorize separately. The credential needs permission to manage your Codespaces secrets:

* **OAuth app tokens and personal access tokens (classic):** The `codespace` scope. The following `gh auth login` command requests this scope in addition to the scopes that GitHub CLI always requests: `repo`, `read:org`, and `gist`. The resulting token can access your repositories, read your organization memberships, and manage your gists, as well as your Codespaces secrets. If you don't want to make this access available in the codespace, use your Codespaces settings in a browser, or manage your secrets from a trusted local machine.
* **Fine-grained personal access tokens:** The "Codespaces user secrets" account permission, with write access. To give repositories access to a secret, the token must also include each of those repositories, with the "Codespaces secrets" repository permission. If you update a secret that repositories can already access, the token needs this access to each of those repositories too.

> [!WARNING]
> When you authorize a credential in a codespace, code running in that codespace, such as dependencies, extensions, and lifecycle scripts, can use the credential. Only authorize a credential in a codespace if you trust all the code that runs in it. Otherwise, use your Codespaces settings in a browser, or manage your secrets from a trusted local machine.

GitHub CLI uses the `GH_TOKEN` environment variable first, then `GITHUB_TOKEN`, and only then the credentials stored by `gh auth login`. Because a codespace sets `GITHUB_TOKEN`, running `gh auth login` on its own isn't enough. On Linux, you can unset these variables for a single command, without removing them from your codespace environment.

1. In the terminal, authenticate GitHub CLI with the `codespace` scope.

   ```shell copy
   env -u GH_TOKEN -u GITHUB_TOKEN gh auth login --hostname github.com --web --scopes codespace
   ```

   If GitHub CLI asks for your preferred protocol for Git operations, choose **HTTPS**. When it asks whether to authenticate Git with your GitHub credentials, answer **No**. If you answer yes, the token can be saved to a Git credential helper, and `gh auth logout` doesn't remove it from there.

2. Run the `gh secret` command you need with the `--user` flag, again unsetting the environment variables for that command. For example, to add or update a secret and give a repository access to it, run the following command, replacing `SECRET-NAME` and `OWNER/REPO`. To give more than one repository access, use a comma-separated list of repositories, each in the `OWNER/REPO` format. GitHub CLI prompts you for the secret value.

   ```shell copy
   env -u GH_TOKEN -u GITHUB_TOKEN gh secret set SECRET-NAME --user --repos OWNER/REPO
   ```

   To list your secrets, run `env -u GH_TOKEN -u GITHUB_TOKEN gh secret list --user`.

3. When you've finished, remove the stored credential from the codespace. Replace `USERNAME` with your GitHub username.

   ```shell copy
   env -u GH_TOKEN -u GITHUB_TOKEN gh auth logout --hostname github.com --user USERNAME
   ```

   Signing out only removes the credential that GitHub CLI stored in the codespace. If you had already signed in to GitHub CLI in the codespace with the same account and hostname, signing in again replaced that stored credential, and signing out doesn't restore your previous sign-in.

   Signing out doesn't revoke the token, so it doesn't protect you if code in the codespace has already copied the credential. If you think a credential might have been exposed, you can revoke your authorization for GitHub CLI. Revoking the authorization invalidates all GitHub CLI tokens that it granted, so you may also be signed out of GitHub CLI on other machines, including your local machine. See [Reviewing your authorized OAuth apps](/en/apps/oauth-apps/using-oauth-apps/reviewing-your-authorized-oauth-apps).

> [!WARNING]
> Don't include a secret value or a token in a command. Commands can be saved in your shell history and are visible to other processes.

### Connecting to an enterprise on GHE.com

If you access GitHub through a subdomain of GHE.com, such as `SUBDOMAIN.ghe.com`, use the following commands instead of the commands in the previous steps. Replace `SUBDOMAIN` with your enterprise's subdomain.

1. Authenticate GitHub CLI with your enterprise's hostname.

   ```shell copy
   env -u GH_TOKEN -u GITHUB_TOKEN gh auth login --hostname SUBDOMAIN.ghe.com --web --scopes codespace
   ```

2. Set `GH_HOST` in each `gh secret` command, so that GitHub CLI uses your enterprise's subdomain instead of GitHub.com.

   ```shell copy
   env -u GH_TOKEN -u GITHUB_TOKEN GH_HOST=SUBDOMAIN.ghe.com gh secret set SECRET-NAME --user --repos OWNER/REPO
   env -u GH_TOKEN -u GITHUB_TOKEN GH_HOST=SUBDOMAIN.ghe.com gh secret list --user
   ```

3. When you've finished, sign out using the same hostname.

   ```shell copy
   env -u GH_TOKEN -u GITHUB_TOKEN gh auth logout --hostname SUBDOMAIN.ghe.com --user USERNAME
   ```

## Using secrets

A development environment secret is exported as an environment variable into the user's terminal session.

![Screenshot of the Terminal in VS Code. The command "echo $EXAMPLE\_API\_KEY" has returned "aBCdeFG1234567."](/assets/images/help/codespaces/exported-codespace-secret.png)

You can use development environment secrets after the codespace is built and is running. For example, a secret can be used:

* When launching an application from the integrated terminal or ssh session.
* Within a dev container lifecycle script that is run after the codespace is running. For more information about dev container lifecycle scripts, see the documentation on the Development Containers website: [Specification](https://containers.dev/implementors/json_reference/#lifecycle-scripts).

Development environment secrets cannot be used:

* During codespace build time (that is, within a Dockerfile or custom entry point).
* Within a dev container feature. For more information, see the `features` property in the [dev containers specification](https://containers.dev/implementors/json_reference/#general-properties) on the Development Containers website.

## Further reading

* [Managing development environment secrets for your repository or organization](/en/codespaces/managing-codespaces-for-your-organization/managing-development-environment-secrets-for-your-repository-or-organization)
* [Creating a codespace for a repository](/en/codespaces/developing-in-a-codespace/creating-a-codespace-for-a-repository#recommended-secrets)
* [Setting your user preferences](/en/codespaces/setting-your-user-preferences)
* [Customizing your codespace](/en/codespaces/customizing-your-codespace)

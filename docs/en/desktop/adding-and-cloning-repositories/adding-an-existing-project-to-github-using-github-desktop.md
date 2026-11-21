---
source_path: "/en/desktop/adding-and-cloning-repositories/adding-an-existing-project-to-github-using-github-desktop"
title: "Adding an existing project to GitHub using GitHub Desktop"
intro: "You can add an existing Git repository to GitHub using GitHub Desktop."
product: "GitHub Desktop"
document_type: "article"
breadcrumbs:
  - title: "GitHub Desktop"
    href: "/en/desktop"
  - title: "Add & clone repositories"
    href: "/en/desktop/adding-and-cloning-repositories"
  - title: "Add an existing project"
    href: "/en/desktop/adding-and-cloning-repositories/adding-an-existing-project-to-github-using-github-desktop"
---

# Adding an existing project to GitHub using GitHub Desktop

You can add an existing Git repository to GitHub using GitHub Desktop.

1. Using the command line, remove any git remotes currently configured for the repository.

   ```shell
   # Show existing remotes
   $ git remote -v
   > origin	git@git-server/octocat/hello-world.git (fetch)
   > origin	git@git-server/octocat/hello-world.git (push)
   # Remove existing remotes
   $ git remote remove origin
   ```
2. [Add the repository to GitHub Desktop](/en/desktop/adding-and-cloning-repositories/adding-a-repository-from-your-local-computer-to-github-desktop).
3. In the repository bar, click **Publish repository**.

   ![Screenshot of the repository bar. A button, labeled "Publish repository", is highlighted with an orange outline.](/assets/images/help/desktop/publish-repository.png)
4. In the "Publish Repository" window, select the **Account** dropdown menu, then click the account you want to publish the repository with. If the repository is assigned to an account that's signed in, that account is selected. For more information, see [Using multiple accounts in GitHub Desktop](/en/desktop/installing-and-authenticating-to-github-desktop/using-multiple-accounts-in-github-desktop).
5. In the "Name" field, type the desired name of the repository or use the default current local repository name.
6. Optionally, add a description for the repository.
7. Optionally, to publish a public repository, deselect **Keep this code private**.
8. Select the "Organization" dropdown menu, then either click the organization where you want to publish the repository, or, to publish the repository to your personal account, click **None**.
9. Click **Publish Repository**.

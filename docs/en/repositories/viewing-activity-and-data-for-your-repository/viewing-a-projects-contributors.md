---
source_path: "/en/repositories/viewing-activity-and-data-for-your-repository/viewing-a-projects-contributors"
title: "Viewing a project's contributors"
intro: "You can see who contributed commits to a repository and its dependencies."
product: "Repositories"
document_type: "article"
breadcrumbs:
  - title: "Repositories"
    href: "/en/repositories"
  - title: "View activity and data"
    href: "/en/repositories/viewing-activity-and-data-for-your-repository"
  - title: "View project contributors"
    href: "/en/repositories/viewing-activity-and-data-for-your-repository/viewing-a-projects-contributors"
---

# Viewing a project's contributors

You can see who contributed commits to a repository.

## About contributors

> \[!NOTE]
> Certain contributor, commit, and code frequency insights are only available for repositories that have fewer than 10,000 commits.

You can view the top 100 contributors to a repository in the contributors graph. Merge commits and empty commits aren't counted as contributions for this graph.

To access the list of community contributors, visit `https://github.com/REPO-OWNER/REPO-NAME/graphs/contributors`.

## Accessing the contributors graph

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-graph" aria-label="graph" role="img"><path d="M1.5 1.75V13.5h13.75a.75.75 0 0 1 0 1.5H.75a.75.75 0 0 1-.75-.75V1.75a.75.75 0 0 1 1.5 0Zm14.28 2.53-5.25 5.25a.75.75 0 0 1-1.06 0L7 7.06 4.28 9.78a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042l3.25-3.25a.75.75 0 0 1 1.06 0L10 7.94l4.72-4.72a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042Z"></path></svg> Insights**.

   ![Screenshot of the main page of a repository. In the horizontal navigation bar, a tab, labeled with a graph icon and "Insights," is outlined in orange.](/assets/images/help/repository/repo-nav-insights-tab.png)
3. In the left sidebar, click **Contributors**.
4. Optionally, to view contributors during a specific time period, to the right of "Contributors," click **Period: All**. Then select a time period.
5. Optionally, to view the graph as a table, in the top-right corner of the graph, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="Chart options" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg>. Then click **View as table**.
6. Optionally, to download a CSV or PNG, in the top-right corner of the graph, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="Chart options" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg>. Then click **Download CSV** or **Download PNG**.

## Troubleshooting contributors

If you don't appear in a repository's contributors graph, it may be because:

* You aren't one of the top 100 contributors.
* Your commits haven't been merged into the default branch.
* The email address you used to author the commits isn't connected to your GitHub account.

> \[!TIP]
> To list all commit contributors in a repository, see [REST API endpoints for repositories](/en/rest/repos/repos#list-repository-contributors).

If all your commits in the repository are on non-default branches, you won't be in the contributors graph. For example, commits on the `gh-pages` branch aren't included in the graph unless `gh-pages` is the repository's default branch. To have your commits merged into the default branch, you can create a pull request. For more information, see [Pull requests](/en/pull-requests/reference/pull-requests).

If the email address you used to author the commits is not connected to your GitHub account, your commits won't be linked to your account, and you won't appear in the contributors graph. For more information, see [Setting your commit email address](/en/account-and-profile/how-tos/email-preferences/setting-your-commit-email-address) and [Adding an email address to your GitHub account](/en/account-and-profile/how-tos/email-preferences/adding-an-email-address-to-your-github-account).

### Contributor data is stale after history changes

After force-pushing, rewriting history, or deleting commits, repository contributor displays and statistics can take about 24 hours to refresh.

If you're a repository owner and contributor data is still incorrect after waiting about 24 hours, contact GitHub Support. For more information about creating a support ticket, see [Creating a support ticket](/en/support/contacting-github-support/creating-a-support-ticket).

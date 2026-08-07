---
source_path: "/en/actions/how-tos/manage-runners/larger-runners/use-larger-runners"
title: "Running jobs on larger runners"
intro: "Identify available larger runners, then route jobs to the right runners by using runner groups and workflow labels."
product: "GitHub Actions"
document_type: "article"
breadcrumbs:
  - title: "GitHub Actions"
    href: "/en/actions"
  - title: "How-tos"
    href: "/en/actions/how-tos"
  - title: "Manage runners"
    href: "/en/actions/how-tos/manage-runners"
  - title: "Larger runners"
    href: "/en/actions/how-tos/manage-runners/larger-runners"
  - title: "Use larger runners"
    href: "/en/actions/how-tos/manage-runners/larger-runners/use-larger-runners"
---

# Running jobs on larger runners

Identify available larger runners, then route jobs to the right runners by using runner groups and workflow labels.

## Identifying available runners for a repository

If you have `repo: write` access to a repository, you can view a list of the runners available to the repository.

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-play" aria-label="play" role="img"><path d="M8 0a8 8 0 1 1 0 16A8 8 0 0 1 8 0ZM1.5 8a6.5 6.5 0 1 0 13 0 6.5 6.5 0 0 0-13 0Zm4.879-2.773 4.264 2.559a.25.25 0 0 1 0 .428l-4.264 2.559A.25.25 0 0 1 6 10.559V5.442a.25.25 0 0 1 .379-.215Z"></path></svg> Actions**.

   ![Screenshot of the tabs for the "github/docs" repository. The "Actions" tab is highlighted with an orange outline.](/assets/images/help/repository/actions-tab-global-nav-update.png)
3. In the left sidebar, under the "Management" section, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-server" aria-label="server" role="img"><path d="M1.75 1h12.5c.966 0 1.75.784 1.75 1.75v4c0 .372-.116.717-.314 1 .198.283.314.628.314 1v4a1.75 1.75 0 0 1-1.75 1.75H1.75A1.75 1.75 0 0 1 0 12.75v-4c0-.358.109-.707.314-1a1.739 1.739 0 0 1-.314-1v-4C0 1.784.784 1 1.75 1ZM1.5 2.75v4c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-4a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25Zm.25 5.75a.25.25 0 0 0-.25.25v4c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-4a.25.25 0 0 0-.25-.25ZM7 4.75A.75.75 0 0 1 7.75 4h4.5a.75.75 0 0 1 0 1.5h-4.5A.75.75 0 0 1 7 4.75ZM7.75 10h4.5a.75.75 0 0 1 0 1.5h-4.5a.75.75 0 0 1 0-1.5ZM3 4.75A.75.75 0 0 1 3.75 4h.5a.75.75 0 0 1 0 1.5h-.5A.75.75 0 0 1 3 4.75ZM3.75 10h.5a.75.75 0 0 1 0 1.5h-.5a.75.75 0 0 1 0-1.5Z"></path></svg> Runners**.
4. Review the list of available runners for the repository.
5. Optionally, to copy a runner's label to use it in a workflow, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="More options" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg> to the right of the runner, then click **Copy label**.

> \[!NOTE]
> Enterprise and organization owners can create runners from this page. To create a new runner, click **New runner** at the top right of the list of runners to add runners to the repository.
>
> For more information, see [Managing larger runners](/en/actions/how-tos/manage-runners/larger-runners/manage-larger-runners) and [Adding self-hosted runners](/en/actions/how-tos/manage-runners/self-hosted-runners/add-runners).

## Targeting larger runners in a workflow

After you identify the larger runners you want to use, you can target them in your workflow with runner groups, workflow labels, or both. Use runner groups to route jobs to a set of runners, workflow labels to target runners with a specific label, or both when a job must match both conditions.

If an administrator has disabled standard GitHub-hosted runners, you can only use runner groups.

### Targeting by runner group

Reference the runner group name in your workflow. Use this when you want to route a job to any available runner in a specific group.

<div class="ghd-tool linux">

In this example, runners have been added to a group called `build-runners`. The `runs-on` key sends the job to any available runner in the `build-runners` group:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on: 
      group: build-runners
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v7
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

</div>

<div class="ghd-tool windows">

In this example, runners have been added to a group called `build-runners`. The `runs-on` key sends the job to any available runner in the `build-runners` group:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on: 
      group: build-runners
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v7
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

</div>

<div class="ghd-tool mac">

In this example, the `runs-on` key sends the job to any available runner in the `macos-build-runners` group:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-swift-version:
    runs-on:
      group: macos-build-runners
    steps:
      - uses: actions/checkout@v6
      - name: Build
        run: swift build
      - name: Run tests
        run: swift test
```

</div>

### Targeting by workflow label

Reference a workflow label in your workflow when you want to route a job to runners that share a specific label.

Larger runners are automatically assigned a workflow label that matches the runner name.

<div class="ghd-tool linux">

In this example, the `runs-on` key sends the job to any available runner that has been assigned the `ubuntu-24.04-16core` label:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on:
      labels: ubuntu-24.04-16core
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v7
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

</div>

<div class="ghd-tool windows">

In this example, the `runs-on` key sends the job to any available runner that has been assigned the `windows-2022-16core` label:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on:
      labels: windows-2022-16core
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v7
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

</div>

<div class="ghd-tool mac">

For macOS larger runners, you can use either GitHub-defined workflow labels or the workflow label that is automatically assigned from the larger runner name you set when you create it. For a list of available macOS workflow labels, see [Larger runners reference](/en/actions/reference/runners/larger-runners#available-macos-larger-runners-and-labels).

In this example, the `runs-on` key sends the job to any available runner that has been assigned the `macos-26-xlarge` label.

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-swift-version:
    runs-on: macos-26-xlarge
    steps:
      - uses: actions/checkout@v6
      - name: Build
        run: swift build
      - name: Run tests
        run: swift test
```

</div>

### Using labels and groups to control where jobs are run

Use both labels and groups when a job must run only on runners in a specific group that also have a specific label. The runner must meet both requirements to be eligible to run the job.

<div class="ghd-tool linux">

When you combine groups and labels, the runner must meet both requirements to be eligible to run the job.

In this example, the `runs-on` key combines `group` and `labels` so that the job is routed to any available runner within the group that also has a matching label:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on:
      group: ubuntu-runners
      labels: ubuntu-24.04-16core
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v7
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

</div>

<div class="ghd-tool windows">

When you combine groups and labels, the runner must meet both requirements to be eligible to run the job.

In this example, the `runs-on` key combines `group` and `labels` so that the job is routed to any available runner within the group that also has a matching label:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-bats-version:
    runs-on:
      group: ubuntu-runners
      labels: ubuntu-24.04-16core
    steps:
      - uses: actions/checkout@v6
      - uses: actions/setup-node@v7
        with:
          node-version: '14'
      - run: npm install -g bats
      - run: bats -v
```

</div>

<div class="ghd-tool mac">

In this example, the `runs-on` key combines `group` and `labels` so that the job is routed to any available runner within the group that also has a matching label:

```yaml
name: learn-github-actions
on: [push]
jobs:
  check-swift-version:
    runs-on:
      group: macos-runners
      labels: macos-26-xlarge
    steps:
      - uses: actions/checkout@v6
      - name: Build
        run: swift build
      - name: Run tests
        run: swift test
```

</div>

## Further reading

For syntax details for the `runs-on` key, see [Workflow syntax for GitHub Actions](/en/actions/reference/workflows-and-actions/workflow-syntax#jobsjob_idruns-on).

For specifications, labels, limitations, and troubleshooting information, see [Larger runners reference](/en/actions/reference/runners/larger-runners).

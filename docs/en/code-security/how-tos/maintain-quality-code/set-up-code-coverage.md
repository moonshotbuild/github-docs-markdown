---
source_path: "/en/code-security/how-tos/maintain-quality-code/set-up-code-coverage"
title: "Setting up code coverage for your repository"
intro: "Use built-in code coverage from Code Quality to find untested code on pull requests, without paying for or maintaining a separate third-party service."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "How-tos"
    href: "/en/code-security/how-tos"
  - title: "Maintain quality code"
    href: "/en/code-security/how-tos/maintain-quality-code"
  - title: "Set up code coverage"
    href: "/en/code-security/how-tos/maintain-quality-code/set-up-code-coverage"
---

# Setting up code coverage for your repository

Use built-in code coverage from Code Quality to find untested code on pull requests, without paying for or maintaining a separate third-party service.

You can set up code coverage for your repository in two ways:

* **Automatic setup:** Use the AI-powered agent to generate a workflow automatically. Choose this option if:
  * You want to get started quickly without writing YAML configuration.
  * Your project uses common test frameworks and build patterns.
  * You're comfortable iterating on an AI-generated workflow.
* **Manual setup:** Configure your CI workflow yourself. Choose this option if:
  * You need precise control over the coverage process.
  * You have complex CI requirements (such as private registries or custom build steps).
  * You want to understand exactly how coverage is configured.

## Automatic setup

You can use the automatic setup option to generate a working code coverage workflow without manually authoring CI configuration. An agent analyzes your repository, identifies your test framework, and opens a pull request with a coverage workflow ready for review.

> \[!NOTE]
> Automatic setup uses AI to generate the workflow file. There is no additional cost for using this feature.

### Prerequisites for automatic setup

* Code Quality is enabled for your repository. See [Enabling GitHub Code Quality](/en/code-security/how-tos/maintain-quality-code/enable-code-quality).
* Your repository has an existing test suite.

### Generating a coverage workflow automatically

1. On GitHub, navigate to the main page of the repository.
2. Under your repository name, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="gear" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> Settings**. If you cannot see the "Settings" tab, select the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-kebab-horizontal" aria-label="More" role="img"><path d="M8 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3ZM1.5 9a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Zm13 0a1.5 1.5 0 1 0 0-3 1.5 1.5 0 0 0 0 3Z"></path></svg>** dropdown menu, then click **Settings**.

   ![Screenshot of a repository header showing the tabs. The "Settings" tab is highlighted by a dark orange outline.](/assets/images/help/repository/repo-actions-settings.png)
3. In the sidebar, under "Security", click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-code-square" aria-label="code review" role="img"><path d="M0 1.75C0 .784.784 0 1.75 0h12.5C15.216 0 16 .784 16 1.75v12.5A1.75 1.75 0 0 1 14.25 16H1.75A1.75 1.75 0 0 1 0 14.25Zm1.75-.25a.25.25 0 0 0-.25.25v12.5c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25V1.75a.25.25 0 0 0-.25-.25Zm7.47 3.97a.75.75 0 0 1 1.06 0l2 2a.75.75 0 0 1 0 1.06l-2 2a.749.749 0 0 1-1.275-.326.749.749 0 0 1 .215-.734L10.69 8 9.22 6.53a.75.75 0 0 1 0-1.06ZM6.78 6.53 5.31 8l1.47 1.47a.749.749 0 0 1-.326 1.275.749.749 0 0 1-.734-.215l-2-2a.75.75 0 0 1 0-1.06l2-2a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042Z"></path></svg> Code quality** to display the "Code quality" page.
4. In the "Code coverage analysis" section, click the **Setup** dropdown box.
5. In the list, select **Generate workflow with AI**. Wait for the agent to analyze your repository. The agent opens a draft pull request and posts a checklist of the steps it is working through.
6. To review the pull request, click **Review pull request**.
   Review the pull request once the agent completes its work. The pull request description summarizes the changes, including any project configuration updates, workflow file changes, and coverage output settings.
7. If the workflow runs successfully in CI and coverage uploads correctly, merge the pull request.

   If the workflow needs adjustments, see [Automatic code coverage setup](/en/code-security/concepts/code-quality/automatic-code-coverage-setup) for guidance on the different outcomes and how to iterate.

For more information about how the agent works and what to expect, see [Automatic code coverage setup](/en/code-security/concepts/code-quality/automatic-code-coverage-setup).

## Manual setup

Built-in code coverage lets you track how thoroughly your tests exercise your code, without adding a third-party service to your toolchain or budget. In the following procedures, you will generate a Cobertura XML coverage report from your test suite, upload it to GitHub, and view the coverage results on your pull requests.

### Prerequisites for manual setup

* Code Quality is enabled for your repository.
* Your repository has a test suite that runs in GitHub Actions.
* Your test framework can produce a coverage report in **Cobertura XML** format.

### Step 1: Generate a Cobertura XML coverage report

Configure your test framework to output a coverage report in the Cobertura XML format. Code coverage works with any programming language that can produce this format.

1. Identify the coverage tool for your language from the table below.
2. Add the appropriate command or configuration to your CI workflow so that a Cobertura XML file is generated each time your tests run.

| Language              | Framework / Tool                | How to generate Cobertura XML                                                     |
| --------------------- | ------------------------------- | --------------------------------------------------------------------------------- |
| Python                | `pytest` + `pytest-cov`         | `pytest --cov=. --cov-report=xml`                                                 |
| Java                  | JaCoCo                          | Use the `cover2cover.py` script or the JaCoCo-to-Cobertura Gradle/Maven plugin    |
| JavaScript/TypeScript | Istanbul / `nyc`                | `nyc report --reporter=cobertura`                                                 |
| Ruby                  | SimpleCov                       | Add `SimpleCov::Formatter::CoberturaFormatter`                                    |
| Go                    | `go test` + `gocover-cobertura` | `go test -coverprofile=cover.out && gocover-cobertura < cover.out > coverage.xml` |

> \[!TIP]
> If your framework isn't listed above, check its documentation for Cobertura output support. Many tools either support it directly or can convert to Cobertura XML from other formats.

### Step 2: Upload the coverage report

After your tests generate a Cobertura XML report, upload it to GitHub so coverage results appear on pull requests.

1. Open your repository's CI workflow file (for example, `.github/workflows/ci.yml`).

2. Add the following step after the step that runs your tests and generates the coverage report:

   ```yaml copy
   - name: Upload coverage report
     if: github.event_name != 'pull_request' || github.event.pull_request.head.repo.full_name == github.repository
     uses: actions/upload-code-coverage@v1
     with:
       file: COVERAGE-FILE-PATH.xml
       language: LANGUAGE
       label: LABEL
   ```

3. Replace the following values:
   * **`COVERAGE-FILE-PATH.xml`**: The path to your Cobertura XML report (for example, `coverage.xml` or `target/site/jacoco/cobertura.xml`).
   * **`LANGUAGE`**: The primary language of the code being covered (for example, `Python`, `Java`, `JavaScript`).
   * **`LABEL`**: An optional label to identify this coverage report (for example, `code-coverage/pytest`).

4. Commit and push the workflow change.

### Full workflow example

This example runs Python tests with `pytest-cov` and uploads the coverage report:

```yaml annotate copy
# This workflow runs your test suite, generates a Cobertura XML coverage report, and uploads it to GitHub. Once this workflow is committed, coverage results appear automatically on every pull request.
name: Code Coverage

# Run on pushes to the default branch (to establish the baseline) and on pull requests (to compare against it). Code Quality compares PR branch coverage to the default branch, so both triggers are needed.
on:
  push:
    branches: [main]
  pull_request:
    branches: [main]

# The `code-quality: write` permission is required to upload coverage data. No other elevated permissions are needed.
permissions:
  contents: read
  code-quality: write

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      # Check out the PR head commit (not the merge commit) so coverage line numbers map correctly to the diff.
      - uses: actions/checkout@v6
        with:
          ref: ${{ github.event.pull_request.head.sha || github.sha }}

      # Replace this step with whatever language setup your project uses (Node.js, Java, Go, etc.). The upload action works with any language that produces a Cobertura XML report.
      - uses: actions/setup-python@v5
        with:
          python-version: "3.x"

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt
          pip install pytest pytest-cov

      # Adapt this step for your test framework. The key requirement is producing a Cobertura XML file. For other languages, see the framework table earlier in this article.
      - name: Run tests with coverage
        run: pytest --cov=. --cov-report=xml

      # This step replaces any third-party coverage upload (Codecov, Coveralls, etc.). After this runs, the `github-code-quality[bot]` bot posts a coverage summary directly on the pull request.
      - name: Upload coverage report
        if: github.event_name != 'pull_request' || github.event.pull_request.head.repo.full_name == github.repository
        uses: actions/upload-code-coverage@v1
        with:
          file: coverage.xml
          language: Python
          label: code-coverage/pytest
```

### Step 3: View coverage results on pull requests

1. Open a pull request (or push to an existing one) that triggers the workflow you configured.
2. After the workflow completes, look for a comment from `github-code-quality[bot]` on the pull request. The comment includes:
   * The aggregate coverage percentage for the pull request branch compared to the default branch.
   * A per-file breakdown showing which files gained or lost coverage.

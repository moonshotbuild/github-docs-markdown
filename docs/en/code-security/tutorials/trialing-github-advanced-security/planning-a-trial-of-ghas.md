---
source_path: "/en/code-security/tutorials/trialing-github-advanced-security/planning-a-trial-of-ghas"
title: "Planning a trial of GitHub Advanced Security"
intro: "Prepare your organization to evaluate Advanced Security against clear security and purchasing goals."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Tutorials"
    href: "/en/code-security/tutorials"
  - title: "Trial GitHub Advanced Security"
    href: "/en/code-security/tutorials/trialing-github-advanced-security"
  - title: "Plan GHAS trial"
    href: "/en/code-security/tutorials/trialing-github-advanced-security/planning-a-trial-of-ghas"
---

# Planning a trial of GitHub Advanced Security

Prepare your organization to evaluate Advanced Security against clear security and purchasing goals.

## Is a self-serve trial right for you?

This article helps you plan a **self-serve** trial of GitHub Advanced Security. A self-serve trial is right for you if both of the following are true:

* You want to conduct your trial independently, without the help of an expert or partner. Typically, this works best for small or medium-sized organizations.
* You own an eligible organization on GitHub Team.

If you want expert help with your trial, [contact our team](https://github.com/enterprise/contact).

Organizations on GitHub Team can start a trial with any payment method. To purchase through the trial checkout flow, the organization must pay by credit card, PayPal, or Azure.

## 1. Define your company goals

Before you start a trial, define its purpose and identify the key questions you need to answer. Keep these goals in focus as you plan so that you gather the information you need to decide whether to upgrade.

If your company already uses GitHub, consider what needs are currently unmet that Secret Protection or Code Security might address. You should also consider your current application security posture and longer term aims. For inspiration, see [Design Principles for Application security](https://wellarchitected.github.com/library/application-security/design-principles/) in the GitHub well-architected documentation.

<div class="ghd-tool rowheaders">

| Example need                               | Features to explore during the trial                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Enforce use of security features           | Security configurations and policies. See [Enabling security features at scale](/en/code-security/concepts/security-at-scale/organization-security).                                                                                                                                                                                                                                        |
| Protect custom access tokens               | Custom patterns for secret scanning, delegated bypass for push protection, and validity checks. See [Secret scanning](/en/code-security/concepts/secret-security/secret-scanning).                                                                                                                                                                                                          |
| Define and enforce a development process   | Dependency review, auto-triage rules, and rulesets. See [Dependency review](/en/code-security/concepts/supply-chain-security/dependency-review), [Dependabot auto-triage rules](/en/code-security/concepts/supply-chain-security/dependabot-auto-triage-rules), and [About rulesets](/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets). |
| Reduce technical debt at scale             | Security campaigns. See [About security campaigns](/en/code-security/concepts/security-at-scale/about-security-campaigns).                                                                                                                                                                                                                                                                  |
| Monitor and track trends in security risks | Security overview. See [Viewing security insights](/en/code-security/how-tos/view-and-interpret-data/analyze-organization-data/viewing-security-insights).                                                                                                                                                                                                                                  |

</div>

## 2. Identify the members of your trial team

GitHub Advanced Security enables you to integrate security measures throughout the software development life cycle. Include representatives from all areas of your development cycle so that you have the data you need to make a decision.

You may also find it helpful to identify a champion for each company need that you want to investigate.

## 3. Determine whether preliminary research is needed

Decide whether your team would benefit from hands-on experience with our free security features **before** you begin your trial. Testing code scanning and secret scanning on public repositories can help new users become familiar with the core features of GitHub Advanced Security. This lets you focus your trial period on private repositories and the advanced features and controls available in Secret Protection and Code Security.

For more information, see:

* [Enabling secret scanning for your repository](/en/code-security/how-tos/secure-your-secrets/detect-secret-leaks/enable-secret-scanning)
* [Configuring default setup for code scanning](/en/code-security/how-tos/find-and-fix-code-vulnerabilities/configure-code-scanning/configure-code-scanning)
* [Enabling the dependency graph](/en/code-security/how-tos/secure-your-supply-chain/secure-your-dependencies/enable-dependency-graph)

Organizations on GitHub Team and GitHub Enterprise can run a free report to scan their code for leaked secrets. This helps you assess your repositories' current exposure to leaked secrets and shows how many existing secret leaks could have been prevented by Secret Protection. See [Secret security with GitHub](/en/code-security/concepts/secret-security/secret-security-with-github).

## 4. Decide which repositories to test

It is generally best to use an **existing** organization and repositories. This ensures that you can experience the features in code you know well and within a familiar development environment.

If you want, add test code later. However, deliberately insecure applications, such as WebGoat, are not the best test. They may contain coding patterns that appear to be insecure but which code scanning determines cannot be exploited. As a result, code scanning may report fewer issues in these artificial codebases than other security scanners.

## 5. Define the assessment criteria for the trial

For each company need or goal you set for the trial, decide how you will measure success. For example, if you want to enforce the use of security features, create test cases for security configurations and policies to confirm they work as expected.

## 6. Start your trial

If you own an eligible organization on GitHub Team, see [Setting up a trial of GitHub Advanced Security](/en/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security).

> \[!NOTE]
> GitHub Advanced Security is free of charge during trials, but usage-based billing applies for features that consume GitHub Actions minutes or AI credits.

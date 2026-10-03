---
source_path: "/en/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security"
title: "Setting up a trial of GitHub Advanced Security"
intro: "Evaluate GitHub Code Security and GitHub Secret Protection on your existing repositories before you buy."
product: "Security and code quality"
document_type: "article"
breadcrumbs:
  - title: "Security and code quality"
    href: "/en/code-security"
  - title: "Tutorials"
    href: "/en/code-security/tutorials"
  - title: "Trial GitHub Advanced Security"
    href: "/en/code-security/tutorials/trialing-github-advanced-security"
  - title: "Trial Advanced Security"
    href: "/en/code-security/tutorials/trialing-github-advanced-security/trial-advanced-security"
---

# Setting up a trial of GitHub Advanced Security

Evaluate GitHub Code Security and GitHub Secret Protection on your existing repositories before you buy.

## Prerequisites

To start a self-serve trial for an organization on GitHub Team, all of the following must be true:

* You are an owner of the organization.
* The organization does not currently have, and has not previously had, a paid license for GitHub Advanced Security.
* The organization is not already using metered billing for GitHub Advanced Security.
* If the organization has previously had a GitHub Advanced Security trial, it has had no more than one previous trial. That trial ended at least 180 days ago.

Your payment method does not affect whether you can start a trial. However, you can purchase GitHub Advanced Security through the trial checkout flow only if your organization pays by credit card, PayPal, or Azure.

## What the trial includes

The trial gives you access to GitHub Code Security and GitHub Secret Protection for private repositories. You can evaluate capabilities such as:

* Code scanning, Copilot Autofix, dependency review, and security campaigns
* Secret scanning, push protection, custom patterns, validity checks, and delegated bypass

Use the trial on a sample of repositories so you can assess the results, developer experience, and controls before you purchase.

## Start your trial

An organization owner can start a trial from the organization's "Licensing" page.

1. In the upper-right corner of GitHub, click your profile picture, then click **Your organizations**.
2. Next to the organization, click **Settings**.
3. In the "Access" section of the sidebar, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-credit-card" aria-label="credit-card" role="img"><path d="M10.75 9a.75.75 0 0 0 0 1.5h1.5a.75.75 0 0 0 0-1.5h-1.5Z"></path><path d="M0 3.75C0 2.784.784 2 1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 14H1.75A1.75 1.75 0 0 1 0 12.25ZM14.5 6.5h-13v5.75c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25Zm0-2.75a.25.25 0 0 0-.25-.25H1.75a.25.25 0 0 0-.25.25V5h13Z"></path></svg> Billing & Licensing**, then click **Licensing**.
4. To the right of "GitHub Advanced Security", click **Try free for 30 days**, then follow the prompts to start your trial.

## Evaluate features during your trial

After you start the trial, enable the features you want to evaluate on a sample of repositories. See [Enabling security features in your trial](/en/code-security/tutorials/trialing-github-advanced-security/enable-security-features-trial).

As you evaluate the features, compare the results with the goals and success criteria you defined when planning the trial.

## Billing during your trial

During the trial, you do not pay license fees for GitHub Secret Protection or GitHub Code Security.

Usage-based billing applies for features that consume GitHub Actions minutes or AI credits. For private repositories, GitHub Actions minutes used by GitHub Advanced Security workflows count toward your organization's included usage. This includes code scanning workflows. Usage beyond the included amount is billed at the standard rate. For more information, see [Product usage included with each plan](/en/billing/reference/product-usage-included).

## Managing and finishing your trial

Your trial lasts 30 days. You can review the expiration date and current usage on the "Licensing" page for your organization or enterprise.

To purchase during the trial:

1. Access the "Licensing" page for the organization.
2. In the GitHub Advanced Security trial banner, click **Buy Advanced Security**.
3. Review the estimated monthly usage, billing information, and payment method.
4. Click **Purchase Advanced Security**.

If you do not purchase by the end of the trial, it expires automatically, and GitHub Secret Protection and GitHub Code Security features are disabled for private repositories.

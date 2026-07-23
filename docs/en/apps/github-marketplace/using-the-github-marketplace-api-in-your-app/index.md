---
source_path: "/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app"
title: "Using the GitHub Marketplace API in your app"
intro: "Learn how to integrate the GitHub Marketplace API and webhook events into your app for the GitHub Marketplace ."
product: "Apps"
document_type: "subcategory"
breadcrumbs:
  - title: "Apps"
    href: "/en/apps"
  - title: "GitHub Marketplace"
    href: "/en/apps/github-marketplace"
  - title: "Marketplace API usage"
    href: "/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app"
---

# Using the GitHub Marketplace API in your app

Learn how to integrate the GitHub Marketplace API and webhook events into your app for the GitHub Marketplace .

## Links

* [REST endpoints for the GitHub Marketplace API](/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app/rest-endpoints-for-the-github-marketplace-api)

  To help manage your app on GitHub Marketplace, use these GitHub Marketplace API endpoints.

* [Webhook events for the GitHub Marketplace API](/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app/webhook-events-for-the-github-marketplace-api)

  A GitHub Marketplace app receives information about changes to a user's plan from the Marketplace purchase event webhook. A Marketplace purchase event is triggered when a user purchases, cancels, or changes their payment plan.

* [Testing your app](/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app/testing-your-app)

  GitHub recommends testing your app with APIs and webhooks before submitting your listing to GitHub Marketplace so you can provide an ideal experience for customers. Before an onboarding expert approves your app, it must adequately handle the billing flows.

* [Handling new purchases and free trials](/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app/handling-new-purchases-and-free-trials)

  When a customer purchases a paid plan, free trial, or the free version of your GitHub Marketplace app, you'll receive the marketplace\_purchase event webhook with the purchased action, which kicks off the purchasing flow.

* [Handling plan changes](/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app/handling-plan-changes)

  Upgrading or downgrading a GitHub Marketplace app triggers the marketplace\_purchase event webhook with the changed action, which kicks off the upgrade or downgrade flow.

* [Handling plan cancellations](/en/apps/github-marketplace/using-the-github-marketplace-api-in-your-app/handling-plan-cancellations)

  Cancelling a GitHub Marketplace app triggers the marketplace\_purchase event webhook with the cancelled action, which kicks off the cancellation flow.

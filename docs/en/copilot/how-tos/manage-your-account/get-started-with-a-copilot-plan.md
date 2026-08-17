---
source_path: "/en/copilot/how-tos/manage-your-account/get-started-with-a-copilot-plan"
title: "Getting started with a GitHub Copilot plan"
intro: "You can use Copilot for free, or choose a paid plan to unlock additional features, models, and limits."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Manage your account"
    href: "/en/copilot/how-tos/manage-your-account"
  - title: "Get started with a Copilot plan"
    href: "/en/copilot/how-tos/manage-your-account/get-started-with-a-copilot-plan"
---

# Getting started with a GitHub Copilot plan

You can use Copilot for free, or choose a paid plan to unlock additional features, models, and limits.

This article covers:

* [Accessing Copilot Free](#accessing-copilot-free)
* [Upgrading from Copilot Free](#upgrading-from-copilot-free)
* [Subscribing to Copilot Pro, Copilot Pro+, or Copilot Max](#subscribing-to-copilot-pro-copilot-pro-or-copilot-max)
* [Troubleshooting](#troubleshooting)

## Accessing Copilot Free

Most individual developers can start using Copilot Free with no setup required. However, there are a few cases where Copilot Free isn't available:

* You have a managed user account.
* You are assigned a Copilot seat through an organization.
* You have an existing Copilot Pro, Copilot Pro+, or Copilot Max plan.
* You have access to Copilot through Copilot Student.
* You have free access to Copilot Pro as a teacher or open-source maintainer.

There are a few ways to start using Copilot Free, depending on where you're working.

### Visual Studio and VS Code

In Visual Studio and VS Code you can access Copilot Free directly from the editor.

1. In the top right of Visual Studio or VS Code, click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg>**.
2. In the sidebar, click **Sign up for Copilot Free**.
3. If you have a GitHub account, you will be prompted to sign in. If you don't have a GitHub account, you will be prompted to create one.

### GitHub.com

With Copilot Free, you can ask Copilot questions within a chat interface on GitHub. Go to [https://github.com/copilot](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&ref_plan=free) to start chatting with Copilot.

### GitHub Mobile

You can also chat with Copilot in GitHub Mobile.

1. In GitHub Mobile, tap the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="Copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg>** icon in the bottom right corner of the screen.

   > \[!NOTE]
   > The **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="Copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg>** icon is not shown on every page in GitHub Mobile. If you don't see the icon, navigate to a different page in GitHub Mobile and look for the icon there.
2. At the bottom of the page, use the "Ask Copilot" box to start a chat with Copilot.

### Other IDEs

To use Copilot Free in other IDEs, you'll need to activate it from your GitHub account settings first.

1. In the upper-right corner of any page on GitHub, click your profile picture, then click **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg> Copilot settings**.
2. Click **Start using Copilot Free** to activate Copilot Free and open [https://github.com/copilot](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&ref_plan=free).
3. In the top right corner, next to **Download**, select the <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-triangle-down" aria-label="More edit options" role="img"><path d="m4.427 7.427 3.396 3.396a.25.25 0 0 0 .354 0l3.396-3.396A.25.25 0 0 0 11.396 7H4.604a.25.25 0 0 0-.177.427Z"></path></svg> dropdown menu and click your preferred editor.

## Upgrading from Copilot Free

If you’re already using Copilot Free and reach your usage limit, you’ll be prompted to upgrade directly. The upgrade experience varies by where you’re using Copilot:

* **In Visual Studio, VS Code, or GitHub.com**:
  You’ll receive a message with your reset date and a link to upgrade to Copilot Pro or Copilot Pro+.

* **In other IDEs**:
  You’ll see an error message. You can start a paid plan from your [GitHub Copilot settings](https://github.com/settings/copilot).

* **In GitHub Mobile**:
  When you hit the usage limit, you’ll be prompted to upgrade via in-app purchase.

## Subscribing to Copilot Pro, Copilot Pro+, or Copilot Max

You can subscribe to Copilot Pro, Copilot Pro+, or Copilot Max at any time to unlock advanced AI features, higher usage limits, and access to additional models.

> \[!TIP] Not sure which plan to choose? For a side-by-side comparison, see [About individual GitHub Copilot plans and benefits](/en/copilot/concepts/billing/individual-plans).

1. Go to the [plans page](https://github.com/features/copilot/plans?ref_product=copilot\&ref_type=purchase\&ref_style=text\&ref_plan=pro).

2. Click **Get started** under the plan you want to subscribe to.

3. Click **Subscribe to Copilot Pro/Copilot Pro+/Copilot Max**.

   If your personal account meets the criteria for a free GitHub Copilot plan instead of a paid plan, you will automatically be taken to step 6.

4. To enable usage beyond your included allowance, select **Yes, I want to enable additional usage for Copilot**. You can change this setting at any time. Click **Save & continue**.

5. Follow the steps to enter and confirm your billing information and payment details, then click **Submit**.

   During checkout, GitHub may place a temporary authorization hold on your payment method to verify it. This hold is not the subscription charge.

   If payment method verification does not succeed, or if you do not complete the activation step on the next screen, your plan will not activate.

6. After reviewing your plan details, click **Activate Copilot Pro/Copilot Pro+/Copilot Max**.

## Troubleshooting

### Account still shows Copilot Free after checkout

If the plan does not appear after following the checkout steps [when subscribing](#subscribing-to-copilot-pro-copilot-pro-or-copilot-max), follow these further steps to confirm and recover your subscription.

1. Confirm that the plan appears in your GitHub Copilot settings or in your personal account settings under **Billing & licensing**. For more information, see [Viewing and changing your GitHub Copilot plan](/en/copilot/how-tos/manage-your-account/view-and-change-your-copilot-plan).
2. If payment method verification failed or you did not complete the activation step, retry the checkout flow.
3. If you completed activation and the plan still does not appear, contact [GitHub Support](https://support.github.com).

### Blocked plan setup on a personal account

Your personal account may have a Copilot access restriction if you see:

* "It appears you are not eligible to sign up for GitHub Copilot Free"
* "Your account is unable to sign up for Copilot. Please contact Support"
* An upgrade that does not complete
* Editor errors that tell you to contact support, or that mention a 403 token error

First check the relevant guidance: [Accessing Copilot Free](#accessing-copilot-free) for eligibility issues, or [Account still shows Copilot Free after checkout](#account-still-shows-copilot-free-after-checkout) for paid upgrades. If those cases do not apply, these messages can indicate an account restriction rather than normal eligibility, checkout, or usage-limit issues.

If your account has a Copilot access restriction, contact [GitHub Support](https://support.github.com) and request an account review. You cannot remove the restriction yourself.

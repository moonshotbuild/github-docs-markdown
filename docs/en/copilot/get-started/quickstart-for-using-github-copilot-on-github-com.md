---
source_path: "/en/copilot/get-started/quickstart-for-using-github-copilot-on-github-com"
title: "Quickstart for using GitHub Copilot on GitHub.com"
intro: "Understand code and work faster by asking questions and assigning coding tasks to Copilot in the cloud without leaving GitHub."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "Get started"
    href: "/en/copilot/get-started"
  - title: "Copilot on GitHub.com"
    href: "/en/copilot/get-started/quickstart-for-using-github-copilot-on-github-com"
---

# Quickstart for using GitHub Copilot on GitHub.com

Understand code and work faster by asking questions and assigning coding tasks to Copilot in the cloud without leaving GitHub.

GitHub Copilot is built into GitHub, so you can use it without installing anything.

This quickstart takes about fifteen minutes and shows how to ask questions about a repository, request and review a code change, and continue your work on GitHub Mobile with Copilot.

## Prerequisites

* For Task 1, you need read access to a repository, such as the public [github/docs](https://github.com/github/docs?utm_source=dotcom-quickstart-os-docs-repo\&utm_medium=docs\&utm_campaign=universe-2026) repository.
* For Tasks 2 and 3, you need write access to a repository. We recommend using a repository that you own or have permission to make changes to.
* To complete each task in this quickstart, Copilot must be available for your account and enabled for the repository you will use. For setup guidance, see [Enable Copilot](/en/copilot/how-tos/copilot-on-github/set-up-copilot/enable-copilot).
* To perform Task 3, you need to have GitHub Mobile installed and set up for your account. See [GitHub Mobile](/en/get-started/using-github/github-mobile).

## Task 1: Ask Copilot questions about a repository

1. [Start a session with Copilot](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&utm_source=dotcom-quickstart-start-session-cta\&utm_medium=docs\&utm_campaign=universe-2026), from the Copilot home page.
2. Below the prompt box, open the **Chat** session scope picker.
3. Under **Work in a repository**, search for and select the repository you want to explore.
   * If you need a repository to try, use the public [github/docs](https://github.com/github/docs?utm_source=dotcom-quickstart-os-docs-repo\&utm_medium=docs\&utm_campaign=universe-2026) repository.
4. If a specific file, issue, or pull request is relevant, type `@` in the prompt box and select it from the suggestions. This gives Copilot a specific place to look for context.
5. Ask a question about the repository. For example:

   ```copilot copy
   I'm new to github/docs. How is this repository organized,
   and where should I start to understand how the site is built?
   ```

   ```copilot copy
   In /package.json, which scripts look relevant for validating
   a change, and what command does each run?
   ```

   ```copilot copy
   What behavior does
   /src/color-schemes/tests/color-mode-script.ts cover?
   Suggest one additional test case that would fit the
   existing tests, and explain why.
   ```

   To create a prompt from the above examples, select **Copy**, and paste it into the prompt box. Then press <kbd>Enter</kbd> to send the prompt.

   Copilot's answer appears in the conversation. Ask a focused question about a file, feature, or error to get a more useful answer.
6. Ask a follow-up question by typing it in the same prompt box and pressing <kbd>Enter</kbd>. The conversation gives Copilot context for your next question.

## Task 2: Request and review a code change

1. [Start a session with Copilot](https://github.com/copilot?ref_product=copilot\&ref_type=engagement\&ref_style=text\&utm_source=dotcom-quickstart-start-session-cta-2\&utm_medium=docs\&utm_campaign=universe-2026), from your Copilot home page.
2. In a repository where you have write access, use the **Chat** session scope picker and select the repository under **Work in a repository**.
3. Request a code change. State the result you want and any relevant file or behavior. For example, copy and send this prompt:

   ```copilot copy
   Add a small ASCII art image to the top of the README file.
   ```

   Paste the prompt into the prompt box and press <kbd>Enter</kbd> to send it. Copilot works on the task in the background.

   > [!IMPORTANT]
   > Review all Copilot requests for permissions or action, before allowing changes.
4. As Copilot works on the request, you can continue to interact with the session. You can also expand each of the steps Copilot takes in the session log to see the work performed and tools used.
5. When Copilot finishes, it will display the changes above the prompt box, and present an option to create a pull request.
6. Click **Changes** to view the proposed changes.
7. To make further changes, type a follow-up request in the same prompt box and press <kbd>Enter</kbd>. The session retains the context from your earlier prompts.
8. Click **Create pull request**, then click the **View PR** link to view your changes.

Proceed to Task 3 to continue your session in GitHub Mobile.

## Task 3: Continue your session in GitHub Mobile

1. Open GitHub Mobile on your device.
2. From the home page, tap the **<svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-copilot" aria-label="Copilot" role="img"><path d="M7.998 15.035c-4.562 0-7.873-2.914-7.998-3.749V9.338c.085-.628.677-1.686 1.588-2.065.013-.07.024-.143.036-.218.029-.183.06-.384.126-.612-.201-.508-.254-1.084-.254-1.656 0-.87.128-1.769.693-2.484.579-.733 1.494-1.124 2.724-1.261 1.206-.134 2.262.034 2.944.765.05.053.096.108.139.165.044-.057.094-.112.143-.165.682-.731 1.738-.899 2.944-.765 1.23.137 2.145.528 2.724 1.261.566.715.693 1.614.693 2.484 0 .572-.053 1.148-.254 1.656.066.228.098.429.126.612.012.076.024.148.037.218.924.385 1.522 1.471 1.591 2.095v1.872c0 .766-3.351 3.795-8.002 3.795Zm0-1.485c2.28 0 4.584-1.11 5.002-1.433V7.862l-.023-.116c-.49.21-1.075.291-1.727.291-1.146 0-2.059-.327-2.71-.991A3.222 3.222 0 0 1 8 6.303a3.24 3.24 0 0 1-.544.743c-.65.664-1.563.991-2.71.991-.652 0-1.236-.081-1.727-.291l-.023.116v4.255c.419.323 2.722 1.433 5.002 1.433ZM6.762 2.83c-.193-.206-.637-.413-1.682-.297-1.019.113-1.479.404-1.713.7-.247.312-.369.789-.369 1.554 0 .793.129 1.171.308 1.371.162.181.519.379 1.442.379.853 0 1.339-.235 1.638-.54.315-.322.527-.827.617-1.553.117-.935-.037-1.395-.241-1.614Zm4.155-.297c-1.044-.116-1.488.091-1.681.297-.204.219-.359.679-.242 1.614.091.726.303 1.231.618 1.553.299.305.784.54 1.638.54.922 0 1.28-.198 1.442-.379.179-.2.308-.578.308-1.371 0-.765-.123-1.242-.37-1.554-.233-.296-.693-.587-1.713-.7Z"></path><path d="M6.25 9.037a.75.75 0 0 1 .75.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 .75-.75Zm4.25.75v1.501a.75.75 0 0 1-1.5 0V9.787a.75.75 0 0 1 1.5 0Z"></path></svg>** icon in the bottom right corner of the screen.
3. Under the list of recent sessions, tap the name of the session you created above. The name is often based on the first prompt you sent. In this example, it may be something like `README ascii art`.
4. Click on **View PR**, and then **Files changed**, to review the proposed changes again.
5. Optionally, to request another change, click the affected line. Add a comment that mentions `@copilot` and describes what to change. Then select **Comment** and click **Finish your review** so Copilot can see and act on your request.

   Copilot will acknowledge your comment with a reaction, and start a session to make the requested changes if possible. Timeline events on the pull request page will show when Copilot is finished, and Copilot will request your review again as well as reply to your previous comment with the results.
6. When you are happy with your pull request, you must **Mark as ready for review**.
7. Review the changes made by Copilot to ensure they meet your expectations. If needed, click **Approve** and then **Finish your review**, to bring the PR to a merge-ready state.
8. Click **Merge** to merge the pull request.

   Next, let's check to see your updated README file.
9. Return to your **Home** on GitHub Mobile to search for your repository, and open it.
10. Scroll to the bottom of the page to view the repository's README, and admire your artwork!

## Next steps

* [Using Copilot in the cloud on GitHub](/en/copilot/how-tos/use-copilot-agents/cloud-agent/use-cloud-agent-on-github)
* [Viewing and estimating your spending](/en/billing/how-tos/products/estimate-spending)
* [Monitoring your GitHub AI Credits usage](/en/copilot/how-tos/manage-and-track-spending/monitor-ai-usage)

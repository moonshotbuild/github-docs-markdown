---
source_path: "/en/copilot/how-tos/administer-copilot/view-impact-dashboard"
title: "Viewing the Copilot impact dashboard"
intro: "The impact dashboard shows how deeply your organization has adopted Copilot, and how that adoption connects to pull request output."
product: "GitHub Copilot"
document_type: "article"
breadcrumbs:
  - title: "GitHub Copilot"
    href: "/en/copilot"
  - title: "How-tos"
    href: "/en/copilot/how-tos"
  - title: "Administer Copilot"
    href: "/en/copilot/how-tos/administer-copilot"
  - title: "View impact dashboard"
    href: "/en/copilot/how-tos/administer-copilot/view-impact-dashboard"
---

# Viewing the Copilot impact dashboard

The impact dashboard shows how deeply your organization has adopted Copilot, and how that adoption connects to pull request output.

Instead of a flat active-user count, the impact dashboard groups users into adoption cohorts based on how they engage with Copilot, and connects that engagement to pull request throughput. This gives you a more meaningful signal of adoption depth than daily or weekly active user counts alone.

For a detailed explanation of what the dashboard shows, including adoption cohorts, engagement trends, potential return on investment, and recommendations, see [GitHub Copilot usage metrics](/en/copilot/concepts/billing-and-usage/copilot-usage-metrics/copilot-metrics).

## Prerequisite

To access Copilot usage metrics, the **"Copilot usage metrics"** policy must be enabled:

* [Managing policies and features for GitHub Copilot in your enterprise](/en/copilot/how-tos/administer-copilot/manage-for-enterprise/manage-enterprise-policies#defining-policies-for-your-enterprise)
* [Managing policies and features for GitHub Copilot in your organization](/en/copilot/how-tos/administer-copilot/manage-for-organization/manage-policies#enabling-copilot-features-and-models-in-your-organization)

## Accessing the dashboard

1. Navigate to your enterprise. For example, from the [Enterprises](https://github.com/settings/enterprises?ref_product=ghec\&ref_type=engagement\&ref_style=text) page on GitHub.com.
2. Click the **Insights** tab.
3. In the left sidebar, click **Copilot impact**.

## Comparing your impact with peers

The **Industry comparison** widget shows how your agentic adoption and leverage compare with participating peers. Industry comparisons are available for enterprises and for organizations that aren't owned by an enterprise. Organizations owned by an enterprise participate through their enterprise, and enterprises used only to assign Copilot Business licenses can't participate, because leverage can't be calculated for them.

### Opting in to industry comparisons

Participation is controlled by the **Copilot metrics industry comparison** policy, which is disabled by default. When the policy is enabled, your enterprise or organization contributes aggregated Copilot metrics to peer cohorts and can view comparisons. When it's disabled, you don't contribute data or see comparisons.

Enterprise owners, and owners of organizations that aren't owned by an enterprise, can opt in from the widget or by enabling the policy. The widget and the policy use the same setting.

1. In the **Industry comparison** widget, click **Opt-in for industry comparison** and review the information about how your data is used.
2. Select values from the **Industry type** and **Company size** dropdown menus. Both values are required to create a peer cohort.
3. Click **Opt in**.

### Viewing industry comparisons

1. Use the scope selector to switch between **All industries** and your selected industry.
2. Review the comparison cards for the selected 28-day reporting period:
   * **Your agentic adoption** shows the percentage of active users who are agent-first or multi-agent users.
   * **Your leverage** compares the pull request merge rate per user per month for agentic users with the rate for non-agentic users.
3. For each card, review your percentile ranking and your difference from the peer median and, if shown, the top decile. The ranking line shows the peer cohort used for the comparison. Use the chart to see your score, the peer median, and the top decile within the peer distribution.

Rankings appear only after enough enterprises and organizations have opted in to form a peer cohort. The median comparison is shown first, and the top-decile comparison is added when the cohort grows larger. If your selected industry doesn't have enough participants yet, the dashboard compares you with peers of the same company size across all industries. If that cohort doesn't have enough participants either, the dashboard doesn't show a ranking. Especially soon after launch, you might see only the median, all industries instead of your selected industry, or no ranking until more peers opt in.

A ranking also isn't shown when your own score can't be calculated for the reporting period. For example, there might be no active users, or all active users might already be agent-first or multi-agent users, leaving no non-agentic users to compare leverage with.

For details about what data is shared and how it's protected, see [GitHub Copilot usage metrics](/en/copilot/concepts/copilot-usage-metrics/copilot-metrics#how-industry-comparisons-protect-your-data).

### Changing your peer cohort or opting out

To change your peer cohort, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="Industry comparison settings" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> in the widget, then choose a different industry or company size. The widget uses your new selection right away, and your data moves to the new peer cohort with the next daily update.

To stop participating, click <svg version="1.1" width="16" height="16" viewBox="0 0 16 16" class="octicon octicon-gear" aria-label="Industry comparison settings" role="img"><path d="M8 0a8.2 8.2 0 0 1 .701.031C9.444.095 9.99.645 10.16 1.29l.288 1.107c.018.066.079.158.212.224.231.114.454.243.668.386.123.082.233.09.299.071l1.103-.303c.644-.176 1.392.021 1.82.63.27.385.506.792.704 1.218.315.675.111 1.422-.364 1.891l-.814.806c-.049.048-.098.147-.088.294.016.257.016.515 0 .772-.01.147.038.246.088.294l.814.806c.475.469.679 1.216.364 1.891a7.977 7.977 0 0 1-.704 1.217c-.428.61-1.176.807-1.82.63l-1.102-.302c-.067-.019-.177-.011-.3.071a5.909 5.909 0 0 1-.668.386c-.133.066-.194.158-.211.224l-.29 1.106c-.168.646-.715 1.196-1.458 1.26a8.006 8.006 0 0 1-1.402 0c-.743-.064-1.289-.614-1.458-1.26l-.289-1.106c-.018-.066-.079-.158-.212-.224a5.738 5.738 0 0 1-.668-.386c-.123-.082-.233-.09-.299-.071l-1.103.303c-.644.176-1.392-.021-1.82-.63a8.12 8.12 0 0 1-.704-1.218c-.315-.675-.111-1.422.363-1.891l.815-.806c.05-.048.098-.147.088-.294a6.214 6.214 0 0 1 0-.772c.01-.147-.038-.246-.088-.294l-.815-.806C.635 6.045.431 5.298.746 4.623a7.92 7.92 0 0 1 .704-1.217c.428-.61 1.176-.807 1.82-.63l1.102.302c.067.019.177.011.3-.071.214-.143.437-.272.668-.386.133-.066.194-.158.211-.224l.29-1.106C6.009.645 6.556.095 7.299.03 7.53.01 7.764 0 8 0Zm-.571 1.525c-.036.003-.108.036-.137.146l-.289 1.105c-.147.561-.549.967-.998 1.189-.173.086-.34.183-.5.29-.417.278-.97.423-1.529.27l-1.103-.303c-.109-.03-.175.016-.195.045-.22.312-.412.644-.573.99-.014.031-.021.11.059.19l.815.806c.411.406.562.957.53 1.456a4.709 4.709 0 0 0 0 .582c.032.499-.119 1.05-.53 1.456l-.815.806c-.081.08-.073.159-.059.19.162.346.353.677.573.989.02.03.085.076.195.046l1.102-.303c.56-.153 1.113-.008 1.53.27.161.107.328.204.501.29.447.222.85.629.997 1.189l.289 1.105c.029.109.101.143.137.146a6.6 6.6 0 0 0 1.142 0c.036-.003.108-.036.137-.146l.289-1.105c.147-.561.549-.967.998-1.189.173-.086.34-.183.5-.29.417-.278.97-.423 1.529-.27l1.103.303c.109.029.175-.016.195-.045.22-.313.411-.644.573-.99.014-.031.021-.11-.059-.19l-.815-.806c-.411-.406-.562-.957-.53-1.456a4.709 4.709 0 0 0 0-.582c-.032-.499.119-1.05.53-1.456l.815-.806c.081-.08.073-.159.059-.19a6.464 6.464 0 0 0-.573-.989c-.02-.03-.085-.076-.195-.046l-1.102.303c-.56.153-1.113.008-1.53-.27a4.44 4.44 0 0 0-.501-.29c-.447-.222-.85-.629-.997-1.189l-.289-1.105c-.029-.11-.101-.143-.137-.146a6.6 6.6 0 0 0-1.142 0ZM11 8a3 3 0 1 1-6 0 3 3 0 0 1 6 0ZM9.5 8a1.5 1.5 0 1 0-3.001.001A1.5 1.5 0 0 0 9.5 8Z"></path></svg> in the widget and select **Opt-out** or set the **Copilot metrics industry comparison** policy to **Disabled**. The dashboard stops showing comparisons immediately, and your data is excluded from peer cohorts starting with the next daily update. Previously calculated aggregate results don't identify your enterprise or organization and are deleted after 30 days.

## Estimating potential return on investment

The "Potential return on investment" section provides a directional comparison of cost and pull request output across adoption phases.

1. Under "Average developer cost in your organization", select a compensation band.
2. In the "Transition your developers to be agent-first" card, compare the cost, payroll, and pull request estimates for "Phase 0-1 Passive and Code First Users" and "Phase 2-3 Agent First Users".

Treat the figures as directional estimates rather than exact financial results. Use them with the adoption multiplier metrics for code shipped and time to merge pull requests.

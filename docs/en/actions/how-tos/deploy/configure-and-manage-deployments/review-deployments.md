---
source_path: "/en/actions/how-tos/deploy/configure-and-manage-deployments/review-deployments"
title: "Reviewing deployments"
intro: "You can approve or reject jobs awaiting review."
product: "GitHub Actions"
document_type: "article"
breadcrumbs:
  - title: "GitHub Actions"
    href: "/en/actions"
  - title: "How-tos"
    href: "/en/actions/how-tos"
  - title: "Deploy"
    href: "/en/actions/how-tos/deploy"
  - title: "Configure and manage deployments"
    href: "/en/actions/how-tos/deploy/configure-and-manage-deployments"
  - title: "Review deployments"
    href: "/en/actions/how-tos/deploy/configure-and-manage-deployments/review-deployments"
---

# Reviewing deployments

You can approve or reject jobs awaiting review.

## Approving or rejecting a job

1. Navigate to the workflow run that requires review. For more information about navigating to a workflow run, see [Viewing workflow run history](/en/actions/how-tos/monitor-workflows/view-workflow-run-history).
2. If the run requires review, you will see a notification for the review request. On the notification, click **Review deployments**.
3. Select the job environment(s) to approve or reject. Optionally, leave a comment.
4. Approve or reject:
   * To approve the job, click **Approve and deploy**. Once a job is approved (and any other deployment protection rules have passed), the job will proceed. At this point, the job can access any secrets stored in the environment.
   * To reject the job, click **Reject**. If a job is rejected, the workflow will fail.

> \[!NOTE]
> If the targeted environment is configured to prevent self-approvals for deployments, you will not be able to approve a deployment from a workflow run you initiated. For more information, see [Managing environments for deployment](/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments).

## Bypassing deployment protection rules

If you have configured deployment protection rules that control whether software can be deployed to an environment, you can bypass these rules and force all pending jobs referencing the environment to proceed.

> \[!NOTE]
>
> * You cannot bypass deployment protection rules if the environment has been configured to prevent admins from bypassing configured protection rules. For more information, see [Managing environments for deployment](/en/actions/how-tos/deploy/configure-and-manage-deployments/manage-environments#creating-an-environment).
> * You can only bypass deployment protection rules during workflow execution when a job referencing the environment is in a "Pending" state.

1. Navigate to the workflow run. For more information about navigating to a workflow run, see [Viewing workflow run history](/en/actions/how-tos/monitor-workflows/view-workflow-run-history).
2. To the right of **Deployment protection rules**, click **Start all waiting jobs**.
   ![Screenshot of the "Deployment protection rules" section with the "Start all waiting jobs" button outlined in orange.](/assets/images/actions-bypass-env-protection-rules.png)
3. In the pop-up window, select the environments for which you want to bypass deployment protection rules.
4. Under **Leave a comment**, enter a description for bypassing the deployment protection rules.
5. Click **I understand the consequences, start deploying**.

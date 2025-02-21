---
title: Process sales quotes and orders with Sales Order Agent (preview)
description: Learn how to work with the Sales Order Agent to process sales quotes and orders from customer requests made via email.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.collection:
  - bap-ai-copilot
ms.date: 12/16/2024
ms.custom: bap-template
ms.search.form: 4400, 4410_Primary
---
# Process sales quotes and orders with Sales Order Agent (preview)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

This article explains how to use the Sales Order Agent to automate taking sales orders based on customer inquiries about products/items received via email.

The Sales Order Agent monitors a designated mailbox for incoming customer emails about item inquiries. When it identifies a potential request, it starts converting the request into an order. For example, it verifies the customer, checks item availability, creates a sales quote, and prepares an email response to the customer with the quote as a PDF attachment.

Some steps require your intervention, such as reviewing email correspondence and assisting the agent as needed. Until an order is created, the agent handles email exchanges with the customer to resolve any missing details and allow for modifications to the original request if necessary.

Learn more about the Sales Order Agent and its process flow in [Sales Order Agent overview](sales-order-agent.md#how-the-agent-processes-requests).

[!INCLUDE [limited-public-preview](includes/limited-public-preview.md)]

<!--[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]-->

## Prerequisites

The Sales Order Agent is activated, and you have permission to use it. Learn more in [Set up Sales Order Agent](sales-order-agent-setup.md).

## Get started

You collaborate with the Sales Order Agent to review and convert quotes into orders using the **Tasks** tab in the **Copilot** pane.

To access this view, select ![Shows Sales Order Agent icon with an open action.](media/soa-activated-number-icon.png) **Sales Order Agent** on the upper right of the navigation menu. A red circle with a number on the icon indicates the tasks that need attention.

![Shows the task view with steps](media/soa-task-view-callouts.png)

The ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** tab opens in the **Copilot** pane to display tasks recently created by the Sales Order Agent. Tasks that require attention&mdash;like reviewing an incoming or outgoing email&mdash;are at the top of the list.  

For each sales quote request, the Sales Order Agent adds a task to track, review, and follow up on updates, eventually processing the quote into an order. Tasks can consist of multiple steps that form a timeline of the process.

> [!TIP]
> Hover over the **Sales Order Agent** icon on the role center to get an overview of the agent's KPIs (Key Performance Indicators) summarizing the impact of the agent's work in your organization. For example, view the number of sales quotes or orders created by the agent, the time saved by your team, and the total amount of sales orders created.

## Review and assist

While the agent does the bulk of work autonomously, it asks for user intervention when required for various steps to move through the process, such as:

- Reviewing and confirming incoming email requests from customers.
- Reviewing and confirming the sales quotes and orders if an admin configured the Sales Order Agent to do so.
- Reviewing outgoing emails created by the Sales Order Agent for the customer.
- Providing assistance to the Sales Order Agent when it needs to get unblocked, for example to provide missing data.

Steps requiring intervention are listed under **Needs Attention** in the **Tasks** tab. To review a step:

1. In **Task** tab, select the step requesting review or assistance.

   The task *timeline* opens, focused on the selected step. The timeline displays each step of a task, past and present, in chronological order.

1. Select **Review** for the step.

   The **Tasks** tab switches to **Review** mode, and the Agent Task Message window opens to display the email contents or quote or order, depending on the task.

1. Review the email contents or the quote or order and make changes as needed. You can't edit incoming emails from the customer.

1. When you're satisfied with the content and want the process to continue, select **Confirm** in the **Review** pane. If you want to complete the task yourself, select **Stop** to halt the agent's processing of this task.

After confirmation, the Sales Order Agent continues processing the task. When a new notification appears on the Sales Order Agent icon after some time, follow the same flow to verify and approve the results.

## Modify sales quotes and orders

You might need to modify sales quotes or orders created by the agent during a review step or when the agent requests assistance, based on its configuration. When you select **Review**, the quote or order opens for inspection. Make changes as needed, then select **Confirm** in the **Review** pane. The agent processes the document, creating a PDF for the outgoing email to the customer.

You also have the opportunity to modify a quote or order during the review step for an outgoing email. In this case, select **...** (More options) > **Discard step** on the step. This action stops the task temporarily to allow you to open the quote or order and makes changes and then resume the step.

![Shows the discard step acion on a sales order agent task.](media/soa-discard-step.png)

> [!NOTE]
> **Discard step** is available only on review steps for outgoing emails.

After you make the changes, return to the **Tasks** tab, select one of the following options for resuming the task, and then select **Send**:

- **I have updated the quote** or **I have updated the order** - Select one of these options if you made changes to the quote or order. The agent generates a new PDF and email for the customer.
- **Just resume** - Select this option if you didn't change the quote or order. The agent doesn't generate a new quote or order and keeps the original email as before.  

![Shows the resume step acion on a sales order agent task.](media/soa-resume-step.png)

If you change your mind while reviewing the outgoing message and decide to make more changes to the sales document, use the **Discard step** action to discard the email message generated by the agent. Then, update the sales document as needed and instruct the agent to create a new outgoing email with the updated attachment.

## Stop a task

Most steps of a task include a **Stop** button that lets you terminate the process. When you select **Stop**, a task isn't terminated immediately—you're asked to confirm before the task is stopped.

Before you stop a task, consider the following behavior:

- Stopped tasks can't be restarted.
- Stopping the task might leave some results incomplete or unwanted, and it might require follow-up actions with the customers. Follow up actions depend on where in the process the task was stopped.

  For example, suppose you stopped a task after a sales quote was created. Although the process stopped, the sales quote is still stored in the system as open. You might have to manually edit the state depending on your company policy and then update the customer.
- Stopped tasks aren't deleted immediately. You can still explore a task's timeline until it's deleted, typically by an administrator.

<!--
## Discard and resume a taks to modify a quote or order

The **Discard**  action ellwo

## View timeline and details of steps

From the ![Shows the task view icon](media/sot-task-view-icon.png) **Tasks** view, you can view the details of each step of a task in chronological order. Click on the task or select **...** (More options) > **Show Details**.-->

## Related information

[Sales order agent overview](sales-order-agent.md)  
[Set up the Sales Order Agent](sales-order-agent-setup.md)  
[FAQ for Sales Order Agent](faqs-sales-order-taker-agent.md)  
[Configure Copilot and AI capabilities](enable-ai.md)  

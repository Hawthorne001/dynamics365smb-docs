---
title: Synchronize Contacts in Business Central with Contacts in Microsoft Outlook
description: This service has deep integration with Microsoft 365 so you can share contacts between Outlook and Business Central.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: contacts, Microsoft 365
ms.search.form: 6700, 5320, 5300, 5301, 5302, 5303, 5304, 5305, 5306, 5307, 5308, 5309, 5310, 5311 
ms.date: 05/21/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Synchronize contacts in Business Central with contacts in Microsoft Outlook

You can set up contact synchronization so that your contacts in [!INCLUDE[prod_short](includes/prod_short.md)] have the same information as your contacts in Microsoft Outlook. For example, if you're a sales person, you might work in Outlook and [!INCLUDE[prod_short](includes/prod_short.md)] at the same time. If the contacts are the same in both places, your work is more straightforward.  

By default, the contacts you're syncing are kept in a **Business Central** folder in your Favorites on the Folder Pane in Outlook. The Business Central folder can make it easier to identify which contacts you're syncing. You can set filters to sync only specific contacts from [!INCLUDE[prod_short](includes/prod_short.md)] to Outlook. After you set up synchronization, you can synchronize manually or automate the process to synchronize on a scheduled basis.  

## Prerequisites

- Your user account in [!INCLUDE[prod_short](includes/prod_short.md)] must specify your Microsoft 365 email account.

  You can check this setting in the **Microsoft 365** section of your **User Card**, which you open from the **Users** list.
- With [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you set up contact synchronization as described in [Set Up contact synchronization with Outlook for Business Central on-premises](admin-contact-sync-setup-onprem.md).

## Set up synchronization

You set up how you want to synchronize contacts with Outlook on the **Exchange Sync. Setup** page in [!INCLUDE[prod_short](includes/prod_short.md)]. 

On the **Exchange Sync. Setup** page, you can validate that the connection to Exchange is working and then set up contact synchronization. From the **Exchange Sync. Setup** page, you can open the **Contact Sync. Setup** page and start the synchronization. Optionally, set a filter to specify which contacts to synchronize. For example, you can filter on name, type, company, and so on. You can also change the default name of the folder in Outlook that the contacts synchronize to.  

Each of your coworkers can also set up their own Exchange synchronization and set their own filters on which contacts to synchronize.  

After you set up synchronization, sync changes manually. Business Central versions 2023 release wave 2 and earlier support automated synchronization. Learn more about automation in the next section of this article.



## Synchronize contacts

To sync contacts, select one of these actions on the **Exchange Sync. Setup** page:

- **Sync with Microsoft 365**

  Synchronize all changes from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft 365 that were made after the last synchronization, based on the last modified date. Also, new contacts from Microsoft 365 are synchronized to [!INCLUDE[prod_short](includes/prod_short.md)]. Typically, this action is faster than a full sync. 

- **Full Sync with Microsoft 365**

  Synchronize all contacts in both directions, regardless of the last sync date and last modified date.  

In both cases, contacts are only synchronized from Outlook if they have the required fields filled in. The required fields to synchronize to Microsoft 365 are **Name**, **Email address** and the contact must be of the type **Person**. [!INCLUDE[prod_short](includes/prod_short.md)] is the source of the contact information, so the [!INCLUDE[prod_short](includes/prod_short.md)] contact information is saved if there are duplicates.  

> [!NOTE]
> If you delete a contact in Outlook, but keep it in [!INCLUDE[prod_short](includes/prod_short.md)], the contact will be recreated in Outlook the next time you sync.

### Automate synchronization (background synchronization)

> [!IMPORTANT]
> Starting in 2024 release wave 1 (version 24), you can't turn on background synchronization anymore. If it's currently on, it works as expected. If you turn it off, you can't turn it on again.

To automate sync, if the **Enable Background Synchronization** toggle is on, create a job queue entry to sync contacts on a schedule you set. Learn more in [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).

The following table lists the settings on the **Job Queue Entry Card** page for syncing contacts:

|Field|Setting for contact sync|
|-----|-----|
|Object Type to Run|Codeunit|
|Object ID to Run|6700|

## Step-by-step guide to sync contacts

You sync contacts from the **Contacts** list page. When you sync contacts you can choose to sync only changes from [!INCLUDE[prod_short](includes/prod_short.md)] to Microsoft 365 that were made after the last synchronization, based on the last modified date. Also, new contacts from Microsoft 365 are synchronized to [!INCLUDE[prod_short](includes/prod_short.md)]. Typically, this action is faster than a full sync. 

- **Full Sync with Microsoft 365**

  Synchronize all contacts in both directions, regardless of the last sync date and last modified date.  


### Perform a full synchronization

A full synchronization synchronizes all contacts regardless of the last sync date and last modified date. Follow these steps:

1. In [!INCLUDE[prod_short](includes/prod_short.md)], [!INCLUDE[open-search-lowercase](includes/open-search-lowercase)], enter *contacts*, and then choose the related links. 
1. In the **Contacts** page, select the **Synchronize with Outlook...** action.

   The **Synchronize contacts** assisted setup guide opens.
1. Choose **Next** to proceed to the synchronization options.
1. On Enable **Force full sync**.
   
   Set the Force full sync field to true to synchronize all contacts in both directions.

5. Choose **Next** to continue.
   
   The system searches for contacts to synchronize. You'll see a message indicating how many contacts were found (for example, "Found 10 contacts").

6. Select the sync direction in the **What to update** field.
   
   Choose the appropriate option for your synchronization needs:
   - Update contacts in both systems
   - Update only in Microsoft 365
   - Update only in [!INCLUDE[prod_short](includes/prod_short.md)]

7. Choose **Synchronize** to start the synchronization.
   
   After the synchronization completes, you'll see a confirmation message (for example, "10 contacts have been synchronized successfully.").

8. Choose **Close** to close the synchronization page.

### Perform a regular (non-full) synchronization

A regular synchronization only synchronizes changes made since the last synchronization, based on the last modified date. Follow these steps:

1. Open the **Contact List** page.
   
   Navigate to Contacts in [!INCLUDE[prod_short](includes/prod_short.md)].

2. Choose the **Synchronize with Outlook...** action.
   
   The **Synchronize contacts** page opens.

3. Choose **Next** twice to skip the full sync option.
   
   Leave the Force full sync field blank or set to false.

4. The system searches for contacts that changed since the last synchronization.
   
   If no contacts are found in the selected folder, you'll see the message "No contacts found in the selected folder to Synchronize."

5. If contacts are found, select the sync direction in the **What to update** field.

6. Choose **Synchronize** to start the synchronization.

> [!NOTE]
> If you attempt to synchronize when no contacts are found or required fields are missing, an error dialog will appear. Make sure your contacts have the required fields filled in before attempting to synchronize.

## Related information

[Getting Ready for Doing Business](ui-get-ready-business.md)  
[Finance](finance.md)  
[Sales](sales-manage-sales.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Use contacts (People) in Outlook on the web](https://support.office.com/article/Using-contacts-People-in-Outlook-on-the-web-1e3438c7-26b2-420c-87de-3cea9d31b5cb?appver=OWB150)  


[!INCLUDE[footer-include](includes/footer-banner.md)]

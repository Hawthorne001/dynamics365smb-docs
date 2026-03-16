---
title: Calculate withholding tax for vendors
description: This article describes how to calculate withholding tax for your vendors.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: withholding, tax, sales, purchases
ms.search.form: 
ms.date: 03/06/2026
ms.custom: bap-template
---

# Calculate withholding tax for vendors

Companies in some countries/regions must pay withholding tax to the government for certain services or vendor purchases. [!INCLUDE [prod_short](includes/prod_short.md)] calculates withholding tax for purchase invoices and orders, based on your setup for withholding tax. The tax amount is withheld from the payment and reduces the total amount you owe to the vendor.

## Set up vendors for withholding tax

To include a vendor in withholding tax calculations, on the **Vendor Card** page, turn on the **Withholding Tax Liable** toggle. Then, in the **Withholding Tax Bus. Post. Group** field, specify the general ledger account to which to post tax amounts.

## Using withholding tax

If the vendor, item, and G/L account are set up for withholding tax, [!INCLUDE [prod_short](includes/prod_short.md)] automatically calculates the tax amount when you post purchase documents that include them on their lines. However, it only creates a withholding tax entry if the value is more than the minimum threshold in the posting setup you created for withholding tax. Learn more at [Create a posting setup for withholding tax](finance-set-up-withholding-tax.md#create-a-posting-setup-for-withholding-tax). 

You can also use the **Calculate and post withholding tax settlements** action to process withholding tax for a specific period based on the withholding tax entries you already posted.

### Calculate and post withholding tax settlements

You can use the **Calculate and Post Withholding Tax Settlement** page to calculate and post the withholding tax amount.

You can close withholding tax entries that are open or not settled and transfer the corresponding amount to the withholding tax settlement account.

The sum of all withheld amounts is reported as a truncated whole number to the tax authorities.

> [!NOTE]
> The smaller truncated amounts are accounted for in a rounding account.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Calculate and Post Withholding Tax Settlement**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Starting Date | The start date of the period for which to settle withholding tax. |
   | Ending Date | The end date of the period for which to settle withholding tax. |
   | Posting Date | The posting date of the withholding tax settlement entries. |
   | Document No. | The document number of the withholding tax settlement entries. |
   | Description | The withholding tax settlement description. |
   | Settlement Account Type | The settlement account type. |
   | Settlement Account | The account number based on the account type selected in the **Settlement Account Type** field. |
   | Rounding G/L Account | The account you post the truncated amount to. |
   | Show Withholding Tax Entries | Review the withholding tax entries for the specified period. |
   | Post | Select to post the withholding tax settlement entries. |
   | Print | Choose the **Print** button to print the report, or choose the **Preview** button to review it first. |

## Related information

[Set up withholding tax](finance-set-up-withholding-tax.md)  
[View withholding tax entries](finance-withholding-tax-entries.md)  

[Financial management](finance.md)  

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

Companies in some countries/regions must pay withholding tax to the government for certain services or vendor purchases. [!INCLUDE [prod_short](includes/prod_short.md)] calculates withholding tax when you pay a vendor invoice, or when you post it, based on your setup. The tax amount is withheld from the payment and reduces the total amount owed to the vendor.

You can configure withholding tax by setting up **Withholding Tax Codes** and **Vendors**.

## Get started

To enable withholding tax calculation, open the **General Ledger Setup** page and turn on the **Enable Withholding Tax** toggle. Next, configure the **Withholding Tax Revenue Types**, including their sequences and posting groups. Then, set up the following:

- **Withholding Tax Bus. Post. Group** and apply it to vendors that are subject to withholding tax.
- **Withholding Tax Prod. Post. Group** and apply it to items or general ledger accounts.  
- **Withholding Tax Posting Setup** (using the two groups above)

If needed, you can override the product posting group on purchase document lines using the **Withholding Tax Prod. Post. Group** field.

### Set up withholding tax posting groups

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct withholding tax calculations are made for each vendor.

> [!NOTE]
> As a prerequisite, you must set up source codes for withholding tax settlement on the Source Code Setup page. Learn more in [Setting Up Source Codes and Reason Codes for Audit Trails](finance-setup-trail-codes.md).

### Set up a product posting group for withholding tax

The following procedure describes how to set up product posting groups for withholding tax, but the same steps also apply to setting up business posting groups for withholding tax.

1. Choose the Tell Me feature icon, enter **Withholding Tax Product Posting Group**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specify the code for the product posting group. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specify the description for the product posting group. You can enter a maximum of 50 alphanumeric characters. |
   
1. Choose the OK button.

### Set up posting for withholding tax

Finally, you must set up how these posting groups must be used when documents are posted.

1. Choose the Tell Me feature icon, enter **Withholding Tax Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | withholding tax Business Posting Group | Specifies the business posting group code for withholding tax. |
   | withholding tax Product Posting Group | Specifies the product posting group code for withholding tax. |
   | withholding tax Calculation Rule | Specifies the calculation rule for withholding tax, which is used with the amount specified in the withholding tax Minimum Invoice Amount field. This helps identify the transactions for which withholding tax isn't deducted.<br><br>For example, if you select the Less than option here and enter 100 in the withholding tax Minimum Invoice Amount field, then withholding tax isn't deducted for those transactions with an amount less than 100. |
   | Withholding tax Minimum Invoice Amount | Specifies the threshold amount that is below which withholding tax isn't deducted. |
   | Withholding tax % | Specifies the withholding tax rate. You must enter the rate without the percent sign. |
   | Realized Withholding Tax Type | Specifies the mode of withholding tax calculation for purchases or sales of items. |
   | Prepaid Withholding Tax Account Code | Specifies the general ledger account number to which sales withholding tax is to be posted. |
   | Payable Withholding Tax Account Code | Specifies the general ledger account number to which purchase withholding tax is to be posted. |
   | Withholding Tax Report | Specifies the withholding tax report type. |
   | Bal. Prepaid Account Type | Specifies the type of balancing account for sales withholding tax transactions. |
   | Bal. Prepaid Account No. | Specifies the account number or bank name for sales withholding tax transactions, based on the type selected in the Bal. Prepaid Account Type field. |
   | Bal. Payable Account Type | Specifies the type of balancing account for purchase withholding tax transactions. |
   | Bal. Payable Account No. | Specifies the account number or bank name for purchase withholding tax transactions. This is based on the type selected in the Bal. Payable Account Type field. |
   | Withholding Tax Report Line No. Series | Specifies the number series for the withholding tax report line. |
   | Revenue Type | Specifies the type of revenue. |
   | Purch. Withholding Tax Adj. Account No. | Specifies the account number on which to post purchase credit memo adjustments. |
   | Sales Withholding Tax Adj. Account No. | Specifies the account number on which to post sales credit memo adjustments. |
   | Sequence | Specifies the sequence in which the withholding tax posting setup information must be displayed in reports. |

1. Choose the OK button.

### Set up revenue types for withholding tax 

Revenue types categorize withholding tax entries and are used for Revenue types are used to categorize withholding tax (WHT) entries and are used for withholding tax certificates.

You can use the **Withholding Tax Revenue Types** page to set up the revenue types for withholding tax.


1. Choose the Tell Me feature icon, enter **Withholding Tax Revenue Types**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specifies the unique code for the revenue type. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specifies the description for the WHT revenue type. |
   | Sequence | Specifies the sequence in which you want to group the revenue types. For example, a revenue type with sequence 0 is displayed before sequence 1. |

### Set up revenue types for withholding tax

1. Choose the Tell Me feature icon, enter **Withholding Tax Revenue Types**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specifies the unique code for the revenue type. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specifies the description for the WHT revenue type. |
   | Sequence | Specifies the sequence in which you want to group the revenue types. For example, a revenue type with sequence 0 is displayed before sequence 1. |

1. Choose the OK button.

## Using withholding tax

Withholding tax applies automatically when you're working with purchase documents. When you post a document that includes withholding tax, [!INCLUDE [prod_short](includes/prod_short.md)] creates a withholding tax entry. You can also use the **Calculate and post withholding tax settlements** action to process withholding tax for a specific period based on the withholding tax entries you already posted.

### Calculate and post withholding tax settlements

You can use the **Calculate and Post Withholding Tax Settlement** page to calculate and post the withholding tax (WHT).

You can close withholding tax entries that are open or not settled and transfer the corresponding amount to the WHT settlement account.

The sum of all withheld amounts is reported as a truncated whole number to the tax authorities.

> [!NOTE]
> The truncated cents are accounted for in a rounding account.

1. Choose the Tell Me feature icon, enter **Calculate and Post Withholding Tax Settlement**, and then choose the related link.
1. Fill in the fields as described in the following table.

| Field | Description |
|-------|-------------|
| Starting Date | The start date of the period for which WHT must be settled. |
| Ending Date | The end date of the period for which WHT must be settled. |
| Posting Date | The posting date of the WHT settlement entries. |
| Document No. | The document number of the WHT settlement entries. |
| Description | The WHT settlement description. |
| Settlement Account Type | The settlement account type. |
| Settlement Account | The account number based on the account type selected in the Settlement Account Type field. |
| Rounding G/L Account | The account to which the truncated amount is to be posted. |
| Show WHT Entries | Select to view the withholding tax entries for the specified period. |
| Post | Select to post the WHT settlement entries. |
| Print | Choose the Print button to print the report, or choose the Preview button to view it on the screen. |

## View withholding tax entries

You can view entries that are posted with withholding tax for a specified general ledger register. On the **Withholding Tax Entry** page, you can explore details about the withholding tax, such as the base amount, the calculated withholding tax amount, the withholding tax calculation method, and the unrealized withholding tax amount.

1. Choose the Tell Me feature icon, enter **G/L Registers**, and then choose the related link.
1. Select the general ledger register for which you want to view withholding tax entries, and then choose the **Withholding Tax Entry** action.
1. Explore the posted withholding tax entries on the Withholding Tax Entry page.

## Related information

[Financial management](finance.md)
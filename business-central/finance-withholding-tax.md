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

To enable withholding tax calculation, open the **General Ledger Setup** page and turn on the **Enable Withholding Tax** toggle. Next, configure following setups:

- [Set up revenue types for withholding tax](#set-up-revenue-types-for-withholding-tax), including their sequences and posting groups.
- [Set up withholding tax posting groups](#set-up-withholding-tax-posting-groups) and apply them to items, general ledger accounts, and vendors that are subject to withholding tax.
- [Create a posting setup for withholding tax](#create-a-posting-setup-for-withholding-tax) using the product and business posting groups.
- [Set up vendors for withholding tax](#set-up-vendors-for-withholding-tax), so that you include the appropriate vendors in tax calculations.
- [Set up general ledger accounts for withholding tax](#set-up-general-ledger-accounts-for-withholding-tax), so that tax amounts go to the correct accounts.

If needed, you can override the product posting group on purchase document lines using the **Withholding Tax Prod. Post. Group** field.

### Set up revenue types for withholding tax 

Revenue types categorize withholding tax entries and are used for Revenue types are used to categorize withholding tax (WHT) entries and are used for withholding tax certificates.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Revenue Types**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specifies the unique code for the revenue type. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specifies the description for the WHT revenue type. |
   | Sequence | Specifies the sequence in which you want to group revenue types. For example, a revenue type with sequence 0 is displayed before sequence 1. |

1. Choose the OK button.

### Set up withholding tax posting groups

To use withholding tax, you must set up the business posting groups and product posting groups for withholding tax so that the correct withholding tax calculations are made for each vendor. To learn more about posting groups, go to [Set up posting groups](finance-posting-groups.md). After you set up your posting groups, then next step is to combine them in a posting setup that helps ensure that the tax amounts go to the correct general ledger accounts.

> [!NOTE]
> As a prerequisite, you must set up source codes for withholding tax settlement on the Source Code Setup page. Learn more in [Setting Up Source Codes and Reason Codes for Audit Trails](finance-setup-trail-codes.md).

The following procedure describes how to set up product posting groups for withholding tax. The steps are the same for business posting groups.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Prod. Post. Group**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Code | Specify the code for the product posting group. You can enter a maximum of 10 alphanumeric characters. |
   | Description | Specify the description for the product posting group. You can enter a maximum of 50 alphanumeric characters. |
   
1. Choose the OK button.

### Create a posting setup for withholding tax

Finally, you must set up how these posting groups must be used when documents are posted.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Withholding Tax Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

   | Field | Description |
   |-------|-------------|
   | Withholding Tax Bus. Post. Group | Specifies the business posting group code for withholding tax. |
   | Withholding Tax Prod. Post. Group | Specifies the product posting group code for withholding tax. |
   | Withholding Tax Calculation Rule | Specifies the calculation rule for withholding tax, which is used with the amount specified in the **Withholding Tax Minimum Invoice Amount** field. This rule helps identify the transactions for which you don't deduct withholding tax.<br><br> For example, if you select the **Less than** option here and enter **100** in the withholding tax **Withholding Tax Minimum Invoice Amount** field, withholding tax isn't deducted for transactions amounts that are less than **100**. |
   | Withholding Tax Minimum Invoice Amount | Specifies the minimum amount that you deduct withholding tax for. Withholding tax isn't deducted for amounts that are less than this value. |
   | Withholding Tax % | Specifies the withholding tax rate. Enter the rate without the percent sign. |
   | Realized Withholding Type | Specifies the mode of withholding tax calculation for purchases or sales of items. |
   | Prepaid Withholding Tax Account Code | Specifies the general ledger account to which you post sales withholding tax. |
   | Payable Withholding Tax Account Code | Specifies the general ledger account number to which you post purchase withholding tax. |
   | Bal. Prepaid Account Type | Specifies the type of balancing account for sales withholding tax transactions. |
   | Bal. Prepaid Account No. | Specifies the account number or bank name for sales withholding tax transactions, based on the type selected in the **Bal. Prepaid Account Type** field. |
   | Bal. Payable Account Type | Specifies the type of balancing account for purchase withholding tax transactions. |
   | Bal. Payable Account No. | Specifies the account number or bank name for purchase withholding tax transactions. This option is based on the type selected in the **Bal. Payable Account Type** field. |
   | Withholding Tax Report Line No. Series | Specifies the number series for the withholding tax report line. |
   | Revenue Type | Specifies the type of revenue. |
   | Purch. Withholding Tax Adj. Account No. | Specifies the account number on which to post purchase credit memo adjustments. |
   | Sales Withholding Tax Adj. Account No. | Specifies the account number on which to post sales credit memo adjustments. |
   | Sequence | Specifies the sequence in which the withholding tax posting setup information displays in reports. |

1. Choose the OK button.

### Set up vendors for withholding tax

To include a vendor in withholding tax calculations, on the **Vendor Card** page, turn on the **Withholding Tax Liable** toggle. Then, in the **Withholding Tax Bus. Post. Group** field, specify the general ledger account to which to post tax amounts.

### Set up general ledger accounts for withholding tax

You must assign the product and business posting groups to the general ledger accounts that you want to use to register withholding tax. On the **G/L Account Card** page, fill in the **Withholding Tax Bus. Post. Group** and **Withholding Tax Prod. Post. Group** fields.

## Using withholding tax

Withholding tax applies automatically when you're working with purchase documents. When you post a document that includes withholding tax, [!INCLUDE [prod_short](includes/prod_short.md)] creates a withholding tax entry. You can also use the **Calculate and post withholding tax settlements** action to process withholding tax for a specific period based on the withholding tax entries you already posted.

### Calculate and post withholding tax settlements

You can use the **Calculate and Post Withholding Tax Settlement** page to calculate and post the withholding tax (WHT).

You can close withholding tax entries that are open or not settled and transfer the corresponding amount to the withholding tax settlement account.

The sum of all withheld amounts is reported as a truncated whole number to the tax authorities.

> [!NOTE]
> The truncated cents are accounted for in a rounding account.

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

## View withholding tax entries

You can view entries that are posted with withholding tax for a specified general ledger register. On the **Withholding Tax Entry** page, you can explore details about the withholding tax, such as the base amount, the calculated withholding tax amount, the withholding tax calculation method, and the unrealized withholding tax amount.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **G/L Registers**, and then choose the related link.
1. Select the general ledger register for which you want to view withholding tax entries, and then choose the **Withholding Tax Entry** action.
1. Explore the posted withholding tax entries on the **Withholding Tax Entry** page.

## Related information

[Financial management](finance.md)
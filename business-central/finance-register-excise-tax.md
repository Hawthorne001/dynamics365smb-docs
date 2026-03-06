---
title: Register excise tax
description: Learn how Business Central helps you capture and report excise tax information.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.search.keywords: tax
ms.search.form: 6287_Primary, 6285, 7414
ms.date: 03/06/2026
ms.custom: bap-template
---

# Register excise tax

Excise taxes are levied on the production or sale of specific goods, such as fuel, alcohol, and tobacco. In [!INCLUDE [prod_short](includes/prod_short.md)], you can register and track excise tax information to ensure accurate tax reporting and compliance with regulatory requirements. By registering excise tax, your company can streamline tax calculations, maintain detailed audit trails, and reduce the risk of non-compliance penalties.

## Get started

Before you can calculate excise taxes, you must configure [excise tax types](#set-up-excise-tax-types). Excise tax types represent the goods or services that you want to register excise tax. For each excise tax type, you can define a tax basis as weight, sugar content, active content,   volume, pure alcohol (ABV), or quantity. Also, set up excise duty rates for each excise tax type to calculate the final tax amount based on the selected basis and the accumulated excise‑liable quantity.

Finally, configure the items and fixed assets you want to include in excise tax calculations.

### Set up excise tax types

Excise tax types represent the goods you want to register excise tax for.

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Excise Tax Types**, and select the related link.
1. Fill in the fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. To make the types available on excise tax journals, turn on the **Enabled** toggle.
1. Choose the **Configure Entry Permissions** action to open the **Excise Tax Entry Permissions** page. 
1. In the **Excise Entry Type** field, specify the type of document to include in excise tax calculations. 
1. 1. On the **Excise Tax Types** page, choose the **Item/FA Rates** action to open the **Excise Tax Item/FA Rates** page.
1. In the **Source Type** field, specify whether the rate applies to items of fixed assets.
1. In the **Source No.** field, choose the item or fixed asset.
1. In the **Excise Duty** field, specify the amount of tax to register for the item or fixed asset.
1. In the **Effective From Date** field, specify the date from which you want to calculate excise tax for the item or fixed asset.
1. Optionally, in the **Report Caption** field, enter text to include in your excise tax report. For example, if you're registering tax for plastics and using weight as the measure, you might enter "Plastic Excise Tax (by Weight)."

### Set up items and fixed assets for excise tax

To prepare items and fixed assets for registering excise tax, on the **Excise Tax** FastTab of the **Item Card** or **Fixed Asset Card** pages, specify the relevant type of excise tax, the unit of measure, and the quantity.

## Register excise tax

1. [!INCLUDE [open-search](includes/open-search.md)], enter **Excise Journal**, and select the related link.
1. Choose the **Generate Excise Tax Entries** action to open the **Generate Excise Tax Journal Entries** page.
1. Fill in the filter fields as necessary. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]
1. Optionally, you can use the **Dimensions** action to add dimensions to the selected line.
1. On the **Excise Journal** page, choose the **Register** action.

## Review your excise tax transactions

After you register your exise taxes for items or fixed assets, you can use the **Excise Taxes Transaction Logs** page to review the data. To drill down deeper into the transactions, use the **Item Ledger Entry** and **FA Ledger Entry** actions to explore the ledger entries for them.

## Related information

[Financial management](finance.md)
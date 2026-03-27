---
title: VAT Return Periods in the Czech version
description: Learn about VAT Return Periods in Czechia, and how it's used in Business Central for VAT reporting.
author: v-jurxova
ms.author: v-jurxova
ms.reviewer: v-soumramani
ms.search.keywords: CZ, Czech, Currency, Finance, Accounting, VAT Return Periods
ms.topic: article
ms.date: 03/17/2026
ms.search.form: 118
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Align VAT periods with Microsoft standard in the Czech version

The feature consolidates the Czech localization functionality VAT Period into the standard VAT Return Period table. All processes previously based on VAT Period—such as period generation, closing, and posting checks—will now operate on VAT Return Period.

Key elements include:

- Data Migration: Existing VAT Period records will be migrated to VAT Return Period during the upgrade.
- Synchronization: Bidirectional synchronization between VAT Period and VAT Return Period ensures data consistency.
- New Report: Create VAT Return Periods report for generating periods with parameters (start date, number of periods, length, due date).
- Report Updates: Reports such as VAT Statement Preparation, Calculate and Post VAT Settlement, and Export VAT Statement will reference VAT Return Period.
- Feature Management: Controlled activation via Feature Management, allowing testing in sandbox environments before enabling in production.

## Related information

- [Core localization pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech local functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

## [!INCLUDE[prod_short](../../includes/free_trial_md.md)]  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

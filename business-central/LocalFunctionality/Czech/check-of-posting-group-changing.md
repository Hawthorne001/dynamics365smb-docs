---
title:  Check posting group change in Customer, Vendor, Item, Bank Account [CZ]
description: Learn how the Czech version of Business Central checks for changes to posting groups on customer, vendor, item, and bank account cards, ensuring compliance with local requirements.
author: v-pejano
ms-service: dynamics-365-business-central
ms.topic: article
ms.search.keywords: Czech, Finance, Localization, CZ
ms.date: 06/02/2025 
ms.reviewer: v-soumramani
ms.author: v-pejano
---

# Check for requests to change posting group in the Czech version

The standard functionality extends with checks if there's a request to change posting groups for customer, vendor, item, and bank account cards.

- On the Customer Card, the customer's posting group can be changed if there are no open customer entries.
- On the Vendor Card, you can change the vendor posting group if there are no open vendor entries.
- On the Item Card, you can change the item posting group if there are no open item entries and at the same time there are no uninvoiced closed item entries.
- On the Bank Account Card, you can change the posting group of the bank account if the Balance or Balance (LCY) isn't zero.

## Related information

- [Core Localization Pack for Czech](ui-extensions-core-localization-pack-cz.md)  
- [Czech Local Functionality](czech-local-functionality.md)  
- [Finance](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

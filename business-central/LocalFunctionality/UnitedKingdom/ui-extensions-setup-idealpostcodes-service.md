---
title: Set up the IdealPostcodes Extension [UK]
description: Learn how to configure the IdealPostcodes extension in the British version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: idealpostcodes, postcodes, extension
ms.search.form: 9142,
ms.date: 02/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set up the IdealPostcodes extension

This extension makes it easy to enter addresses in the United Kingdom (UK) for entities like customers, contacts, employees, vendors, bank accounts, and so on.

The IdealPostcodes extension uses the **IdealPostcodes** API to find addresses in postcodes in the UK. To use the extension, you need to get a plan and an API Key for the IdealPostcodes API. We help you access the latest plans when you set up the IdealPostcodes extension in [!INCLUDE [prod_short](../../includes/prod_short.md)]. 

Plans are based on use, or what are sometimes referred to as "calls." A call, in this case, is when [!INCLUDE [prod_short](../../includes/prod_short.md)] displays a list of addresses in a postcode. Depending on how often you add addresses, choose the plan that's best for you.

## Set up the IdealPostcodes extension

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Connections**, and then choose the related link.
1. On the **Service Connections** page, choose **UK Postcode Service**.
1. On the **Postcode provider configuration** page, choose **Disabled**.
1. On the **Postal code service selection** page, choose **IdealPostcodes**.
1. On the **IdealPostcodes Provider Setup** page, choose **Get API Key** to open the **Plans** page on the website for the **IdealPostcodes** API.

   > [!NOTE]
   > You might need to allow pop-ups in your browser. 

1. Purchase a plan. You might have to provide your email address.
1. Open the email from IdealPostcodes, and copy the API key.
1. On the **IdealPostcodes Provider Setup** page:

   1. In the **API Key** field, enter the API key.
   1. Read the **Terms & Conditions**.
   1. Select the **Enabled** checkbox, and then choose **OK**.

1. On the **Service Connections** page, verify that the **Address Provider** field contains **IdealPostcodes**. If it does, the service is ready to use. 

## Related information

[IdealPostcodes extension in the British version](ui-extensions-idealpostcodes.md)  
[United Kingdom local functionality in the British version](united-kingdom-local-functionality.md)  

[!INCLUDE [footer-banner](../../includes/footer-banner.md)]

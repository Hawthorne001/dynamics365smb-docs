---
title: Use an integration with Field Service
description: This article describes how to benefit from an integration with Microsoft Dynamics 365 Field Service.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: field service, integration, integrating
ms.date: 05/14/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap template
---

# Use an integration with Field Service

This article describes the tasks that integrating [!INCLUDE [prod_short](includes/prod_short.md)] and [!INCLUDE [field-service-short](includes/field-service-short.md)] enables. What you can do depends on whether your integration is the **Project** or **Project and Service** type.

The following sections describe tasks in both applications for both types of integrations.

> [!NOTE]
> The **Project and Service** type of integration includes the same features as the **Project** type. To keep this article short and avoid redundancy, the sections that describe the **Project and Service** type focus on using service features.

## Use a Project type of integration in Field Service

### Synchronize work order products and services with project tasks

You can [create work orders](/dynamics365/field-service/create-work-order) using the **Service Account** and **Billing Account** from [!INCLUDE [prod_short](includes/prod_short.md)]. On work orders, you must select the **Business Central Project Task** in the **External Project** field. Selecting a project lets you synchronize work order products and services to the appropriate project task in [!INCLUDE [prod_short](includes/prod_short.md)].

### Check item availability

You can add inventory and noninventory items as **Work Order Products** on work orders and get the quantity on hand and costs and prices from [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Create a work order from the work order form and record list](/dynamics365/field-service/create-work-order#create-a-work-order-from-the-work-order-form-and-record-list).

You can use the **Open in Business Central** action to open a location that's coupled to a warehouse.

Technicians can verify whether the items they need to complete a work order are available. To check availability, on the **Work Order** or **Product** pages, on the **Related** menu, choose **Items Availability by Location**.

### Book resources

You can book a resource and relate the **Bookings** to work order services using a **Bookable Resource** from [!INCLUDE [prod_short](includes/prod_short.md)].

### Create and post service orders

When you mark a work order product or service as **Used** on a work order with a specific work order type, the lines synchronize to a service order. Consumption is also posted, based on settings on the **Dynamics 365 Field Service Integration Setup** page.

During consumption and invoice posting in [!INCLUDE [prod_short](includes/prod_short.md)], the quantities are updated on the original work order product and work order service lines in [!INCLUDE [field-service-short](includes/field-service-short.md)].

## Use a Project type of integration in Business Central

Depending on your settings on the **Field Service Integration Setup** page, when work orders include products and services, consumption information is transferred and posted using a **Project Journal** in [!INCLUDE [prod_short](includes/prod_short.md)].

### Create and post sales invoices

The **Quantity To Bill** and **Duration To Bill** values are copied to the **Qty- to Transfer to Invoice** field. Based on those values, you can create and post sales invoices in [!INCLUDE [prod_short](includes/prod_short.md)] to invoice the customer. After the invoice is posted and synchronized to the Dynamics 365 Sales environment, or consumption is processed in [!INCLUDE [prod_short](includes/prod_short.md)], the quantity invoiced and quantity consumed display on the [!INCLUDE [prod_short](includes/prod_short.md)] tab on the **Work Order Product** and **Work Order Service** pages.  

### Track consumption on work orders

Use the **Project Planning Lines** page to track posting and invoicing of consumption on work orders. From the **Project Planning Lines** page, you can create and post sales invoices in [!INCLUDE [prod_short](includes/prod_short.md)]. Afterward, you can synchronize them with [!INCLUDE [field-service-short](includes/field-service-short.md)] and keep track of the status of the invoices.

> [!NOTE]
> For work orders services with a booking that uses a bookable resource, and the bookable resource is coupled to a [!INCLUDE [prod_short](includes/prod_short.md)] resource, data synchronizes to two project journal lines:
>
> - One line of the type **Budget** for the coupled resource.
> - One line of the type **Billable** for the item being serviced.
>
> The product that's chosen on the work order service must be coupled to an item of the type **Service** in [!INCLUDE [prod_short](includes/prod_short.md)]. Also, the base unit of measure for the item must be **Hours Unit of Measure** on the **Dynamics 365 Field Service Integration Setup** page.
>
> You can create an invoice for an item of the type **Service** from the billable project planning line, and use the budget project planning line to register cost with the resource.

### Manage locations

Use the **Locations in Field Service** action on the **Locations** and **Location Card** pages to open a coupled location in [!INCLUDE [field-service-short](includes/field-service-short.md)], synchronize it, set up and delete couplings, and view synchronization logs. You can view the product quantity allocated from work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] as part of the gross requirements in Business Central's inventory availability calculation. Demand generated by orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] automatically becomes input for planning.

## Use a Project and Service type of integration in Field Service

### Align work orders with service orders

The integration automatically synchronizes work orders in [!INCLUDE [field-service-short](includes/field-service-short.md)] with service orders in [!INCLUDE [prod_short](includes/prod_short.md)]. For example, when you create a work order, a service order is automatically created in [!INCLUDE [prod_short](includes/prod_short.md)] and coupled with it. Data from work order incidents aligns with service item lines, and work order products and services align with service lines.

On work orders, you can add items of the type **Service** as **Work Order Services** and get costs and prices from [!INCLUDE [prod_short](includes/prod_short.md)]. To learn more, go to [Products and services tab](/dynamics365/field-service/work-order-experience#products-and-services-tab). The items from [!INCLUDE [prod_short](includes/prod_short.md)] show as primary assets under  **Assets** on the work order.

> [!NOTE]
> When a product or service's status on a work order changes from **Estimated** to **Used** in [!INCLUDE [field-service-short](includes/field-service-short.md)], they synchronize to project journal lines in [!INCLUDE [prod_short](includes/prod_short.md)].

### Use a Project and Service type of integration in Business Central



## Related information

[Integrate with Microsoft Dynamics 365 Field Service](admin-integrate-field-service.md)  
[Integrate with Microsoft Dataverse via data sync](admin-common-data-service.md)  

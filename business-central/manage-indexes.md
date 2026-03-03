---
title: Index Management Features in Business Central
description: Learn how Business Central's enhanced index management tools provide developers and admins with detailed insights and control over database indexes.
author: phduck
ms.author: magram
ms.reviewer: jswymer
ms.topic: conceptual
ms.collection: #Required; If this isn't a getting started article, don't remove the attribute, but leave the value blank. The values for this attribute will be updated over time.
ms.date: 02/23/2026
ms.custom: bap-template
---

# Manage indexes in Business Central

[!INCLUDE [applies-to-2026-releasewave1-later](includes/applies-to-2026-releasewave1-later.md)]

As an admin, you can view and manage database indexes per company to optimize performance and reduce costs. Selectively disable non-essential indexes to improve write performance and storage, while protecting unique indexes and SIFT indexes from being disabled.

## About indexes

An *index* is a database structure that makes it faster to find, filter, sort, or aggregate data in a table. An index is a defined ordering of one or more fields in a table that SQL Server (for Business Central on‑premises) or Azure SQL (for online) uses to speed up lookups. Without an index, the database must scan the entire table to find matching records. With a suitable index, it can jump directly to the relevant rows, which is dramatically faster for large tables.

On the other hand, indexes have a maintenance cost: they require additional storage and can slow down create, update, and delete (CRUD) operations because the index must be kept up to date.

In AL code, indexes are defined by secondary keys in both table objects and table extension objects. A single table object and table extension object can have multiple secondary keys. Learn more in [Table keys](/dynamics365/business-central/dev-itpro/developer/devenv-table-keys).

## View index information

You view table indexes from the **Table Information** page:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Table Information**, then choose the related link.
1. On the **Table Information**, locate the table and select its ID in the **Table No.** column.

   The **Table Data Management** card for the table opens showing general information about the table and it's indexes.

   The **Indexes** section displays details of each index on table including index storage size, index usage statistics, and index type (AL-defined or system-generated). Use the values in the columns to identify underused indexes in a specific company or environment.

> [!NOTE]
> The index information is sourced from a virtual table called [Database Index](https://learn.microsoft.com/en-us/dynamics365/business-central/application/system/table/system.diagnostics.database-index). This table exposes data from the corresponding [SQL dynamic management view (DMV)](/sql/relational-databases/system-dynamic-management-views/sys-dm-db-index-usage-stats-transact-sql), providing two sets of usage metrics: user* and last_user*.

## Turn off indexes per company

You can turn off non-unique indexes with low usage to reduce storage costs and improve write performance. In the Indexes section of the Database Index Information page, clear the Enabled in Database check box for the unwanted index.

Unique indexes, primary keys, SIFT, and systemid indexes are protected from disabling. Disabling an index takes effect immediately. Enabling an index is queued for the next scheduled midnight process.
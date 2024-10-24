---
ms.date: 10/24/2024
title: Upload and maintain data through the Microsoft 365 admin center
description: Learn how to upload organizational data using the Microsoft 365 Admin Center instead of Viva Insights.
author: zachminers
ms.author: v-zachminers
ms.topic: article
ms.localizationpriority: medium
ms.collection: viva-insights-advanced
ms.service: viva-insights
manager: anirudhbajaj
audience: Admin
---

# Upload and maintain data through the Microsoft 365 admin center

Organizational data uploads must now be done in the Microsoft 365 admin center, *not* the Viva Insights Advanced Analytics app or Analyst Workbench.  

This new platform centralizes organizational data uploads across all Viva apps, making it easier and faster to re-use your organizational data across multiple Viva apps and Microsoft 365 applications without needing to upload data for each app separately.

>[!Important]
>This change is being made in waves, and all Viva Insights tenants have been put into one of three migration waves. If you're part of wave 1, your Viva Insights admin has been notified, and this change will roll out on November 26, 2024.
>
>Once your tenant(s) migrate, only Global admins can manage data uploads through the Microsoft 365 admin center. Managing data uploads through the Viva Insights Analyst Workbench will no longer be available.
>
>[Learn more about the Microsoft 365 admin center](/microsoft-365/admin/admin-overview/admin-center-overview).

## Upload your data in the Microsoft 365 admin center

Global admins must now work with your organization’s data source admin to prepare organizational data using the .csv template in the Microsoft 365 admin center.

1. First, update the template with your organizational data using the attribute name headers as specified in the template. This means that the attribute names in the data file must be prefixed with Microsoft_*attribute-name*, such as Microsoft_*Organization*. Please take note of the expected attribute names to prevent data upload errors.
2. Follow the Organizational data in Microsoft 365 wizard to complete your data upload. Then you can:
    1. View the data upload progress.
    1. Download data validation error logs to help you correct your data if needed.
    1. Check the organizational data import history.
    1. View the data quality of past uploads.

>[!Note]
>Microsoft Entra data is the default data source until you upload a data file. [Learn more](/viva/organizational-data).

## Other capabilities remaining in the Advanced Analytics app

While organizational data uploads must now be done in the Microsoft 365 admin center, all other tasks must still be done in the Advanced Analytics app such as creating [data partitions](../admin/partitions.md), uploading all other types of data such as [sentiment data](../../org-team-insights/copilot-dashboard.md#upload-group-level-survey-results-with-the-advanced-insights-app), business outcome data, and managing your Viva Insights [admin settings](../admin/admin-center.md).

## FAQ

**Why am I in wave 1?**

Current product usage and geographical location were the main factors to determine which customers to migrate first.

**Will this affect my organization’s existing data?**

There is no impact on your organization’s existing data in Viva Insights.

**Will there be any downtime associated with this move?**

No delays are expected, and you should not experience any break in Viva Insights seeded, Copilot dashboard, or premium Viva Insights capabilities. The usual time to process your data uploads will still apply. While no system downtime is expected, you might need some time to get familiar with the Microsoft 365 admin center platform.

**Will I still be able to use the Viva Insights Advanced Analytics app to upload data?**

No, you won’t have access to the organizational data upload feature in the Viva Insights app. All other features you use in Viva Insights will still be available.

If you have any other questions or would like to be excluded from this migration wave, please reach out to vitomodismigration@microsoft.com by November 15, 2024.
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

Starting December 5, 2024, organizational data uploads must be done in Organizational data in Microsoft 365 through the Microsoft 365 admin center, *not* the Viva Insights Advanced Analytics app.  

Organizational data in Microsoft 365 centralizes organizational data uploads across Viva and Microsoft 365 apps, making it faster to reuse your organizational data across multiple apps without needing to upload data for each app separately.

[Learn more about organizational data in the Microsoft 365 admin center](/viva/organizational-data).

[Learn more about the Microsoft 365 admin center](/microsoft-365/admin/admin-overview/admin-center-overview).

>[!Important]
>There's a six-month transition period for Viva Insights admins to this new platform. This change is being made in three transition waves, and all Viva Insights tenants have been put into one wave.  
>
>If your tenant is part of the first wave, your Viva Insights admin has been notified, and we’ll begin the rollout on December 5 through April 2025.
>
>Once your tenant(s) migrate to Organizational data in Microsoft 365, only Global admins can upload and manage data through the Microsoft 365 admin center, [here](https://go.microsoft.com/fwlink/?linkid=2298902). Managing data uploads through the Viva Insights Analyst Workbench will no longer be available.

## 1. Prepare your organizational data

Work with the person responsible for preparing your data, such as your data source admin, to prepare your organizational data.

To use organizational data in Microsoft 365, you need to use the same column headers provided in the template through the data upload wizard.  

Ensure your file is updated with the correct attribute name headers as specified in the template, which must be prefixed with Microsoft_*attribute-name* such as Microsoft_*Organization*. This is different from how you currently prepare your data file for upload within Viva Insights. The headers should now be prefixed with Microsoft_. Keep this formatting in mind as you prepare your data file to prevent data upload errors.

[Learn more about the public attributes you can upload through Organizational data in the Microsoft 365 admin center](/viva/organizational-data).

[Learn more about how to prepare your data](..//admin/prepare-org-data.md).

>[!Note]
>Microsoft Entra data is the default data source until you upload an organizational data file. [Learn more](/viva/organizational-data).

## 2. Upload and manage your data in the Microsoft 365 admin center

After preparing your data, Global admins must now work with your organization’s data source admin to prepare organizational data using the .csv template in the Microsoft 365 admin center.

To upload data, follow the Organizational data in Microsoft 365 wizard to complete the data upload. After successfully uploading data, Global admins can: 

* View the data upload progress
* Download data validation error logs to help correct the data if needed
* Check organizational data import history
* View the data quality of past uploads

>[!Note]
>Uploading files larger than 25 MB using Organizational data in Microsoft 365 requires the use of SharePoint. [Learn how to upload data through Sharepoint](/viva/import-orgdata#upload-the-file-to-sharepoint).

## Other capabilities remaining in the Advanced Analytics app

While uploading and managing organizational data must now be done in the Microsoft 365 admin center, all other tasks must still be done in the Advanced Analytics app such as creating [data partitions](../admin/partitions.md), uploading all other types of data such as [sentiment data](../../org-team-insights/copilot-dashboard.md#upload-group-level-survey-results-with-the-advanced-insights-app), business outcome data, and managing your Viva Insights [admin settings](../admin/admin-center.md).

## FAQ

**Why am I in wave 1?**

Current product usage and geographical location were the main factors to determine which customers to migrate first. Reach out to us if you have any questions about the wave to which you're assigned.

**Will this affect my organization’s existing data?**

There's no impact on your organization’s existing data in Viva Insights. Every new upload from organizational data in Microsoft 365 is an incremental upload to your existing data.

**Will there be any downtime associated with this move?**

No delays are expected, and you shouldn't experience any break in Viva Insights seeded, Copilot dashboard, or premium Viva Insights capabilities. The usual time to process your data uploads will still apply. While no system downtime is expected, you might need some time to get familiar with the Microsoft 365 admin center platform.

**Will I still be able to use the Viva Insights Advanced Analytics app to upload data?**

No, you won’t have access to the organizational data upload feature in the Viva Insights app. All other features you use in Viva Insights will still be available.

**I have more questions that haven’t been answered, or I need to make a request to the Viva Insights team.**

Please reach out to us through your Viva Insights support team.
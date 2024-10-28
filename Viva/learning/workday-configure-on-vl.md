---
title: Configure Workday on Viva Learning
ms.author: bhaswatic
author: bhaswatic
manager: elizapo
ms.reviewer: chrisarnoldmsft
ms.date: 10/28/2024
audience: admin
ms.topic: article
ms.service: viva-learning
search.appverid: MET150
ms.collection:
  - enabler-strategic
  - m365initiative-viva-learning
  - highpri
  - Tier1
ms.localizationpriority: medium
description: Learn how to configure Workday on Viva Learning, the licensing required for the process, and also how to enable Single Sign On (SSO) 
---
# Configure Workday on Viva Learning Admin tab

You need to have premium Viva Learning license to configure Workday. Global Admin or Knowledge Admin role is required to access Viva Learning Admin tab.

1. Sign in to your Viva Learning app

2. Navigate to Admin tab, then select Manage providers from left navigation menu. 

   :::image type="content" alt-text="Screenshot of the Manage Providers tab in Viva Learning." source="../media/learning/wd-s4-1.png" lightbox="../media/learning/wd-s4-1.png":::

3. Select **Add provider** and select **Workday**. Select **Next**.

4. Fill in the following required configuration details for Workday:

   1. Display name: This information is the name of the carousel under which Workday learning content appears for your organization in Viva Learning. If you don't enter a name, it displays the name "Workday".

   1. Workday catalog RaaS report URL: Enter the report URL, which was generated while creating RaaS for catalog. This URL consists of address for API endpoint and Workday username.  

   1. Client ID, Client Secret, and refresh token: These are the values you created while enabling OAuth.

   1. Org ID (only If you want to enable the LRS). Manual full sync triggering is required for codev post adding/deleting any org ID. Full sync can be triggered from Manage providers.

      :::image type="content" alt-text="Screenshot of the Configure Workday window with the fields for name and client info" source="../media/learning/wd-s4-3.png":::

5. Select **Save** to activate Workday content in Viva Learning. It may take up to 24 hours for the content to display in the Viva Learning app.

6. Once configured, Workday appears in the Configured providers list. You can track the sync status, sync time stamp and can download the sync logs.

   :::image type="content" alt-text="Screenshot of the manage providers list that includes the configured Workday provider" source="../media/learning/wd-s4-4.png" lightbox="../media/learning/wd-s4-4.png":::

7. If you want to enable LRS (Learner record sync) in Assignment and Completion, enable the LRS toggle.
 
8. You can also use **Manage providers** to edit or delete the Workday configuration.
 
9. Admins can also trigger full sync for catalog from "Full Sync" toggle in the catalog row.

## Enable SSO for Workday

Viva Learning and Workday integration allows seamless authentication (SSO). On Teams Desktop and Web, users can directly consume a course on Workday portal without the need to sign in via Workday credentials. On Teams mobile, user need to enter the credentials for first time. 

Refer to the [SSO integration between Workday and Viva Learning](/entra/identity/saas-apps/workday-tutorial).

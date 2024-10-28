---
title: Generate connection parameters in Workday
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
description: Learn how to generate connection parameters on your Workday portal for the Viva Learning integration.
---

# Generate connection parameters in the Workday portal

This article outlines how to generate connection parameters on your Workday portal for integration with Viva Learning.

## Retrieve the Workday Web Service endpoint

You can find the required Workday Web Service endpoint on the Workday Data Centers page on Community.

1. Use the Workday [resource page](https://resourcecenter.workday.com) to identify which Workday Production Data Center your tenant is in.

1. Now that you know your data center, fill in your information inside the {brackets} to get your URL. You need this URL for integration in your Microsoft 365 admin center. `https:// {**Production Data Center URL Prefix**}/ccx/service/{**Tenant name**}/Learning/v39.2`
 
An example of a URL: `https://wd3.myworkday.com/ccx/service/yourorg/Learning/v39.2`

## Enable OAuth for Workday, generate Client ID, client secret and refresh token

To enhance the security and maintain the integration, we enabled OAuth for Workday.

This avoids dependency from ISU’s username and password and handles the scenario if ISU leaves the company. Refer to below steps to generate client ID and Client secret required for configuration on admin portal. 
OAuth access is applied at client level, so it will not impact any other sign in flow of other clients linked to Workday. To know more about OAuth, you can refer to [Workday’s OAuth documentation.](https://resourcecenter.workday.com/en-us/signin.html?fromURI=https://signin.resourcecenter.workday.com/app/workdayciam_aembetadoc2_1/exkd1j067lBdQMGYl4x7/sso/saml)

1. Enable OAuth for the tenant 

   1. Access the **Edit Tenant Setup - Security** task. 
   2. Scroll down, in the **OAuth 2.0 Settings section**, select the **OAuth 2.0 Clients Enabled** check box.
    
   :::image type="content" alt-text="Screenshot of the OAuth 2.0 Clients Enabled checkbox selected." source="../media/learning/wd-s3-1.png" lightbox="../media/learning/wd-s3-1.png":::

1. Create the client for OAuth. 

1. Search for **Register API client for integrations** task. Enter client name as "VivaLearning" and set expiry of refresh token as "Never" and Scope (Functional Areas) the following. To edit any existing OAuth settings, you can use the **view API client for integrations** action.

    - "Organizations and Roles”
    - "Learning core"
    - "Staffing"
    - "System"
    - "Tenant nonconfigurable"  

    :::image type="content" alt-text="Screenshot of the Register API Client for Integrations" source="../media/learning/wd-s3-2.png":::

4. After creation of API client for integration, you'll get the ClientID and client Secret. Copy the client ID and client secret. This information is used on the admin portal.

5. Generate refresh token 

    1. Search for task- "View API client", go to tab "API clients for integration". It shows all clients. Open the "VivaLearning" client created in previous step. 

    1. Select the ellipses (...), then **API client** and **Manage Refresh Token for Integration**. 
    
       :::image type="content" alt-text="Screenshot of the View API Client with the option task to manage refresh tokens for integration" source="../media/learning/wd-s3-3.png" lightbox="../media/learning/wd-s3-3.png":::

    1. Select the ISU created initially during Viva Learning setup.
    
       :::image type="content" alt-text="Screenshot of the Manage Refresh Tokens for Integration" source="../media/learning/wd-s3-4.png" lightbox="../media/learning/wd-s3-4.png":::
    
    1. Enable "Generate new refresh token" checkbox, select **OK**.

    1. Copy the generated refresh token. 

## Get org ID

You need to enter the org IDs for which you want to get assignment and completion records. If you want to pull the data for all employees you can do so by adding all child org IDs for root ID in Workday. Follow below steps for same.

To generate the org IDs for a single department, please follow below steps.

1. Go to your Workday portal. Search for the organization for which you want to sync the assignment and completion records. If you want to select the data for all employees, search for root org.

2. Select the organization under category Organizations.

1. Select the ellipses (...) and select **Integration IDs** and then **View IDs**.

   :::image type="content" alt-text="Screenshot of the View IDs options within the Organizations menu" source="../media/learning/wd-s3-6.png" lightbox="/viva/media/learning/wd-s3-6.png":::

1. Select the Workday ID mentioned above. Save this ID for later as this will be used as a configuration parameter.

   :::image type="content" alt-text="Screenshot of the Integrations ID section with the ID highlighted" source="../media/learning/wd-s3-7.png" lightbox="../media/learning/wd-s3-7.png":::

5. Run following report "Headcount Report" on Workday and select root org. It gives you a list of all departments under root org.

6. Select ellipses (...) and select **Integration IDs** and then View IDs.

7. Select the Workday ID mentioned above. Save this ID for later as this will be used as a configuration parameter.

8. In large tenant, generate org IDs for departments under root ID

9. If your tenant has large employee base, instead of adding the root ID you can add the child of root in configuration form.

10. Run the "Headcount Report" on Workday and select root org. It gives you a list of all departments under the root org.

:::image type="content" alt-text="Screenshot of the Headcount Report" source="../media/learning/wd-s3-8.png":::



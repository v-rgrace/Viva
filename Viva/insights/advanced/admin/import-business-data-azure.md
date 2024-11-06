---
ms.date: 08/6/2024
title: Import business data with Azure blob import
description: Learn how to import business data into Viva Insights through an Azure blob import.
author: zachminers
ms.author: v-zachminers
ms.topic: article
ms.localizationpriority: medium
ms.collection: viva-insights-advanced
ms.service: viva-insights
manager: anirudhbajaj
audience: Admin
---

# Import business data with Azure blob import

Uploading business data into Viva Insights helps you understand how Copilot usage influences the business outcomes that matter most to your organization. Business outcomes might include productivity metrics at both the task and job levels, such as the number of emails sent by your sales team or the number of closed deals. Please refer to our separate documentation on the Copilot Business Outcome report to learn more. 
 
You can upload business data in the Microsoft Viva Insights’ advanced insights app in one of two ways: through individual .csv files that you as an Insights Administrator upload directly to Viva Insights; or through an Azure blob import that you, your source system admin, and your Azure contributor set up. 

This article covers the second option, Azure blob import. 

With an Azure blob import, your Azure subscription’s **Owner** or **Storage Account Contributor (with Role Based Access Control Administrator)** creates a new Storage account with blob container on the Azure portal, and your source system admin configures a periodic export of a .csv file to the blob container’s location. You can then set up Viva Insights to automatically pull business data from the .csv file within this location.

## Workflow

1. Setup:

    1. The Azure subscription Owner creates a secure blob container on the Azure portal. The blob store location should be secure for sensitive business data, and it needs to be set up in the customer’s Azure subscription. 

    2. If the Azure contributor prefers service principal authorization, the Azure contributor authorizes the service principal and provides the blob URL to the Insights admin and source system admin by sharing it in a secure way. If the Azure contributor does not prefer service principal authorization, they generate a SAS URL and provide it to the Insights admin and source system admin. 

    3. The source system admin prepares the data in a .csv file, and configures a periodic export of the file from the HR source system to the blob container. 

    4. The Insights admin enters the URL in the Viva Insights app to turn on the import from the Azure blob store location. The Insights Admin also uploads the mapping file for the business data.

2. Validation: Viva Insights validates the data. (If validation isn’t successful, you can choose from a few options described in Validation fails.) 

3. Processing: Viva Insights processes the data. (If processing isn’t successful, you can choose from a few options described in Processing fails.) 

After the data successfully validates and processes, the overall data-import task is complete.

## Setup

### 1. Create a secure blob container

*Applies to: Azure Subscription Owner or Storage Account Contributor*

1. Open a browser and sign in to your organization’s Azure portal.  

2. Under **Azure services**, select **Storage accounts**. 

3. Under **Storage accounts** at the top left, select **Create** to create a new storage account. 

4. Under **Project details**, use the default settings. 

5. Under **Instance details**, enter a storage account name and select your region. For Primary service, Use Gen 2 Storage account that supports hierarchical namespace. [Learn more about how to create an Azure storage account](/azure/storage/common/storage-account-create).

6. For Performance and Redundancy, you can use the default settings unless you need to make changes. 

7. At the bottom, select **Next** to go to Advanced section. 

8. On the Advanced page, make sure that "Require secure transfer for REST API operations" and "Enable storage account key access" are both selected. For "Minimum TLS version," select at least **Version 1.2**. 

9. For all other Advanced settings, you can use the default settings unless you need to make changes.

10. At the bottom, select **Next: Networking**.

11. Under **Network connectivity**, select **Enable public access from all networks**. 

12. Under **Network routing**, select your routing preference. 

13. At the bottom, select **Next: Data protection**. 

14. On the Data protection page, you can use the default settings unless you need to make changes. 

15. At the bottom, select **Next: Encryption**. 

16. On the Encryption page, you can use the default settings unless you need to make changes. 

17. At the bottom, select **Next: Tags**. 

18. Optional: Add tags to the account. 

19. At the bottom, select **Next: Review**. 

20. Review your selections. Then, at the bottom left, select **Create**. 

21. On the next page, a message will appear that says, "Deployment is in progress." Once deployment is complete, your storage account and its settings will appear. 

22. On the left, under **Data storage**, select **Containers**. 

23. To create a new container, at the top, select **Container**. Then, on the right, enter a name for the container, like "myCustomData." At the bottom, select **Create**.

### 2. Authorize the blob container

*Applies to: Azure Subscription Owner or Role Based Access Control Administrator*

Next, you’ll need to create a blob SAS URL or authorize **Workplace Analytics** service principal. Service principal authorization is the recommended and more secure approach. The blob SAS token does not have any built-in auditing capabilities. Follow the appropriate steps below for the method you choose.

#### For service principal authorization

1. On the left panel, select **Access Control**. 

2. At the top, select **Role assignments**. Select **Add**, then select **Add role assignment**. 

3. In the list of roles, find and select **Storage Blob Data Contributor**. 

4. Next to **Members**, select **Select members**. In the search field on the right, enter **Workplace Analytics**, and select it. 

5. At the bottom left, select **Review + assign**. 

6. On the left panel, under **Data storage**, select **Containers**. 

7. Select the storage container you created in the above steps. 

8. On the left panel, under **Settings**, select **Properties**. 

9. Copy and securely share the URL with the Insights admin. 

10. Let the source system admin know, who will populate the data in this container. They will need Storage Blob Data Contributor access.

#### For SAS URL authorization

1. When the new storage container you created appears, select it. Then, on the left under **Settings**, select **Access policy**. 

2. Under **Stored access policies**, select **Add policy**. Provide a unique identifier, such as "BlobStoreVivaInsights." Select **Read** and **List** permissions. Select a start time a few minutes in the past and an end time one year from now. Select **OK**. 

3. On the left under **Settings**, select **Shared access tokens**. 

4. You can use the default option under **Signing key**. Under **Stored access policy**, select the policy created above. This will auto-populate the expiry window and permissions list. 

5. For **Allowed IP addresses** and **Allowed protocols**, you can use the default settings. 

6. Select **Generate SAS token and URL**. 

7. Copy and securely share the blob SAS URL with the Insights admin. 

8. Let the source system admin know, who will populate the data in this container. They will need Storage Blob Data Contributor access.

### 3. Set up Viva Insights to import data from the blob location

*Applies to: Insights admin* 

Business data likely has different data sources, and might update on different schedules. Customer satisfaction and sales activity metrics, for example, might have different source systems and source admins. You should set up a separate blob connection for each of these, which Viva Insights refers to as "datasets."

1. Start the import from one of two places in the advanced insights app: the **Data hub** page; or **Business data** page under **Platform Setup**. 

    * From **Data hub**: 
        1. In the right panel, under **Business data sources**, select **Azure Blob import**.  
        2. Select **Start**. 

    * From **Business data** page: 
        1. Select **Manage data sources**, then select **Azure Blob import**. 
        2. Select **Start**. 
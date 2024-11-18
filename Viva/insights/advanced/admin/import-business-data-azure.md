---
ms.date: 11/18/2024
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

# Import business data with Azure blob import (preview)

>[!IMPORTANT]
> This feature is for public preview customers only. Features in preview might not be complete and could undergo changes before becoming available in the broader release.

Uploading business data into Viva Insights helps you understand how Copilot usage influences the business outcomes that matter most to your organization. Business outcomes might include productivity metrics at both the task and job levels, such as the number of emails sent by your sales team or the number of closed deals. Please refer to our separate documentation on the [Copilot Business Outcome (Copilot Business Impact) report](..//analyst/templates/copilot-business-impact.md) to learn more. 
 
You can upload business data in the Microsoft Viva Insights’ advanced insights app in one of two ways: through individual .csv files that you as an Insights Administrator upload directly to Viva Insights; or through an Azure blob import that you, your source system admin, and your Azure contributor setup. 

This article covers the second option, Azure blob import. 

With an Azure blob import, your Azure subscription’s **Owner** or **Storage Account Contributor (with Role Based Access Control Administrator)** creates a new Storage account with blob container on the Azure portal, and your source system admin configures a periodic export of a .csv file to the blob container’s location. You can then setup Viva Insights to automatically pull business data from the .csv file within this location.

## Workflow

1. Setup:

    1. The Azure subscription Owner creates a secure blob container on the Azure portal. The blob store location should be secure for sensitive business data, and it needs to be setup in the customer’s Azure subscription. 

    2. If the Azure contributor prefers service principal authorization, the Azure contributor authorizes the service principal and provides the blob URL to the Insights admin and source system admin by sharing it in a secure way. If the Azure contributor does not prefer service principal authorization, they generate a SAS URL and provide it to the Insights admin and source system admin. 

    3. The source system admin prepares the data in a .csv file, and configures a periodic export of the file from the HR source system to the blob container. 

    4. The Insights admin enters the URL in the Viva Insights app to turn on the import from the Azure blob store location. The Insights Admin also uploads the mapping file for the business data.

2. Validation: Viva Insights validates the data. (If validation isn’t successful, you can choose from a few options described in [Validation fails](#validation-fails).) 

3. Processing: Viva Insights processes the data. (If processing isn’t successful, you can choose from a few options described in [Processing fails](#processing-fails).) 

After the data successfully validates and processes, the overall data-import task is complete.

## Setup

### 1. Create a secure blob container

*Applies to: Azure Subscription Owner or Storage Account Contributor*

1. Open a browser and sign in to your organization’s Azure portal.  

2. Under **Azure services**, select **Storage accounts**. 

3. Under **Storage accounts** at the top left, select **Create** to setup a new storage account. 

4. Under **Project details**, use the default settings. 

5. Under **Instance details**, enter a storage account name and select your region. For Primary service, Use Gen 2 Storage account that supports hierarchical namespace. [Learn more about how to create an Azure storage account](/azure/storage/common/storage-account-create).

6. For Performance and Redundancy, you can use the default settings unless you need to make changes. 

7. At the bottom, select **Next** to go to Advanced section. 

8. On the Advanced page, make sure that "Require secure transfer for REST API operations" and "Enable storage account key access" are both selected. For "Minimum TLS version," select at least **Version 1.2**. 

9. For all other Advanced settings, you can use the default settings unless you need to make changes.

10. At the bottom, select **Next: Networking**.

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

### 3. Setup Viva Insights to import data from the blob location

*Applies to: Insights admin* 

Business data likely has different data sources, and might update on different schedules. Customer satisfaction and sales activity metrics, for example, might have different source systems and source admins. You should setup a separate blob connection for each of these, which Viva Insights refers to as "datasets."

1. Start the import from one of two places in the advanced insights app: the **Data hub** page; or **Business data** page under **Platform Setup**. 

    * From **Data hub**: 
        1. In the right panel, under **Business data sources**, select **Azure Blob import**.  
        2. Select **Start**. 

    * From **Business data** page: 
        1. Select **Manage data sources**, then select **Azure Blob import**. 
        2. Select **Start**. 

2. In the Azure Blob Connection page, under **Connection name**, enter a unique name for the import.  

3. Under **Authorization type**, select **Service Principal Authorization**, or **SAS URL Authorization**. Your selection here depends on the authorization method used by your Azure contributor in Step 2 above. 

4. Enter the **Blob SAS URL** or the **Blob URL** for the import provided to you by the Azure contributor in Step 2. 

5. Upload a metadata.json file, with the inputs described below:

    * `"Dataset type"`: The name of the data category, such as "Sales data." You can assign any unique type except these system reserved types: "Survey," "CRM," "Person," "Signal," "AnalystUploadedData," "UserSkills," "HeirarchicalSkills," "RelatedSkills," "SkillsLibrary," "ManagerHierarchy," "Learning," "None," "InteractiveExplorationPersonOutput," "None" 

    * `"Dataset name"`: Unique name representing a specific table in the data category. In case your dataset type is named "SalesData," an example dataset could be "Deals," "Inventory" or "Orders."  

    * `"IsBootstrap"`: This is set to **False** by default. Set to **True** only if you want to overwrite a previously uploaded table (see Dataset name). 

    * `"ColumnMap"`: In addition to the required fields of PersonId and StartDate, include the custom fields from your .csv file. For custom fields, you must include a name and data type.
        * The labels used for the source column(s) named "BusinessMetric1," "BusinessMetric2" and "BusinessMetric3" should match the names of the columns in your .csv file.  

        * The "name" property should represent the names you would like to see reflected in your report output. Make sure that labels you pick follow [these rules](..//admin/rules-validation-errors.md). 

        * You have two options for specifying the "type":  
            * Enter "int32" if your data values consist of whole numbers 
            * Enter "double" if your data values include decimal points

    >[!Note]
    >You'll need to upload numeric business outcome data to be used in any of the reports in advanced insights.

    Here's a sample metadata file: 

    ```
    { 
      "DatasetType": "SalesData", 
      "IsBootstrap": "false", 
      "properties": { 
        "DatasetName":  "Deals" 
      }, 
      "ColumnMap": { 
        "StartDate": { 
          "name": "StartDate", 
          "type": "DateTime_MMDDYYYY" 
        }, 
        "PersonId": { 
          "name": "PersonId", 
          "type": "EmailType" 
        }, 
        "BusinessMetric1": { 
          "name": " Metric1", 
          "type": "int32" 
        }, 
        "BusinessMetric2": { 
          "name": " Metric2", 
          "type": "int32" 
        }, 
        "BusinessMetric3": { 
          "name": " Metric3", 
          "type": "double" 
        } 
      } 
    }
    ```
    For example, let’s say your source system admin uses "PipelineGenerated" to capture the number of deals created. The code would be:  

    ```
    "PipelineGenerated": { 

    "name": "DealsCreated", 

    "type": "int32" 

    } 
    ```

    When you upload your data, data is recorded as "PipelineGenerated" of integer type. Ensure you upload a numeric outcome. [Learn more about how to setup your business data file](#4-prepare-business-data-file-and-send-to-blob-store).

6. Select **Submit**. 

7. If you see an error message, check to make sure you followed all the steps outlined above, and check to ensure the blob SAS URL or blob URL you entered is accurate. Select **Retry**. 

### 4. Prepare business data file and send to blob store

*Applies to: Source system admin*

#### Task 1 - Prepare your data 

First, create a separate .csv file for each dataset. Refer to the [sample .csv template](https://go.microsoft.com/fwlink/?linkid=2286402) for data structure and guidelines to avoid common issues like too many or too few unique values, redundant fields, invalid data formats, and more. [Learn more about file rules and validation errors](..//admin/rules-validation-errors.md). 

Structure the data in this way:

* Add all fields you want to import to the file 

* Required fields are "PersonId" and "StartDate" 

* All business data should be tallied at a monthly and per-person level 

* "StartDate" should represent a month’s data and the date should represent the first of the month. For example, January 2024 should be represented as 1/1/2024. At least three months of business data is recommended.  

* Add a column for each business outcome metric you would like to analyze.  

* You'll need to upload numeric business outcome data to be used in any of the reports in advanced insights.

>[!Note]
>Any files that are dropped prior to the connection creation and mapping upload will not be picked up by Viva Insights. Therefore, make sure you establish the connection first before you drop the file.

#### Task 2 - Export data from your source system to the Blob store 

*Required resource: the .csv file created in previous task*

At the frequency you decide, programmatically export the business data from your source system as a .csv file to your blob store. Alternatively, you could upload the .csv file to Blob store manually in the Azure portal.

### 5. Validation

*Applies to: Insights admin*

After the source system admin exports the data and you setup the import, the app starts validating. In most cases, file validation should complete quickly. 

After this phase completes, validation has either succeeded or failed. Depending on the outcome, you’ll either receive a success status or a failure status in the Import history table in **Business data**.  

For information about what happens next, go to the appropriate section:

* [Validation succeeds](#validation-fails) 

* [Validation fails](#validation-fails)

#### Validation succeeds 

After successful validation, Viva Insights starts processing your new data. Processing can take between a few hours and a day or so. During processing, you’ll see a "Processing" status on the **Import history** table. 

After processing completes, it's either succeeded or failed. Depending on the outcome, you’ll either find a "Success" or "Failed" status in the **Import history** table.

#### Processing succeeds 

When you find the "Success" status in the **Import history** table, the upload process is complete. After you receive the "Success" status, you can: 

* Select the view (eye) icon to see a summary of the validation results. 

* Select the mapping icon to see the mapping settings for the workflow.

#### Processing fails 

If processing fails, you’ll find a "Processing failed" status in the **Import history** table. For processing to succeed, the source system admin needs to correct errors and push the data to Viva Insights again.

>[!Note]
>Processing failures are generally due to backend errors. If you’re seeing persistent processing failures and you’ve corrected the data in your imported file, [log a support ticket with us](/microsoft-365/admin/get-help-support). 

#### Validation fails 

If data validation fails, you'll see a "Validation failed" status in the **Import history** table. For validation to succeed, the source system admin needs to correct errors and resend the data to the blob store. Under **Actions**, select the download icon to download an error log. Send this log to the source system admin so they know what to correct before sending the data again.

The source system admin might find the following section helpful to fix data errors in their export file.

#### About errors in data

*Applies to: Source system admin*

When any data row or column has an invalid value for any attribute, the entire import will fail until the data source admin fixes the source data. 

Here are a few import-specific errors you might encounter if your files aren't formatted correctly: 

* The .csv file is empty. Add a non-empty .csv file and upload again. 

* If a zip file is uploaded to the blob location, upload a .csv instead. 

* If mandatory fields are missing in the .json file, please check and upload mapping file again. 

* The source column isn't mapped to a supported data type. Map to a supported data type and upload the file again. 

* The header names in the .csv file don’t match the fields you mapped in the .json file. Make sure the .json file contains the same fields as the .csv file, and upload the .zip file again. 

* The number of headers in the .csv file doesn't match the fields you mapped in the .json file. Make sure the .json file contains the same fields as the .csv file, and upload the .zip file again. 

* Your .csv file is mapped to a null or empty field in your .json file. Map it to a non-empty field and upload the .zip file again. 

* [Learn about other file rules and validation errors](..//admin/rules-validation-errors.md).

#### Suspended state 

If you see a “Suspended” status in the **Import history** table or when you select **Manage data sources**, this means your authorization credentials have expired, or access has been revoked. You’ll need to update your credentials and reconnect the data source.

## Add new data and manage datasets

*Applies to: Insights admin*

After you've setup your data import, use the steps below to add new data to an existing dataset, create a new dataset, turn off automated imports, and more.

1. On the **Business data** page, select **Manage data sources**. 

2. Under **Azure blob**, select **Manage**. 

    * To add a new dataset, select **Add a dataset**, and follow the process outlined in [Step 3 above](#3-setup-viva-insights-to-import-data-from-the-blob-location). 

    * To delete a dataset, next to the dataset you’d like to delete, select the trash can icon. 

    * To make changes to an existing dataset, select the settings icon.

    * To add new data to an existing dataset, select the plus icon next to the dataset.

On the next page, you can edit the connection name, the blob SAS URL, or the blob URL. If you update the SAS URL or URI, the new location will be used for future data refreshes. 

You can also turn automated imports on or off. When you’re done, select **Save**. 

To replace or edit the business data using the existing blob SAS URL or blob URL, contact your source system admin. When you import data to Viva Insights, you’ll either perform a full or an incremental refresh. If you want to delete fields, you can use a full refresh to do so.

### Refresh types

#### Full

When you perform a full refresh, you’re replacing all your business data in Viva Insights—that is, you overwrite what you’ve already imported. The required fields are PersonId and StartDate. 

You can use a full refresh to delete fields, because fields you leave out won’t show up in your data. We cover deleting data in the next section.

##### Deleting fields with full refreshes

To delete fields with a full refresh, export your data as a .csv that contains all fields except the fields you want to delete. Because a full refresh replaces existing data, you’ll end up with every field except the ones you left out during the import.

#### Incremental

Perform an incremental refresh when you only want to add new information to business data you’ve already uploaded to Viva Insights. With an incremental refresh, you can add new business data for existing employees, or edit existing business data.

##### How to indicate a full or incremental refresh

1. In metadata.json, go to line 3. 

2. Update the `"IsBootstrap"`: property to one of the following: 

    * For a full refresh, use `"IsBootstrap" : "true"`. 

    * For an incremental refresh, use `"IsBootstrap" : "false"`. 

When your import option runs, Viva Insights will start to process your data either as a full or incremental refresh, depending on what you specified here in metadata.json. 

>[!Important]
>Make sure you delete any fields from metadata.json that you're not including in your data.csv file. If you have more fields in your metadata.json file than in your data.csv file—or vice versa—processing for your import will fail.

##### Fields to include in data.csv for full and incremental refreshes

Both full and incremental refreshes should include the same set of required fields: PersonId and StartDate. The StartDate value should be aligned with monthly boundaries. Remove any fields you don’t have in your .csv from your metadata .json file.

### Related topics

* [Copilot business outcome (Copilot business impact) report](..//analyst/templates/copilot-business-impact.md)

* [File rules and validation errors](..//admin/rules-validation-errors.md)

---
ms.date: 08/6/2024
title: Import business data via .csv upload
description: Learn how to import business data into Viva Insights through a .csv file upload.
author: zachminers
ms.author: v-zachminers
ms.topic: article
ms.localizationpriority: medium
ms.collection: viva-insights-advanced
ms.service: viva-insights
manager: anirudhbajaj
audience: Admin
---

# Import business data via .csv upload (preview)

>[!IMPORTANT]
> This feature is for public preview customers only. Features in preview might not be complete and could undergo changes before becoming available in the broader release.

Uploading business data into Viva Insights helps you understand how Copilot usage influences the business outcomes that matter most to your organization. Business outcomes might include productivity metrics at both the task and job levels, such as the number of emails sent by your sales team or the number of closed deals.  

Your business data can appear in the Microsoft Viva Insights advanced insights app in one of two ways: through individual .csv files that you as an Insights Administrator upload directly to Viva Insights; or through an Azure blob import that you, your source system admin, and your Azure contributor set up. 

This article covers the first option, uploading .csv file.

## Workflow

1. Prepare your business data for upload.  

2. Upload the .csv file. 

3. Map fields. 

4. The app validates your data. (If validation isn’t successful, you can choose from a few options described in [Validation fails](#validation-fails).) 

5. The app processes your data. (If processing isn’t successful, you can choose from a few options described in [Processing fails](#processing-fails).) 

After the data successfully validates and processes, you're done with the overall data-upload task.

## Prepare your business data  

Business data can originate from different data sources and might refresh at different cadences. For example, customer satisfaction and sales activity metrics might have different source systems and source admins.  Viva Insights refers to these as "datasets." You should set up a separate .csv upload for each dataset. Refer to the [sample .csv template](https://go.microsoft.com/fwlink/?linkid=2286402) for data structure and guidelines to avoid common issues like too many or too few unique values, redundant fields, invalid data formats, and more. [Learn more about file rules and validation errors](..//admin/rules-validation-errors.md).

To create a separate .csv file for each dataset, structure the data in this way:  

* Add all fields you want to import to the file 

* Required fields are "PersonId" and "StartDate" 

* All business data should be tallied at a monthly and per-person level 

* "StartDate" should represent a month’s data and the date should represent the first of the month. For example, January 2024 should be represented as 1/1/2024. At least three months of business data is recommended.  

* Add a column for each business outcome metric you would like to analyze 

>[!Note]
> You'll need to upload numeric business outcome data to be used in any of the reports in advanced insights.

## Setup

### 1. Specify the dataset

To upload your business dataset in a .csv file, follow these steps:

1. Open the [advanced insights app's](https://analysis.insights.viva.office.com) admin experience. 

2. Under **Platform Setup**, select **Business data**. 

3. Select **Manage data sources**. Next to **.CSV upload**, select **Manage**. If this is your first upload, you'll see **Start**.

4. Select **Add Dataset**. If this is your first upload, you'll be taken directly to step 5.

5. For easy access to this data, enter a "name" and "type" for this dataset. For example, you could be upload two different datasets from your sales team on customer satisfaction and account retention. You can assign the type "Sales" to these datasets and name them "CSAT" and "Account." Analysts can discover this data by searching for their name and type. The dataset name should not contain spaces. 

6. Select **Next**.

>[!Note]
> You can’t subsequently change the Dataset name and type.

### 2. Upload file and define fields

1. Upload your .csv file and specify the "Upload name." Select **Next**. 

2. You’ll see the **Required attributes** page. To view insights from your data, you need to map fields (columns) from your .csv file to field names that the app recognizes.

#### Required fields

Required fields are PersonId and StartDate. Select columns from your .csv file that map to these required fields.

>[!IMPORTANT]
> Every required field must have a valid, non-null value in every row. You need to map all required Viva Insights values, even if the column headers in your .csv files don’t exactly match the Viva Insights value name.

#### Custom

All business data fields in your .csv files are custom attributes. The app will automatically assign it a name. You can change this name and select a data type from the dropdown menu. Once you select a name and datatype, they can’t be changed. After you’ve completed mapping your attributes, select **Next** at the bottom left. After you map fields, the app validates and processes your data as described below. If validation and processing succeed, you're done with the upload process.

### 3. Validation

After you’ve mapped attributes, the app starts validating your data. In most cases, file validation should complete quickly. If your business data file is large, validation could take up to one or two minutes. 

After this phase is completed, validation has either succeeded or failed. Depending on the outcome, you’ll either receive a success status or a failure status in the Import history table in **Business data**.  

For information about what happens next, go to the appropriate section:

* [Validation succeeds](#validation-succeeds)

* [Validation fails](#validation-fails)

#### Validation succeeds

After successful validation, Viva Insights starts processing your new data. Processing can take between a few hours and a day or so. During processing, you’ll see a “Processing” status on the **Import history** table.

After processing completes, it's either succeeded or failed. Depending on the outcome, you’ll either find a “Success” or “Failed” status in the **Import history** table.

##### Processing succeeds

When you find the “Success” status in the **Import history** table, the upload process is complete.

After you receive the “Success” status, you can:

* Select the view (eye) icon to see a summary of the validation results.
* Select the mapping icon to see the mapping settings for the workflow.

>[!Note]
> Each tenant can have only one import in progress at a time. You need to complete the workflow of one data file, which means you either guide it to a successful validation and processing or abandon it, before you begin the workflow of the next data file.

##### Processing fails

If processing fails, you’ll find a “Processing failed” status in the **Import history** table. For processing to succeed, the source system admin needs to correct errors and push the data to Viva Insights again.

>[!Note]
> Processing failures are generally due to backend errors. If you’re seeing persistent processing failures and you’ve corrected the data in your imported file, [log a support ticket with us](/microsoft-365/admin/get-help-support).

#### Validation fails

If data validation fails, you'll see a "Validation failed" status in the **Import history** table. For validation to succeed, the admin needs to correct errors and push the data to Viva Insights again. Under **Actions**, select the download icon to download an error log. This log file describes the problems in your data that might have caused the validation errors. Use this information to decide what to do next: fix the source data or change your required and custom field definitions.

#### About errors in data

When any data row or column has an invalid value for any attribute, the entire import will fail until the data source admin fixes the source data. 

Learn more about how to [prepare your business data](..//admin/import-business-data-azure.md#4-prepare-business-data-file-and-send-to-blob-store) for specific formatting rules that might help resolve errors you encounter. [Learn about other file rules and validation errors](./rules-validation-errors.md).

## Manage data source and make changes

After you've set up your data import, use the steps below to delete a dataset, add a dataset, or add new data to an existing dataset. 

1. On the **Business data** page, select **Manage data sources**. 

2. Under **.CSV Upload**, select **Manage**. 

    * To add a new dataset, select **Add a dataset**, and follow the process outlined in [Step 1](#1-specify-the-dataset) above. 

    * To delete a dataset, next to the dataset you’d like to delete, select the trash can icon. 

    * To make changes to an existing dataset, select the plus icon and upload according to process outlined in [Step 2](#2-upload-file-and-define-fields) above.

3. For incremental uploads into the same dataset, follow the process outlined above. Required fields are needed for every upload.

### Related topics

* [Copilot business outcome report](..//analyst/templates/copilot-business-outcome.md)

* [File rules and validation errors](..//admin/rules-validation-errors.md)
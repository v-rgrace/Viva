---
title: "Prepare and import your organizational data"
ms.reviewer: elizapo
ms.author: elizapo
author: lizap
manager: elizapo
ms.date: 11/05/2024
audience: Admin
f1.keywords:
- NOCSH
ms.topic: solution-overview
ms.service: viva-suite
ms.localizationpriority: medium
ms.custom:
ms.collection:  
- M365initiative-viva
- m365solution-overview
- highpri
search.appverid:
- MET150
description: "Prepare and import your organizational data"
---
# Prepare and import your organizational data 

Before you upload organizational data, you need to do the following:

1. [Download a .csv template](#step-1---download-a-csv-template)
1. [Structure the organizational data](#step-2---structure-the-organizational-data)
1. [Import your organizational data for the first time](#step-3---import-your-organizational-data-for-the-first-time)
1. [Update or make other changes to your data](#step-4---update-or-make-other-changes-to-your-data)

## Step 1 - Download a .csv template

1. Sign into to the Microsoft 365 admin center as a user with Global Admin permissions.
1. On the **Organizational Data in Microsoft 365** page (under **Setup > Migration and imports**), select **Get started** (if this is the first time you're importing data) or **New import**.
2. Select **Download CSV template**.

> [!NOTE]
> You can also use organizational data exported from another system, such as your HR software, as your starting point, as described in [Get an export of organizational data](/viva/insights/advanced/admin/prepare-org-data#step-3---get-an-export-of-organizational-data).

## Step 2 - Structure the organizational data
Now that you have your .csv file starting point, add the organizational data that you want to use in Microsoft 365, and then save the file.

There are two types of attributes you can add in your organizational data file: required and reserved optional. Attributes can be in any order in the file. 

- **Required** - The only attribute required by default is email address.
- **Reserved** - Attributes are reserved column headers for attributes that are currently used to calculate, filter, and group data.


### Sample data file
Here's an example snippet of a valid .csv file:

```CSV
Microsoft_PersonEmail,Microsoft_ManagerEmail,Microsoft_LevelDesignation,Microsoft_Organization,Microsoft_Layer,Microsoft_CompanyOfficeCity
Emp1@contoso.com,Mgr1@contoso.com,Junior IC,Sales,8,Seattle
Emp2@contoso.com,Mgr1@contoso.com,Junior IC,Sales,8,Seattle
Emp3@contoso.com,Mgr2@contoso.com,Manager,Sales,7,Seattle
Emp4@contoso.com,Mgr3@contoso.com,Support,Sales,9,New York
Emp5@contoso.com,Mgr3@contoso.com,Support,Sales,9,New York
Emp6@contoso.com,Mgr3@contoso.com,Support,Sales,9,New York

```

For more information about attributes, see the [Attribute reference](#attribute-reference).

## Step 3 - Import your organizational data for the first time 
After you create a .csv file with your data, the next step is to import the data, either from your local computer (for Viva Insights-licensed customers) or from a SharePoint site.

### Upload the .csv file from your computer (for Viva Insights-licensed customers)
After you create the .csv file with your data, you can upload it directly from your local files. 

>[!NOTE]
> - Local upload is only available for Viva Insights-licensed customers.
> - There's a 25 MB limit on files uploaded directly from your local files. If your .csv file is larger, [upload it first to SharePoint](#upload-the-file-to-sharepoint) and then import it from there.

:::image type="content" source="media/orgdata-import-local.png" alt-text="A screenshot shows local import option. ":::

### Upload the .csv file from SharePoint
First you need to upload the file from your local computer to a secure SharePoint location; then you import the data.

#### Upload the file to SharePoint
Use the following steps to upload your data to SharePoint. Make sure that your SharePoint site has the right permissions and that only those that should be able to access the data can access the site. You can upload a file up to 5 Gb in size. 

1. Open the SharePoint site library.
2. Select **Upload**, and then select **Files**.

   :::image type="content" source="media/sharepoint-library.png" alt-text="A screenshot shows the Upload menu in SharePoint.":::

3. Navigate to the location where you saved the .csv file, and then select **Open**.

   You can also use drag and drop to upload the file.
    
   Before you import the data into Viva, you need the path to the file on SharePoint, in this format: https://*domain*.sharepoint.com/sites/*sitename*/Documents/*foldername*/*filename*.csv. Use the following steps to get the path to your file - the path isn't the same as the URL that you see in your browser when you view the file.

1. Select the ellipses (...) next to the file and then select **Details**.

   :::image type="content" source="media/sharepoint-path-ellipses.png" alt-text="A screenshot shows the ellipses option next to a file in a SharePoint library. "::: 

1. Find the **Path** value, and then select the copy icon. 

   :::image type="content" source="media/sharepoint-path-icon.svg" alt-text="A screenshot shows the Path information for a file in SharePoint.":::
   
   
> [!NOTE]
> Be sure to follow these steps to get the path to the file. This is a different path than what's visible in the URL field of a browser when you view the .csv file in SharePoint.

#### Import the data into Microsoft 365
Now you're ready to import the data. 

1. On the **Organizational Data in Microsoft 365** page (under **Setup > Migration and imports**), select **Get started** (if this is the first time you're importing data) or **New import**.
3. On the **Import data from SharePoint** page, enter the SharePoint location where you saved your .csv file. (If you copied the location at the end of the upload step, paste it here.) 
1. Confirm that you understand that the data you upload here may be processed by Viva and Microsoft 365, as well as non-Microsoft services that you've granted access to the data through Microsoft Graph. Select **Next**.
1. Review the details for your upload, and then select **Begin validation**.

Your organizational data is validated against the requirements for use with Viva and Microsoft 365 services. Validation takes a few hours; however it can take up to three days for your complete data upload to be available in the profile store. You can check the validation status on the **Organizational data** page in the admin center. When the validation is complete, you see a message that your data is in use and managed by Viva and Microsoft 365. 

Each end user's organizational data is stored in that end user's mailbox and respects the data residency rules for Exchange Online (as described in [Data Residency for Exchange Online](/microsoft-365/enterprise/m365-dr-workload-exo?view=o365-worldwide&preserve-view=true)).

## Step 4 - Update or make other changes to your data

Only the global admin can update or delete organizational data stored in the Microsoft 365 User Profile.

To update or delete an end user's organizational data, create and upload a new .csv file containing only the users whose data you want to update or delete. 

- To update a value, include all of the attributes that you want to update. Provide a different value for any attribute that you want to change. If you include an attribute but don't provide a value (but do **not** set it to an empty string), the current value in the Microsoft 365 User Profile is used (it isn't updated).
- To delete a value, set the value for the attribute to an empty string by using two single quotes (''). (Set the **Microsoft_Layer** attribute "-1".) To delete all of the data for a user, enter the empty string or integer value for all of their attributes.


> [!NOTE]
> If you use Excel to edit the .csv file, use three single quotes (''') instead of two ('')- Excel sees a single quote (') as the escape character.

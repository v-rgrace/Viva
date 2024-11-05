---
title: "Organizational Data in Microsoft 365"
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
description: "Import Organizational Data in Microsoft Viva and Microsoft 365"
---
# Use your organizational data in Microsoft 365 and Microsoft Viva

*Organizational data* refers to employee data that your admin uploads by using the Organizational Data in Microsoft 365 feature. Organizational Data in Microsoft 365 combines this uploaded data with existing Microsoft 365 data to power certain capabilities in Microsoft 365 applications. This feature also helps improve your [Microsoft 365 User Profile](/graph/api/resources/profile?view=graph-rest-beta&preserve-view=true) data by ingesting organizational data that currently resides in your organization's external systems (such as human capital management systems). This helps fill in any gaps related to missing or stale user profile data and enables richer experiences in Microsoft 365 and Microsoft Viva.

*Microsoft 365 User Profile Data* refers to the information associated with a user's account and is stored in the Microsoft 365 User Profile. This information includes email address, phone number, job title, and other descriptive information.

Microsoft 365 User Profile Data comes from two main sources: either Microsoft Entra ID (formerly Azure Active Directory), which is the default setting, or from Organization Data in Microsoft 365 through a .csv file that you upload. The properties in the Microsoft Entra schema and in the Microsoft 365 User Profile match the column names in the .csv file and are referred to as *attributes* in Organizational Data in Microsoft 365. 

Use the following information to understand, prepare, and import your organizational data:

- [What data's available and how is it used](understand-orgdata.md)
- [Import the data](import-orgdata.md)
- [Attribute reference](orgdata-attributes.md)
-
> [!NOTE]
> Do you have Microsoft 365 Copilot? Check out [Use organizational data in the Microsoft Copilot dashboard](organizational-data-copilot.md) for important information about configuring and accessing the organizational data.

## Data attributes

When you upload a .csv file, you need to include at least one required attribute, **Microsoft_PersonEmail**, for each employee. Based on specific requirements for applications that use this data (for example, the Copilot Dashboard), you might need to upload additional fields. To learn how to set up and structure an organizational data .csv file, see [Prepare and import your organizational data](#prepare-and-import-your-organizational-data).

You can also include the following optional attributes. (The value in parentheses is the corresponding property name in the [Microsoft 365 User Profile](/graph/api/resources/profile?view=graph-rest-beta&preserve-view=true#relationships) schema.).

See [Attribute reference](#attribute-reference) for more details about the specific attributes, and [Attribute to property mapping](#attribute-to-property-mapping) for information on how the Organizational Data in Microsoft 365 attributes map to Microsoft 365 User Profile data.

- Names 
   - **Microsoft_FirstName** (first) 
   - **Microsoft_LastName** (last) 
   - **Microsoft_DisplayName** (displayName) 
- Positions  
   - Detail 
      - **Microsoft_JobTitle** (jobTitle) 
      - ***Microsoft_SecondaryJobTitle*** (secondaryJobTitle) - used for skills mapping
      - **Microsoft_JobDiscipline** (role) 
      - **Microsoft_LevelDesignation** (level) 
      - **Microsoft_Layer** (layer) 
         - Company 
            - **Microsoft_Company** (displayName) 
            - **Microsoft_CompanyCode** (companyCode)
            - **Microsoft_Organization** (department) 
            - **Microsoft_CompanyOfficeLocation** (officeLocation) 
               - Address 
                  - **Microsoft_CompanyPostOfficeBox** (postOfficeBox) 
                  - **Microsoft_CompanyOfficeStreet** (street) 
                  - **Microsoft_CompanyOfficeCity** (city) 
                  - **Microsoft_CompanyOfficeState** (state) 
                  - **Microsoft_CompanyOfficeCountryOrRegion** (countryOrRegion) 
                  - **Microsoft_CompanyOfficePostalCode** (postalCode) 
- Manager 
   - **Microsoft_ManagerEmail** (userId) 
- User Skills
   - **Microsoft_UserSkillNames** 

> [!IMPORTANT]
> - In the Microsoft 365 User Profile, Microsoft Entra data takes precedence over Organizational Data in Microsoft 365. When a service queries a Microsoft 365 User Profile, if there is both organizational data and Microsoft Entra data for a single attribute, the Microsoft Entra value is used. Learn how to customize the data precedence for your tenant in [Data usage](#data-usage).
>
> - If you upload organizational data through the Microsoft 365 admin center, that data is also accessible to and used by Viva Insights (except for those excluded attributes listed in [How Organizational Data in Microsoft 365 works with Viva Insights](#how-organizational-data-in-microsoft-365-works-with-viva-insights)). If you upload data from Viva Insights *first*, and then upload data using Organizational Data in Microsoft 365, the data is merged *and* Viva Insights will also use your organizational data. In this instance, whichever data value was uploaded most recently takes precedence.
>
> - Three name related attributes (**Microsoft_FirstName**, **Microsoft_LastName**, and **Microsoft_DisplayName**) are treated as a group in the Microsoft 365 User Profile, so if any one of them has a value in the input .csv file, the other two also need to have values. Otherwise, the specified value isn't stored in the Microsoft 365 User Profile.

 
## Prepare and import your organizational data 

Before you upload organizational data, you need to do the following:

1. [Download a .csv template](#step-1---download-a-csv-template)
1. [Structure the organizational data](#step-2---structure-the-organizational-data)
1. [Import your organizational data for the first time](#step-3---import-your-organizational-data-for-the-first-time)
1. [Update or make other changes to your data](#step-4---update-or-make-other-changes-to-your-data)

### Step 1 - Download a .csv template

1. Sign into to the Microsoft 365 admin center as a user with Global Admin permissions.
1. On the **Organizational Data in Microsoft 365** page (under **Setup > Migration and imports**), select **Get started** (if this is the first time you're importing data) or **New import**.
2. Select **Download CSV template**.

> [!NOTE]
> You can also use organizational data exported from another system, such as your HR software, as your starting point, as described in [Get an export of organizational data](/viva/insights/advanced/admin/prepare-org-data#step-3---get-an-export-of-organizational-data).

### Step 2 - Structure the organizational data
Now that you have your .csv file starting point, add the organizational data that you want to use in Microsoft 365, and then save the file.

There are two types of attributes you can add in your organizational data file: required and reserved optional. Attributes can be in any order in the file. 

- **Required** - The only attribute required by default is email address.
- **Reserved** - Attributes are reserved column headers for attributes that are currently used to calculate, filter, and group data.


#### Sample data file
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

### Step 3 - Import your organizational data for the first time 
After you create a .csv file with your data, the next step is to import the data, either from your local computer (for Viva Insights-licensed customers) or from a SharePoint site.

#### Upload the .csv file from your computer (for Viva Insights-licensed customers)
After you create the .csv file with your data, you can upload it directly from your local files. 

>[!NOTE]
> - Local upload is only available for Viva Insights-licensed customers.
> - There's a 25 MB limit on files uploaded directly from your local files. If your .csv file is larger, [upload it first to SharePoint](#upload-the-file-to-sharepoint) and then import it from there.

:::image type="content" source="media/orgdata-import-local.png" alt-text="A screenshot shows local import option. ":::

#### Upload the .csv file from SharePoint
First you need to upload the file from your local computer to a secure SharePoint location; then you import the data.

##### Upload the file to SharePoint
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

##### Import the data into Microsoft 365
Now you're ready to import the data. 

1. On the **Organizational Data in Microsoft 365** page (under **Setup > Migration and imports**), select **Get started** (if this is the first time you're importing data) or **New import**.
3. On the **Import data from SharePoint** page, enter the SharePoint location where you saved your .csv file. (If you copied the location at the end of the upload step, paste it here.) 
1. Confirm that you understand that the data you upload here may be processed by Viva and Microsoft 365, as well as non-Microsoft services that you've granted access to the data through Microsoft Graph. Select **Next**.
1. Review the details for your upload, and then select **Begin validation**.

Your organizational data is validated against the requirements for use with Viva and Microsoft 365 services. Validation takes a few hours; however it can take up to three days for your complete data upload to be available in the profile store. You can check the validation status on the **Organizational data** page in the admin center. When the validation is complete, you see a message that your data is in use and managed by Viva and Microsoft 365. 

Each end user's organizational data is stored in that end user's mailbox and respects the data residency rules for Exchange Online (as described in [Data Residency for Exchange Online](/microsoft-365/enterprise/m365-dr-workload-exo?view=o365-worldwide&preserve-view=true)).

### Step 4 - Update or make other changes to your data

Only the global admin can update or delete organizational data stored in the Microsoft 365 User Profile.

To update or delete an end user's organizational data, create and upload a new .csv file containing only the users whose data you want to update or delete. 

- To update a value, include all of the attributes that you want to update. Provide a different value for any attribute that you want to change. If you include an attribute but don't provide a value (but do **not** set it to an empty string), the current value in the Microsoft 365 User Profile is used (it isn't updated).
- To delete a value, set the value for the attribute to an empty string by using two single quotes (''). (Set the **Microsoft_Layer** attribute "-1".) To delete all of the data for a user, enter the empty string or integer value for all of their attributes.


> [!NOTE]
> If you use Excel to edit the .csv file, use three single quotes (''') instead of two ('')- Excel sees a single quote (') as the escape character.



## Attribute reference   	
The following table provides more details about the Organizational Data in Microsoft 365 attributes.

> [!NOTE]
> Be aware that **Microsoft_LevelDesignation** and **Microsoft_Layer** attributes don't have corresponding properties in Microsoft Entra. Because of this, the only way to add these values to a Microsoft 365 User Profile is by using the Organizational Data in Microsoft 365 feature.

|#|Attribute|Description|Data type|Example|
|-|-|-|-|-|
|1|Microsoft_PersonEmail|Unique identifier for the employee record - an employee's email address.|Email|person.name@xyz.com|
|2|Microsoft_ManagerEmail|Unique identifier for an employee’s manager - the employee's manager’s email address.|Email|manager.name@xyz.com|
|3|Microsoft_Organization|The internal organization or department name that an employee belongs to.|String|Financial Planning and Analysis|
|4|Microsoft_LevelDesignation|Level that represents an employee's experience, management level, or seniority within the organization. This is whatever public level designation your company uses.|String|Director|
|5|Microsoft_JobDiscipline|The discipline that an employee belongs to. For more actionable insights, avoid using too few or too many unique Job disciplines. This is the public job discipline.|String|Finance management|
|6|Microsoft_Layer|An employee's position within the organizational hierarchy, expressed as their distance from the top leader of the organization. For example, the CEO is at Layer 0. Avoid using too few or too many unique layers. This is the layer that is publicly available in your company.|Integer|2|
|7|Microsoft_FirstName|First name of the end user.|String|Alexa|
|8|Microsoft_LastName|Last name of the end user.|String|Smith|
|9|Microsoft_DisplayName|Preferred name of employee to display. This is the public display name an employee chooses to list.|String|Alexa Smith|  
|10|Microsoft_JobTitle|The public facing job title of the employee.|String|Software engineer|
|11|Microsoft_CompanyOfficeLocation|An employee’s company office location. This is a location code, like a building number, floor, or room. This shouldn't be an employee's home office or personal address.|String|2N|
|12|Microsoft_CompanyPostOfficeBox|The post office box number. This is the publicly available company office box number.|String|PO Box 12|
|13|Microsoft_CompanyOfficeStreet|The street. This is the publicly available company office street address.|String|NE 12th Street|
|14|Microsoft_CompanyOfficeCity|The city of the company office the user is associated with. This is the publicly available office address city.|String|Redmond|
|15|Microsoft_CompanyOfficeState|The state. This is the publicly available company office state.|String|Washington|
|16|Microsoft_CompanyOfficeCountryOrRegion|The country or region. It's a free-format string value, for example, "United States". This is the publicly available company office country or region.|String|United States|
|17|Microsoft_CompanyOfficePostalCode|The publicly available company office postal code.|String|98004|
|18|Microsoft_Company|Company name.|String|Contoso|
|19|Microsoft_CompanyCode|Legal entity number of the company or its subdivision.|String|A2518|
|20|Microsoft_SecondaryJobTitle|Secondary job title for the employee|String|Software engineer|
|21|Microsoft_UserSkillNames|Skills the employee has, separated by commas. This value is used for Viva Skills inferencing, so it's important to make sure the field uploaded here is a field that you want to use to generate skills for your users.|String|Project management, organization|

## Attribute to property mapping
The following table shows how Organizational Data in Microsoft 365 attributes map to properties in the Microsoft 365 User Profile schema.


|#|Attribute (column heading) in .csv file|Property in Microsoft 365 User Profile schema |
|-|-|-|
|1|Microsoft_PersonEmail |N/A <br><br>The email is converted to the Microsoft Entra objectId of the end user and is used for internal processing.|
|2|Microsoft_ManagerEmail|positions -> manager -> userId<br><br>The email is converted to the Microsoft Entra objectId for the manager and is stored in the Microsoft 365 User Profile.|
|3|Microsoft_Organization|positions -> positionDetail -> companyDetail -> department|
|4|Microsoft_LevelDesignation |positions -> positionDetail -> level |
|5|Microsoft_JobDiscipline |positions -> positionDetail -> role |
|6|Microsoft_Layer|positions -> positionDetail -> layer|
|7|Microsoft_FirstName|names -> first|
|8|Microsoft_LastName|names -> last|
|9|Microsoft_DisplayName|names -> displayName|
|10|Microsoft_JobTitle|positions -> positionDetail -> jobTitle|
|11|Microsoft_CompanyOfficeLocation|positions -> positionDetail -> companyDetail -> officeLocation|
|12|Microsoft_CompanyPostOfficeBox|positions -> positionDetail -> companyDetail -> physicalAddress -> postOfficeBox|
|13|Microsoft_CompanyOfficeStreet|positions -> positionDetail -> companyDetail -> physicalAddress -> street| 
|14|Microsoft_CompanyOfficeCity|positions -> positionDetail -> companyDetail -> physicalAddress -> city|
|15|Microsoft_CompanyOfficeState|positions -> positionDetail -> companyDetail -> physicalAddress -> state|
|16|Microsoft_CompanyOfficeCountryOrRegion|positions -> positionDetail -> companyDetail -> physicalAddress -> countryOrRegion|
|17|Microsoft_CompanyOfficePostalCode|positions -> positionDetail -> companyDetail -> physicalAddress -> postalCode|
|18|Microsoft_Company|positions -> positionDetail -> companyDetail -> displayName|
|19|Microsoft_CompanyCode|positions -> positionDetail -> companyDetail ->companyCode|
|20|Microsoft_SecondaryJobTitle|positions -> positionDetail -> secondaryJobTitle|

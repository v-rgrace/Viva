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
*Organizational data* is employee data that describe the users in your organization - their name, location, job role. You can import this information into Microsoft 365 and Microsoft Viva through a feature called **Organizational Data in Microsoft 365**. This data adds to and updates existing information from Microsoft Entra ID to provide more information in experiences like Viva Insights. You can also use your organizational data to refresh and extend the information in your users' [Microsoft 365 User Profiles](/graph/api/resources/profile?view=graph-rest-beta&preserve-view=true) with additional information that currently resides in an external system (for example, your HR system).

Use the following information to understand, import, and manage your organizational data:

- [Understand what organizational data is](#what-user-information-makes-up-your-organizational-data)
- [Import your organizational data](import-orgdata.md)
- [Understand how organizational data is retained and managed](orgdata-data-usage.md)
- [Attribute reference](orgdata-attributes.md)

> [!NOTE]
> Do you have Microsoft 365 Copilot? Check out [Use organizational data in the Microsoft Copilot dashboard](organizational-data-copilot.md) for important information about configuring and accessing the organizational data.

## What user information makes up your organizational data?

The Microsoft 365 User Profile is, essentially, a collection of attributes that describe each user, referred to as *Microsoft 365 User Profile Data* (the data stored in the Microsoft 365 User Profile). This information includes email address, phone number, job title, and other descriptive information.

Microsoft 365 User Profile Data comes from two main sources: either Microsoft Entra ID (formerly Azure Active Directory), which is the default setting, or from Organizational Data in Microsoft 365, which you upload manually (as a .csv file). 

>[!IMPORTANT]
> In the Microsoft 365 User Profile, Microsoft Entra data takes precedence over Organizational Data in Microsoft 365. When a service queries a Microsoft 365 User Profile, if there is both organizational data and Microsoft Entra data for a single attribute, the Microsoft Entra value is used. Learn how to customize the data precedence for your tenant in [Data usage](orgdata-data-usage.md#data-usage).

There's one required attribute for Organizational Data in Microsoft 365: **Microsoft_PersonEmail**, which associates the organizational data with a specific person. Other applications that use organizational data, like the Microsoft Copilot Dashboard, may have additional data requirements, so be sure to check. To learn how to import organizational data, see [Prepare and import your organizational data](import-orgdata.md).

You can also include the following optional attributes. (The value in parentheses is the corresponding property name in the [Microsoft 365 User Profile](/graph/api/resources/profile?view=graph-rest-beta&preserve-view=true#relationships) schema.).


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


See [Attribute reference](orgdata-attributes.md) for more details about the specific attributes, and [Attribute to property mapping](orgdata-attributes.md#attribute-to-property-mapping) for information on how the Organizational Data in Microsoft 365 attributes map to Microsoft 365 User Profile data.

> [!IMPORTANT]
>
> - If you upload organizational data through the Microsoft 365 admin center, that data is also accessible to and used by Viva Insights (except for those excluded attributes listed in [How Organizational Data in Microsoft 365 works with Viva Insights](orgdata-data-usage.md#how-organizational-data-works-with-viva-insights)). 

If you upload data from Viva Insights *first*, and then upload data using Organizational Data in Microsoft 365, the data is merged *and* Viva Insights will also use your organizational data. In this instance, whichever data value was uploaded most recently takes precedence.
>
> - Three name related attributes (**Microsoft_FirstName**, **Microsoft_LastName**, and **Microsoft_DisplayName**) are treated as a group in the Microsoft 365 User Profile, so if any one of them has a value in the input .csv file, the other two also need to have values. Otherwise, the specified value isn't stored in the Microsoft 365 User Profile.

Now that you understand what organizational data is and where it comes from, you're ready to [import your organizational data into Microsoft 365](import-orgdata.md).
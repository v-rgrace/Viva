---
title: "Understand what makes up your organizational data and how it's used and retained in Microsoft 365"
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
description: "Understand what makes up your organizational data and how it's used and retained in Microsoft 365"
---
# Understand what makes up your organizational data and how it's used and retained in Microsoft 365

Review the following information to understand how organizational data is used, stored, and deleted.

When you upload a .csv file, you need to include at least one required attribute, **Microsoft_PersonEmail**, for each employee. Based on specific requirements for applications that use this data (for example, the Copilot Dashboard), you might need to upload additional fields. To learn how to set up and structure an organizational data .csv file, see [Prepare and import your organizational data](import-orgdata.md).

You can also include the following optional attributes. (The value in parentheses is the corresponding property name in the [Microsoft 365 User Profile](/graph/api/resources/profile?view=graph-rest-beta&preserve-view=true#relationships) schema.).

See [Attribute reference](orgdata-attributes.md) for more details about the specific attributes, and [orgdata-attributes.mdAttribute to property mapping](#attribute-to-property-mapping) for information on how the Organizational Data in Microsoft 365 attributes map to Microsoft 365 User Profile data.

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


## How Organizational Data in Microsoft 365 works with Viva Insights
The data uploaded here's also used in Viva Insights and is mapped to these Viva Insights reserved fields:

- PersonId
- ManagerId
- Organization
- LevelDesignation
- FunctionType
- Layer
- Location

The following data is uploaded from the Organizational Data feature but isn't available for use in Viva Insights:
- Microsoft_DisplayName
- Microsoft_FirstName
- Microsoft_LastName
- Microsoft_SecondaryJobTitle
- Microsoft_UserSkillNames

These attributes are available to use as custom attributes in Viva Insights.
- Microsoft_JobTitle
- Microsoft_City
- Microsoft_CountryOrRegion
- Microsoft_PostalCode
- Microsoft_PostOfficeBox

## Data usage
The organizational data you upload may be used by Viva, Microsoft 365 services, and non-Microsoft services that have been given access through the Microsoft Graph API. *This data is treated as **publicly available** within the organization, meaning it may be displayed to any end user in the organization. This data might also be used in [cross-tenant collaboration scenarios](https://support.microsoft.com/office/what-is-a-shared-channel-in-microsoft-teams-e70a8c22-fee4-4d6e-986f-9e0781d7d11d), in Microsoft 365 Copilot, and machine learning model training.*

In the Microsoft 365 User Profile, Microsoft Entra data is given precedence over Organizational Data in Microsoft 365 by default. When a service queries a Microsoft 365 User Profile, if there's both organizational data *and* Microsoft Entra data for a single attribute, the Microsoft Entra value is returned. For example, a given end user has "Software Engineer" as the jobTitle property in Microsoft Entra ID. The global admin for your organization uses the Organizational Data in Microsoft 365 feature to upload a value of "Senior Software Engineer" for the **Microsoft_JobTitle** attribute for that same end user. After the upload, both values are stored in the end user's Microsoft 365 User Profile. When an experience like [Profile cards in Microsoft 365](https://support.microsoft.com/office/profile-cards-in-microsoft-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501) queries the Microsoft 365 User Profile to get the **jobTitle** property for that end user, "Software Engineer" is returned (instead of "Senior Software Engineer").

If, however, there's no data for an attribute in Entra ID, the corresponding organizational data value is used. So, in the previous example, if there's no value for **jobTitle** in Entra ID, the Profile card in Microsoft 365 uses "Senior Software Engineer" from Organizational Data in Microsoft 365.

If you prefer to use the value from your organizational data in the Microsoft 365 User Profile, contact Microsoft by sending a request to orgdatainm365support@microsoft.com. Include the subject line, "Request to give organizational data precedence over Microsoft Entra data in Microsoft 365 User Profile for Tenant [Name] [Tenant ID]." It can take up to four days for this change to take effect. 

If you later want to switch back to the default behavior (where Microsoft Entra data is given precedence), contact Microsoft again, using a subject line of, "Request to give Microsoft Entra data precedence over Organizational Data in Microsoft 365 User Profile for Tenant [Name] [Tenant ID]." This change also takes up to four days.

To ensure that the data in the Microsoft 365 User Profile remains up to date and accurate, we recommend that you upload refreshed organizational data regularly (for example, weekly). This prevents the data in the user profile from becoming stale when compared to the data in your organization's human capital management systems.

Ensure that the data you upload matches attribute names and descriptions listed in the [Attribute reference](#attribute-reference). Also avoid uploading [sensitive personal data](https://commission.europa.eu/law/law-topic/data-protection/reform/rules-business-and-organisations/legal-grounds-processing-data/sensitive-data/what-personal-data-considered-sensitive_en).

## Data deletion
See [Update or make other changes to organizational data](#step-4---update-or-make-other-changes-to-your-data) for information about deleting user data. As soon as the update is processed, the associated user data is overwritten with blank fields, meaning their data is effectively deleted immediately.

When a tenant is removed from Microsoft 365, all tenant data is purged within 30 days.

## Data retention
Organizational data is stored as long as the end user is active and has a valid license and no deletion request has been made by the end user or the global admin.

## Data residency
When you upload organizational data, your .csv file is stored in your SharePoint Online site, and each end user's organizational data attributes are scoped to their Microsoft 365 User Profile and stored in the user's Exchange Online mailbox. For data residency information for SharePoint Online and Exchange Online, see [Data Residency for SharePoint Online](/microsoft-365/enterprise/m365-dr-workload-spo?view=o365-worldwide&preserve-view=true) and [Data Residency for Exchange Online](/microsoft-365/enterprise/m365-dr-workload-exo?view=o365-worldwide&preserve-view=true). 

### Manage data subject requests
A *Data Subject Request* or DSR is a formal request by a data subject (an end user) to a controller to take an action on their personal data. To understand what data subject rights end users have, see [Office 365 Data Subject Requests Under the GDPR and CCPA](/compliance/regulatory/gdpr-dsr-office365). 

Use the following information to fulfill DSRs from end users:

- Access and Export – An end user can access and export organizational data uploaded by a global admin and stored in the Microsoft 365 User Profile by using the data export function in the profile card. See [Export data from your profile card](https://support.microsoft.com/office/export-data-from-your-profile-card-d809f83f-c077-4a95-9b6c-4f093305163d). 
- Edit – see [Update or make other changes to organizational data](#step-4---update-or-make-other-changes-to-your-data). 
- Delete – see [Update or make other changes to organizational data](#step-4---update-or-make-other-changes-to-your-data) and [Data deletion](#data-deletion). 

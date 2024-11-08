---
title: "Organizational Data in Microsoft 365 - Attribute reference"
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
description: "Organizational Data in Microsoft 365 - Attribute reference"
---
# Organizational Data in Microsoft 365 - Attribute reference   	
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

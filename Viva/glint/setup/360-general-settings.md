---
title: Viva Glint 360 feedback General Settings 
description: 360 feedback setup begins in the General Settings section of the admin dashboard.
ms.author: JudithWeiner
author: JudyWeiner
manager: mbarry
audience: admin
f1.keywords: NOCSH
keywords: localization, supported languages, dashboard languages
ms.collection:  
- m365initiative-viva
- selfserve 
search.appverid: MET150 
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 11/15/2024
---

# Viva Glint 360 feedback General Settings 

1. From the Glint admin dashboard, select the **Configuration** symbol and then **General Settings**. 
1. Review selections that apply to all your Glint programs and confirm that 360 items are set up. 
1. [View, edit, or update the information](manage-general-settings.md).

Focus on these items:

|Section|Item to set up|Description|
|-------|---------|---------|
|**Company information**|**Top-level Manager (CEO**)|Confirm that the top-level Manager/CEO for your organization is selected. Manager Hierarchy is a critical piece of information used in 360s to determine feedback provider category assignments and 360 report access.|
|**Engage Survey Details**| **Require Azure AD for links in survey emails** | Viva Glint Admins, 360 Admins, and 360 subjects must exist in and authenticate with Microsoft Entra ID to access 360 feedback items. Feedback provivders have two access options based on the this access setting. Confirm whether this is set to: <br><br> <ul><li>**Yes** to require all users to authenticate with Microsoft Entra ID, or </li> <li>**No** to allow feedback providers to give feedback without authenticating with Microsoft Entra ID</li></ul> <br> **Note:** This setting applies to all surveys and not just 360 feedback programs. [Learn more about survey access methods](understand-survey-access-methods.md)
|**Features**|**Community Enabled**|Define if access to Viva Glint’s community is allowed |
|**Features**|**Default Focus Area Privacy**|Set privacy level for users to search for, view, and comment on other users’ focus areas:<br><br><ul><li> **Publicly Visible** - Everyone in the organization </li><li> **Visible to Manager** - The user’s manager, up-level managers, or anyone configured with custom focus area access </li><li> **Visible to Manager and Directs** - The user’s manager, up-level managers, direct reports, or anyone configured with custom focus area access </li><li> **Visible to Manager and Full Team** - The user’s manager, up-level managers, everyone who reports up to the user, or anyone with custom focus area access to the manager </li></ul>|
|**Localization**|**Supported Survey Languages**|Determines which survey languages are available for users to select in a 360 feedback program|
|**Localization**|**Supported Dashboard Languages**|Determines which dashboard languages are available to select in a 360 feedback program|

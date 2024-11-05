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

> [!NOTE]
> Do you have Microsoft 365 Copilot? Check out [Use organizational data in the Microsoft Copilot dashboard](organizational-data-copilot.md) for important information about configuring and accessing the organizational data.
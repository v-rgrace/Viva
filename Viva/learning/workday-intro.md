---
title: Introduction to Workday in Microsoft Viva Learning 
ms.author: bhaswatic
author: bhaswatic
manager: elizapo
ms.reviewer: chrisarnoldmsft
ms.date: 10/23/2024
audience: admin
ms.topic: article
ms.service: viva-learning
search.appverid: MET150
ms.collection:
  - enabler-strategic
  - m365initiative-viva-learning
  - highpri
  - Tier1
ms.localizationpriority: medium
description: Learn how to configure and manage Workday for Microsoft Viva Learning.

---

# Introduction Workday in Microsoft Viva Learning

This document introduces the process for configuring Workday as a content source in Microsoft Viva Learning.
It also outlines prerequisites and recommendations. 

The integration is based on Workday RaaS APIs (Report as a Service). Any breach in API contract might change the user experience. 
Integration supports catalog, assignment, and completions data from Workday. Catalog covers blended courses, digital courses, lessons, programs, and external providers integrated on Workday.

> [!NOTE]
> Catalog, assignments, and completion data are retrieved using RaaS (REST APIs). Thumbnails for Workday hosted content is retrieved using SOAP APIs, while thumbnails for third party content configured on Workday are retrieved using the RaaS report. The Workday-hosted thumbnails are stored in Viva Learning as metadata.

## Supported Workday scenarios 

| Scenario  | Supported/Not supported |
|---|---|
| Catalog types  | Viva Learning supports all catalog types from Workday. These types include: <ul> <li> Digital courses</li> <li> Blended courses <li> Programs (equivalent to learning paths in Viva Learning) <li>  Lessons <br> In addition to this Viva Learning supports ingestion of content from other learning providers configured in Workday, such as LinkedIn Learning configured in Workday.  | 
| Assignments on all catalog types from Workday  | Supported  | 
| Assignment completions  | Supported   |
| Self-enrollment completions  | Supported for all catalog types except lessons  | 
| Single sign-on  | Supported  | 
| Catalog Permissions from Workday  | Not supported – API not available from Workday  |  
| In app play  | Not supported by Workday  |  


## Prerequisites

You need the following permissions and scenarios in place to complete the Workday configuration process:

- Viva Learning Admin access
- Workday Admin access
- User mapping between Microsoft Entra ID (formerly Azure Active Directory) and Workday should be in place (check the RaaS report creation section for more details)
- Workday Web Service Endpoint & RaaS reports are available for Viva Learning integration with no inhibition by any network or firewall policies


### User mapping: 
User mapping between Workday and Viva Learning should exist before configuration.
 
The default user mapping is determined by the "username" field in Workday user RaaS Report and the UPN alias in the Microsoft Entra (formerly Azure Active Directory) system. For proper mapping or mapping to work, the username field needs an email alias and the UPN should have an email address. 
 
If there's any discrepancy in mapping logic used by the customer organization, please reach out to the Viva Learning product group. We have custom user mapping option available, which are controlled from the backend. The custom mapping is based on Workday attributes: Username, Email_address, and  employee_ID and corresponding AAD attributes as UPN alias, UPN, employee ID and custom AAD attributes. 

If there are duplicates in Microsoft Entra (formerly Azure Active Directory) for a particular user mapper, all the duplicate records are dropped from Viva Learning.

The mapping logic isn't case sensitive to the mapper values.

### Data ingestion timelines 

We're ingesting data for User RaaS from January 1, 1970 and catalog, assignment, and completion RaaS data from January 1, 2016. 
If any user has hiring date before 1970, reach out to the Viva Learning product group.  
If customer has different data ingestion timelines, reach out to the Viva Learning product group. 

## Integration recommendations

Recommendations for organizations that have Workday integrated with other 3P content providers such as LinkedIn, Udemy, and Coursera for tracking user completion records.

### Common practice

Organizations chose to have compliance trainings come from the learning management system (LMS) and growth, skill, and optional trainings come from digital content providers. 

- Compliance trainings have to be audited and tracked, with a few exceptions based on the regional policies.
- Growth/skill/optional trainings don't have to be tracked, but can be recommended to others.

### Deciding factors

These scenarios depend on whether Viva Learning is integrated with an LMS that includes 3P content providers or not.

We recommend not to have individual connector configurations for the included 3P content providers in the LMS, so that the same content isn't duplicated.

### For learning management systems that include 3P content providers

**Admin experience:**

- Less overhead in managing only the connector for LMS.
- Less overhead in maintaining the 3P content that is part of learning paths, collections, and other structured learning.

For learning management systems that don't include 3P content providers 
 
**Learner experience:**

- Consistent consumption experience for both contents coming from LMS and 3P providers.
- The **Assigned to you** tab shows the content assignment for 3P content.
- The **Completed** tab shows the history of completion status for 3P content.

**Admin experience**

- Manage multiple connectors for LMS and each 3P content providers.
- Manually update the 3P content that is part of learning paths, collections, and other structured learning when the connectors for 3P content are updated, deleted, enabled, or disabled.

**Learning experience**

- Mixed consumption experience for contents coming from LMS and 3P content providers.
- The **Assigned to you** tab doesn't show any assignment for 3P content as it can be only recommended.
- The **Completed** tab won't show the history of completion status for 3P content.

> [!NOTE]
> - Deleting connectors from the admin interface will remove only the courses from LMS and 3P content providers based on the connectors being deleted.  
> - Please note that some LMS connectors must be reconfigured only after the content catalog is cleaned up. Reach out to Viva Learning support for help.


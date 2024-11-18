---
title: Overview of Skills in Viva 
ms.author: bhaswatic
author: bhaswatic
manager: elizapo
ms.reviewer: chrisarnoldmsft
ms.date: 11/06/2024
audience: admin
ms.topic: article
ms.service: viva-learning
search.appverid: MET150
ms.collection:
  - enabler-strategic
  - m365initiative-viva-learning
ms.localizationpriority: medium
description: An introduction to Skills in Viva. 
---

# Overview of Skills in Viva 

 Skills in Viva is an AI-powered service in the Microsoft Viva Suite that delivers personalized skills-based experiences throughout supported Microsoft 365 and Viva applications for employees, business leaders, and HR. 

It uses data from Microsoft 365 profiles and the [Microsoft Graph](/graph/overview) combined with skills from the [LinkedIn Skills Graph](https://engineering.linkedin.com/blog/2022/building-linkedin-s-skills-graph-to-power-a-skills-first-world) to predict a user’s skills and offer tailored skill suggestions to users. At the same time, Skills in Viva provides you with a better understanding of your organization’s current workforce skills distribution. Learn more about [Skills in Viva](https://techcommunity.microsoft.com/t5/microsoft-viva-blog/introducing-ai-powered-skills-in-microsoft-viva-a-new-way-to/ba-p/3947844). 


If you’d like to learn more or apply for the Skills in Viva preview, contact your Microsoft representative. 

> [!NOTE]
> Skills in Viva is currently available only for private preview customers. The features described here are subject to change.

## Prerequisites 

To help ensure a productive preview that enables Skills in Viva to meet and exceed your company's goals, the following are the requirements for private preview participation: 

- Private preview must be deployed on a production tenant where users are spending at least 80% of their time on emails, documents, and other Microsoft 365 and Viva applications. 
- More than 100 users who are licensed for either Viva Suite or Viva Learning.  

> [!NOTE]
> Private preview is available only in English (en-US). 


## Admin roles 

The following roles and permissions are required to set up Skills in Viva. Review the documentation for [assigning roles](/entra/identity/role-based-access-control/manage-roles-portal). 


| Roles |  Permissions | 
| - | - | 
| Microsoft 365 Global Administrator | Microsoft 365 Global Administrator has global access to most management features and data across Microsoft online services. For Skills in Viva, the Microsoft 365 Global Administrator can configure and manage your organization’s skills library related settings from the Microsoft 365 admin center.| 
| Knowledge Administrator | The Knowledge Administrator needs to be assigned by the Microsoft 365 Global Administrator or the Privileged Role Administrator. The Knowledge Administrator can configure and your organization’s skills library and related settings from the Microsoft 365 admin center. | 

## Sharing and management of skills data

See [Set up Skills in Viva](skills-get-started.md) and [Manage your skills library](manage-skills-library.md) for information about how Skills data is shared and managed.

> [!NOTE]
> When individual users confirm skills in their skills experience available at [Skills in Viva](https://skills.cloud.microsoft), those skills will be visible to people in your organization by default. Users can manage which skills will be seen across the various skills-related experiences in Microsoft 365, such as the [profile card](https://support.microsoft.com/office/profile-cards-in-microsoft-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501), other Microsoft Viva products, and other connected applications, by toggling the visibility and learning options for each skill.


### Exporting skills

 Users can export the skills displayed on their profile card by selecting the ellipsis that appears at the top of the card and then **Export data**. This exports all of the data shown on the profile card to a file on their local computer.

:::image type="content" source="../media/skills/export-data.png" lightbox="../media/skills/export-data.png" alt-text="A screenshot of the Skills in Viva query view with a pic of a logged in user.":::


## View existing profile skills 

If a user added skills to their Microsoft 365 profile before joining the Skills in Viva private preview program, they can't see those skills on their Live Profile card during this current preview. 

Provide this information to users who are accessing these skills. 

1. Go to the profile editing page on your individual work SharePoint site. Replace `[tenant]` with the name of your tenant. 

    `https://[tenant]-my.sharepoint.com/_layouts/15/editprofile.aspx?`

    For example, at Microsoft, the URL for most people would be:  
    `https://microsoft-my.sharepoint.com/_layouts/15/editprofile.aspx?` 

For more information, see [URL considerations](#url-considerations).

2. Under **Edit Details**, select the **Details** tab. You see your existing skills under the Skills heading. You can copy or delete skills from this location. 


      :::image type="content" source="../media/skills/skills-edit-details-details-tab.png" lightbox="../media/skills/skills-edit-details-details-tab.png" alt-text="A screenshot of the Skills in Viva edit details tab with fields where you can fill in information like past projects, skills, schools, birthdays, and interests":::


### URL considerations 

If there are profile skills that previously appeared on the live profile card and don’t see them here, there could be more characters in the URL for your individual work SharePoint site.
 
1. Go to your individual SharePoint site, which you can find using first part of the URL. Replace `[tenant]` with your tenant name:
`https://[tenant]-my.sharepoint.com`
 
2. When your individual SharePoint page loads, check if the address contains other characters after the word SharePoint.  

3. Append the address you get with `/_layouts/15/editprofile.aspx?`  

    This address takes you to the correct editing experience where you see your existing profile skills:
    `[address that resolved in step 2]/_layouts/15/editprofile.aspx?`

Reach out to your IT admin for more guidance. 
 
To add skills to your current skills profile,  don’t use this SharePoint experience. Go to [Skills in Viva](https://skills.cloud.microsoft). 

### Next steps

[Set up Skills in Viva](skills-get-started.md)

[Manage your skills library](manage-skills-library.md)

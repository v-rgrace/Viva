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
> When individual users confirm skills in their skills experience available at [Skills in Viva](https://skills.cloud.microsoft), those skills will be visible to people in your organization by default. Users can manage which skills will be seen across the various skills-related experiences in Microsoft 365, such as the [profile card](https://support.microsoft.com/office/profile-cards-in-microsoft-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501), other Microsoft Viva products, and other connected applications, by toggling the visibility and/or learned/learning options for each skill.

## View existing profile skills 

If a user added skills to their Microsoft 365 profile before joining the Skills in Viva private preview program, they won't see those skills on their Live Profile card during this current preview. 

To access profile skills and shared skills added through Skills in Viva for an individual user, you can: 

1. Go to the [Microsoft Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)

1. Enter one of the following in the **Query** bar.
    1. To access a user's skills, replace [EmailAddress] with their corporate email address in the URL. Don't include the brackets. 
    `https://graph.microsoft.com/beta/users/[EmailAddress]/profile/skills?$select=displayName,createdBy `
    2. If a user needs to access their own skills: 
    `https://graph.microsoft.com/beta/me/profile/skills?$select=displayName,createdBy`

3. Select **Run Query**.

4. In the **Response preview** pane, you see a detailed response that includes skill names with information about each skill, as shown here.  

    For example, the skill shown in the response pane is “Product Management” and the display name under the heading “createdBy” (which indicates the skill source) is the user profile application (UPA). The reference to UPA means this skill is one added to the selected user’s Microsoft 365 profile outside of the current preview experience.

    You can save this list of skills by copying it and then pasting it into the document of your choice.
 
    > [!NOTE]
    > If you receive an error when running this query, confirm that you're logged into your corporate user account on this website. You should see your profile image on the toolbar at the top of the screen (shown in the following screenshot as a blue circle). If you don't, click the image placeholder to log in and then try to run the query again.

    :::image type="content" source="../media/skills/user-profile-application.png" lightbox="../media/skills/user-profile-application.png" alt-text="A screenshot of the Skills in Viva query view with a pic of a logged in user.":::

### Next steps

[Set up Skills in Viva](skills-get-started.md)

[Manage your skills library](manage-skills-library.md)

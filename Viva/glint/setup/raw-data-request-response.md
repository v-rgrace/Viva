---
title: Responding to Data Subject Requests (DSRs) in Microsoft Viva Glint
description: 
ms.author: JudithWeiner
author: JudyWeiner
manager: MelissaBarry
audience: admin
f1.keywords: NOCSH
keywords: Microsoft Viva Glint, raw data, extreme circumstance
ms.collection: 
 - m365initiative-viva
 - selfserve
 - essentials-compliance
 - essentials-security
search-appverid: MET150
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.custom: CELA-approved
ms.date: 10/31/2024
---

# Responding to Data Subject Requests (DSRs) in Microsoft Viva Glint

Viva Glint admins, designated by your Microsoft 365 Global Admin, can use in-product admin functionality to respond to DSRs from Viva Glint survey participants. Read more about DSRs.

> [!NOTE]
> Raw survey response export doesn't need to be enabled to fulfill DSRs. Admins can send a survey taker’s raw survey responses directly to the survey taker without accessing or viewing this data.

> [!IMPORTANT]
> Customers can use program setup features to respond to users' Data Subject Requests (DSR).
> 
> For information on how to support a request to delete data, visit Delete user data from Viva Glint. For information on how to export user data visit the section Use the People feature to export responses.

## Use the People feature to export responses

As the Viva Glint Admin, you can export a survey taker's user attributes and raw survey responses and send this data - without viewing it - directly to the survey taker. Attributes are populated from the data sent to Viva Glint in your Human Resources Information System (HRIS) file.

### Procedure to export user data

1. From the admin dashboard, select the **Configuration** symbol, then in **Employees** choose **People**.
1. Search for the user in the **Search People** field.
1. On the user's profile, select **Send User Data** from the **Actions** dropdown menu.
1. In the **Send User Data** slider:
   1. Enter an email address in the **User's Personal Email Address** field if data should be sent to a personal email. If not, enter the user's work email address.
   1. There's the option to **Include raw survey responses**. Select this option to include the user's responses surveys. Data can't be extracted during a live survey.
   2. In the **Send User Data** slider, all attributes from your HRIS file are preselected.
      1. Select **Clear All** and then select the attributes you want to export, or
      1. Exclude attributes from the export by deselecting them.
1.	Select **Send**. A "**User data export sent successfully**" message appears.
2.	Send the encrypted, compressed file of the user's data that downloads to your device to the requesting employee.
1.	The employee receives an email with a password to decrypt their compressed folder.

:::image type="content" source="../../media/glint/setup/dsr-email.png" alt-text="Screenshot of the email that a user receives after their data has been exported from Glint, including a password to access their compressed, encrypted file.":::

>[!TIP]
> For more information on how to support a request to delete data, visit [Delete user data from Viva Glint.](/../../viva/glint/setup/delete-user-data)



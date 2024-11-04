---
title: Responding to Data Subject Requests (DSRs) in Viva Glint
description: Viva Glint admins can use in-product admin functionality to respond to DSRs from Viva Glint survey participants.
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
ms.date: 11/04/2024
---

# Responding to Data Subject Requests (DSRs) in Viva Glint

Viva Glint Administrators, designated by your Microsoft 365 Global Admin, can use in-product admin functionality to respond to DSRs from Viva Glint survey takers. [Read more about DSRs](/viva/glint/setup/gdpr-special-categories).

For information on how to support a request to delete data, visit [Delete user data from Viva Glint](delete-user-data.md). For information on how to export user data, visit the section [Use the People feature to export responses](#use-the-people-feature-to-export-responses).

## Delete user data

> [!CAUTION]
> User data deletion in Viva Glint is an irreversible process. Learn more about Viva Glint [data deletion controls](delete-user-data.md).

1. From the admin dashboard, select the **Configuration** symbol, then in **Employees** choose **People**.
1. Search for the user in the **Search People** field.
1. On the user's profile, select **Delete User** from the **Actions** dropdown menu.
4. A Delete User Confirmation box displays with this information:
     1. Data is removed from Viva Glint except for essential account information associated with your organization’s Microsoft subscription.
     2. To include later, the information must be reuploaded into your company’s employee data.
     3. By deleting the user:
         1. Survey results are deleted, possibly impacting Viva Glint reports, if deletion control is set to off. [Learn more](https://go.microsoft.com/fwlink/?linkid=2286286).
         2. The user’s data is removed from distribution lists and future surveys.
         3. The user’s role definitions and their reporting permissions are removed.
     4. The display indicates whether the user has direct reports and that the admin needs to reassign the reports later or in the next employee data import. Follow these steps to facilitate a [**retroactive user upload update**](/../../viva/glint/setup/update-glint-reporting-data) if past survey data should reflect the new manager.
5. Return to the **People** page and verify that the user doesn't appear in the list of **All, Active or Inactive** employees.
6. Return to the admin dashboard and select **Activity Audit Log** in the **Service Configuration** section. The user deletion action should be listed in the **Event** column and its status should read "Success." The **Details** column should show "Deleted."
7. If the deleted user is a manager, verify that all reports their team appeared in no longer include their name. The report now reads, "Deleted User’s Team."

## Use the People feature to export responses

As the Viva Glint Admin, you send survey taker's user attributes and raw survey responses directly to the survey taker - without viewing it. Attributes are populated from the data sent to Viva Glint in your Human Resources Information System (HRIS) file.

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

## Correct user data

> [!CAUTION]
> - Don't perform a retroactive update while a Glint survey is live.
> - Deleted user data can't be retroactively updated.

As a Viva Glint Admin, you can update employees' current data or past data tied to closed survey cycles.

- To update **current employee data**, [choose an approved upload method](choose-upload-method.md) to transfer updated data to Glint.
- To update **past employee data tied to a closed survey cycle**:
  - Use the [Retroactive User Updates upload option](advanced-config-uploads.md#perform-retroactive-user-updates) for non-manager hierarchy information.
  - Use the [RETROACTIVE_PULSE_UPDATE Data App](glint-data-apps.md#retroactive-pulse-update) to correct manager hierarchy information.



---
title: Upload your employee attributes in Viva Glint
description: Learn how Viva Glint provides the most relevant results reporting when employee attributes are uploaded on a regular cadence.
ms.author: SarahBerg
author: SarahAnneBerg
manager: elizapo
audience: admin
f1.keywords: NOCSH
keywords: file requirements, upload attributes, manual upload, update attributes, Employee Attribute File
ms.collection: 
 - m365initiative-viva
 - selfserve
search-appverid: MET150
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 11/21/2024
---

# Upload your employee attributes to Viva Glint

User file imports help admins to keep users current with their organization's HRIS system. During the Platform Setup, learn how to upload employee data in the Microsoft Viva Glint application.

>[!WARNING]
> For security reasons, never email your employee attributes file.

> [!CAUTION]
> Ensure that all Company Admin users are included in your first file upload, with Employee IDs that match the IDs in Viva Glint. If not, Company Admin users will be deactivated and lose access to the platform.

### File requirements

Use the [employee data file checklist](data-checklist.md) to ensure that your data meets all of Viva Glint's requirements.

## Import employee data

The import function allows you to quickly modify employee records in bulk and add new users.

> [!TIP]
> Update your employee file on a regular basis. Ensure that your latest employee attributes have been sent and uploaded prior to a survey launch as your attributes can't be changed at the point of survey launch.

### Process for import of employee attributes

The following steps guide you through the process of importing the attributes manually: 

1. Select the **Configuration** symbol. 
2. In the **Employees** section, select **People**.
3. Select **Import** and then choose **Edit Employee List and Details**.

   :::image type="content" source="../../media/glint/setup/import-choice.png" alt-text="Screenshot of the import option selection screen, including the Edit Employee List and Details option."
   
5. Select the checkbox when updating all employee records, both in the file and in the system. 
6. Drag and drop your file or browse to choose it. Select **Upload File**. A message appears, informing you that an email sends once the upload is ready for review and confirmation.
7. Then, select **Close**.
8. After receiving the file upload email, go to the **People page** to confirm your upload.
   1. Alternatively, refresh the People page to monitor the upload status in the progress bar at the top of the page.
9. Select the **Review Upload** button in the top right of the People page.
10. In the **Confirm your import** dialog that appears, before selecting **Confirm Import**:
   1. Confirm that the **employees moved to inactive** count is accurate.
   2. Confirm that the **employee change** count is accurate.
   3. Confirm that the **employees added** count is accurate.
   1. [Troubleshoot errors](/viva/troubleshoot/glint/data-file-upload/data-file-upload-warnings-errors) as needed.

> [!NOTE]
> - Only the user performing the upload receives an email when the file has processed.
> - If the file isn't confirmed within 60 minutes of upload, it's cancelled.

## Update your employee data regularly

Your company can send employee data updates whenever necessary and based on whatever cadence works best for you. Some companies send daily, weekly, or monthly updates, while others don’t forward updates until they're ready to launch a survey. 

> [!TIP]
> Update your employee data weekly, or at least at a regular cadence. 
>
> If you have fewer than 10,000 employees, a daily feed of the full file should be sufficient, and you won’t have to send an incremental file. If you have a large employee base with several attributes (50+), sending full files 1-2 times per month with daily incremental files may make more sense for your company’s needs.

## Related topics

- [Create Employee Attribute Template](create-employee-attribute-template.md)
- [Understand upload errors and warnings](https://go.microsoft.com/fwlink/?linkid=2230863)

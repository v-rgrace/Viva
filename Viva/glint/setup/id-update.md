---
title: Update employee IDs in Viva Glint
description: Use the Microsoft Viva Glint employee ID update feature to keep employee information current.
ms.author: aweixelman
author: AliciaWeixelman
manager: melissabarry
audience: admin
f1.keywords: NOCSH
keywords: employee ID update, update user ID, ID update, ID correction
ms.collection: 
 - m365initiative-viva
 - selfserve
search-appverid: MET150
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 11/21/2024
---

# Update employee IDs in Viva Glint

Use the Microsoft Viva Glint employee ID update feature to keep employee information current. Viva Glint admins can update users' IDs one-off or in bulk when there are:

- Duplicated IDs
- Missed leading zeros
- Acquisitions
- Rehires
- Changes in HR information system (HRIS) vendor
- Incorrect IDs

## Update a user's employee ID

To update a user's ID:

1. From the admin dashboard, select the **Configuration** symbol and in the **Employees** section, choose **People**.
1. Search for and select a user to go to their Glint profile.
1. At the top of the page, select the pencil symbol next to **Employee ID**.

    :::image type="content" source="../../media/glint/setup/id-update-user-profile.png" alt-text="Screenshot of a user's Glint profile with the employee ID update option.":::

1. In the **Edit Employee Details** dialog that appears, enter a new value in the **Employee ID** field.
1. Select **Save Changes** to update the ID.

    :::image type="content" source="../../media/glint/setup/id-update.png" alt-text="Screenshot of an employee ID update on a user's Glint profile.":::

    > [!IMPORTANT]
    > Employee IDs must be unique for each user. If you update an ID to a value that's already in use by another user, you see this message: 
    > "**Update didn't save.** This Employee ID is already in use by user@contoso.com"

## Update employee IDs in bulk

To update users' IDs in bulk:

1. From the admin dashboard, select the **Configuration** symbol and in the **Employees** section, choose **People**.
2. In the menu on left side of the **People** page, select **All People** and then choose **Export**.
4. In the **Export All People** dialog that appears, switch the **Include all user attributes?** toggle to **Yes** and select **Export**.
5. A .csv file of all Glint users downloads to your device. To retain leading zeros and special characters when opening the file, [import it in Microsoft Excel](https://support.microsoft.com/office/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba).
1. Delete all columns except for:
   1. First Name
   1. Last Name
   2. Email Address
   3. Employee ID

      > [!IMPORTANT]
      > - To avoid upload errors, don't include **Status** or any other columns in the ID update file.
      > - The labels for required attributes in your Viva Glint tenant may differ from the columns listed in this article. For example, your ogranization may use Worker ID instead of Employee ID.
      
4. Delete users from the file that don't need an ID update and update values in the Employee ID column for remaining users.
6. Save the updated file in one of the following formats:
   1. .xlsx with a single sheet and no passwords or formulas
   2. .csv with a comma separator and UTF-8 encoding
3. On the **People** page, select **Import** and choose the **Employee ID Updates** option.

   :::image type="content" source="../../media/glint/setup/import-choice.png" alt-text="Screenshot of the import option selection screen, including the Employee ID Updates option.":::
   
5. Drag and drop or browse to choose your ID update file and select **Upload File**.
6. A progress bar at the top of the page show the status of the ID update file and you receive an email when the file is read to confirm.
7. When the upload is complete, select **Review Upload** on the **People** page.
8. In the **Confirm your import** dialog that appears, verify that:
   1. The number of IDs updated is correct
   1. There are 0 unchanged IDs
   2. There are 0 errors found. Select **Download Errors** to review a file of warnings/errors if needed. Use this article to troubleshoot: [Resolve upload errors related to employee ID updates](#troubleshoot-warnings-and-errors).
  
      :::image type="content" source="../../media/glint/setup/id-update-confim.png" alt-text="Screenshot of Confirm your import dialog with a summary of updates, errors, and a summary download option.":::
   
3. Optionally, select **Download Summary** to download a file summarizing ID changes to your device.
4. To finish the update, select **Confirm Import**.

   > [!IMPORTANT]
   > To prevent the ID update from cancelling, confirm the import within 60 minutes of receving the **Confirm your Glint file** email.

6. A progress bar at the top of the page show the status of the update and you receive an email when the file is successfully imported.

## Troubleshoot warnings and errors

You may see some of the following errors and warnings when updating IDs in bulk. Use the following guidance to troubleshoot and resolve issues.

### CONFIGURATION_ERROR: Columns

Error message:  

> This file must contain the First Name, Last Name, Email Address, and New Employee ID.  All of these columns must be present, with no additional columns.  Please correct and resubmit.  

This error occurs when the uploaded file includes extra columns, like Status.

#### Resolution

Remove all columns except for:

- First Name
- Last Name
- Email Address
- Employee ID

> [!IMPORTANT]
> The labels for required attributes in your Viva Glint tenant may differ from the columns listed in this article. For example, your ogranization may use Worker ID instead of Employee ID.

### MISSING_COLUMN

Error message:  

> Missing mandatory column `<attribute name>`. Add this column of data to your file and reupload.  

This error occurs when the uploaded file doesn’t contain one of the four required fields for employee ID updates.

#### Resolution

Update the file to include:

- First Name
- Last Name
- Email Address
- Employee ID

### UNEXPECTED_ATTRIBUTE

Error message:  

> The following attribute/attributes `'<attribute name1>'`, `'<attribute name2>'` are in file but not configured in Glint. If this is a new attribute, use the self-serve feature in Glint by navigating to Settings -> Configure -> People and add new attributes or email support.  

This error occurs when the columns in the uploaded file don’t match the columns labels in your Viva Glint attribute setup.

#### Resolution

Confirm the attribute labels configured in Viva Glint and update the file header row.

1.	Go to **Configuration** and select **People**.
2.	In the **Actions** menu, select **Manage User Attributes**.
3.	Review the **Active Attributes** section and make note of the **Required** field labels in the **User Attribute** column.
4.	Update the employee ID update file’s header row to match these labels and upload the file again.

### CONFIGURATION_ERROR: No new values

Error message:  

> All Employee Ids match the existing values for all users.  Please upload a different data file and resubmit. 
  
This error occurs when the employee IDs provided in the file match ID values already in Viva Glint.

#### Resolution

Review the uploaded file and provide new employee ID values.

> [!TIP]
> If the file is .csv format, [import it in Excel](https://support.microsoft.com/office/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba) to preserve the data in the expected format, including leading zeros.

### CONFIGURATION_ERROR: Blank IDs

Error message:  

> This file has a missing Employee Id at line x.  Please correct and resubmit.  

This error occurs when there are users in the uploaded file with blank employee ID values.

#### Resolution
Review the uploaded file and provide employee ID values where users have no ID listed.

### NO_EMPLOYEE_RECORD

Error message:  

> Line x with email user@contoso.com does not correspond to any existing user in Viva Glint.  Please correct and resubmit.  

This error occurs when the uploaded file contains email addresses, which Viva Glint uses to match records between the file and the platform, that don’t exist for any user in Viva Glint.

#### Resolution

Review the email addresses listed in the file and update to the email address that’s tied to the users in Viva Glint. 

1.	Go to **Configuration** and select **People**.
2.	Search for each user by first and last name.
3.	Note the email address for each user and update their record in the employee ID update file.

### SUSPICIOUS_VALUE

Error message:  

> Warning at line x: The First Name of y does not match the stored value of z.  

> OR  

> Warning at line x: The Last Name of y does not match the stored value of z.  

This warning occurs when the first and/or last name for a user doesn’t match what’s on file in Viva Glint. This warning doesn’t fail the ID update. 

#### Resolution
If the names changes are expected, you can ignore these warnings. If the names changes are unexpected, [upload an employee file](upload-employee-attributes.md#process-for-import-of-employee-attributes) to correct users’ names.

### DUPLICATE_IN_FILE

Error message:  

> Lines x and y contain the same Employee ID of zzz. Each ID must be unique.  Please correct and resubmit.

#### Resolution
Update employee ID values in the uploaded file so that all users have a unique ID and upload again.

### DUPLICATE_ID

Error message:  

> The Employee ID xxx on Line y is already associated with user@contoso.com.  Please correct and resubmit.

#### Resolution
Update employee ID values in the uploaded file to IDs that aren’t already tied to users in Viva Glint and upload again.

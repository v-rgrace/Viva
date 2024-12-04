---
title: Manage subjects, feedback providers, and coaches in a Viva Glint 360 feedback program
description: Selecting subjects, feedback providers, and coaches is done in the Manage Subjects sections of a Viva Glint 360 program.
ms.author: JudithWeiner
author: JudyWeiner
manager: mbarry
audience: admin
f1.keywords: NOCSH
keywords: 
ms.collection:  
- m365initiative-viva
- selfserve 
search.appverid: MET150 
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 12/04/2024
---

# Manage subjects, feedback providers, and coaches in a Viva Glint 360 feedback program

>[!TIP]
> Although **Manage Subjects** shows on the 360 Program Summary page ahead of **Cycle Settings**, configure cycle settings before adding Subjects. Access the **Manage Subjects** section after choosing your cycle.

:::image type="content" source="../../media/glint/setup/360-add-subject-in-manage-subjects.png"alt-text="Screenshot of the Add a Subject in the Manage Subjects cycle section.":::

## Manual addition of 360 Subjects

Selecting Subjects can be done manually or through an upload, if you’re adding a large number of Subjects. 

1. Search for the employee’s name in **Add a Subject**. Begin to type an employee’s name.
2. Select it from the dropdown menu.
3. The Subject name now appears in the **Manage Subjects** box.

## Bulk addition of Subjects and Coaches

1.	Select **Import Subjects**.
2.	In the window that displays, select **Download CSV**. [Read about CSV export and import here](/viva/glint/setup/360-export-import).
3.	Populate the .csv file with Subject unique IDs and email addresses and then add the names by selecting **Upload**. 

    :::image type="content" source="../../media/glint/setup/360-bulk-subject-coach-upload.png" lightbox="../../media/glint/setup/360-bulk-subject-coach-upload.png" alt-text="Screenshot of the Upload a Subject and Coach CSV window.":::

>[!NOTE]
> Coach assignment is optional, and selection is up to your organization. Managers are often coaches but don’t have to be. Coaches guide Subjects though their 360 report and are automatically granted report access.

## Select 360 feedback providers

Generally, allow the 360 Subject to select and review their own feedback providers as part of the 360 process. As an admin, however, you can select feedback providers on a Subject’s behalf.

>[!IMPORTANT]
> If 360s are being run for senior execs, prepopulated feedback providers are automatically invited.

:::image type="content" source="../../media/glint/setup/360-edit-add-providers.png" lightbox="../../media/glint/setup/360-edit-add-providers.png" alt-text="Screenshot of the ellipses section dropdown next to a Subject's name.":::

1. Select the **ellipses next to the Subject name** and then choose **Edit/Add Feedback Providers**.
2. Choose the appropriate feedback providers and then select **Invite Feedback Providers when cycle is live**. 

    > [!NOTE]
    > Emails are configured in the **Communications** setup for the cycle. That email is where Subjects see what tasks are left for them to complete their 360.

## Using the prepopulated Feedback Providers setting for senior leaders

In the Subject ellipses menu: 

1.	Select **Edit/Add feedback providers**. 
1.	Select **Invite feedback providers when Cycle is Live**. 

    Once selections are saved and the cycle is live, feedback providers receive an invitation to participate. The Subject can review and add other feedback providers during the cycle. 
    
    > [!NOTE]
    > Employees, other than the Subject, may be added to any feedback provider category but can’t be added to multiple feedback provider categories for a single subject.

## Add a coach

1. Select the ellipses next to the Subject name.
2. Select **Edit/Add Coach.**
3. Search for the coach's name using the search bar and select **Add Coach**.

   > [!IMPORTANT]
   > The role of coach is optional and the 360 program can proceed without it.
    
   :::image type="content" source="../../media/glint/setup/360-edit-add-coach2.png" alt-text="Screenshot of the ellipses section dropdown next to a Subject's name for adding a coach.":::

## Generate a CSV report

For any 360 cycle in draft or scheduled status, admins can download a CSV file by selecting the **Import Subjects** button and then the **Download CSV** link.

Download a CSV file to:
- Perform a bulk upload or download of Subjects
- Receive a time-based release of your 360 report
- Perform a bulk extension of the 360 end date for Subjects

:::image type="content" source="../../media/glint/setup/360-import-csv.png" alt-text="Screenshot of the Import Subjects button for a 360 program.":::

:::image type="content" source="../../media/glint/setup/360-download-csv.png" alt-text="Screenshot of the Upload a Subject and Coach CSV file dialog box for a 360 program.":::

Open your CSV download in a new tab. These columns generate:

|Column|Column header|
|------|---------|
|A|Subject Employee ID|
|B|Subject Email Address|
|C|Subject First Name (optional)|
|D|Subject Last Name (optional)|
|E|Coach Employee ID|
|F|Coach Email Address|
|G|Coach First Name (optional)|
|H|Coach Last Name (optional)|
|I|Remove Action|
|J|Glint Error Message - Leave Blank

### Use the Remove Action column

There are three ways to use the **Remove Action** column:

- Leave the cell blank to bulk upload a Subject or a Subject/Coach pair for a cycle
- Insert **SUBJECT** into a cell to remove the Subject from that cycle
- Insert **COACH** to keep the Subject but remove the Subject's coach from that cycle



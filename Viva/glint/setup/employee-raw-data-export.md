---
title: Access Viva Glint raw survey responses
description: Admins can export employee data and raw data from Viva Glint programs.
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

# Access Viva Glint raw survey responses

In Microsoft Viva Glint, "raw survey responses" refers to unaggregated survey responses that are directly tied to a survey taker. 
> [!NOTE]
> "Raw survey responses export" can also be referred to as "Raw data export."

## Does enabling raw survey response export make survey takers identifiable in reporting?

Export of raw survey responses is only available to your organization through admin controls. Viva Glint admins should consult with their privacy, HR, and legal teams. 

>[!NOTE]
> Reporting is aggregated for surveys with a minimum threshold of three (3) or more respondents.

## Configure raw survey response access
Your organization may not want access to raw survey responses for every survey. This data access decision could be because of the data's sensitivity, employee privacy concerns, regulatory or contractual obligations (such as Works Council agreements), or other reasons. Your role as the Viva Glint admin provides permissions for you to configure them at your discretion.

> [!IMPORTANT]
> When setting up each Viva Glint program, the Viva Glint admin decides whether raw survey response exports are available. Admins can change the raw response data toggle at any time during a survey program's lifecycle, but the change only applies to future survey cycles. Closed cycles are controlled by the raw response setting that admins established when the cycle launched. Raw survey export **doesn't** need to be enabled for an employee to request their personal data.

## Admins can opt out of response exports

By default, raw survey responses are available for each new program, but Viva Glint admins can opt out of response exports. 

### Procedure to opt of our response exports
Opting out of response exports occurs within the **Confidentiality** section of *Program Setup*. Program Summary is accessible from the *Survey Programs* configuration page of the admin dashboard. 

1. Select **Survey Programs** in the **Survey** section.
1. Select the survey and then **Program Setup** on the *Program Summary* page.

>[!NOTE]
> A program can't be in **Approved** status to enable this feature. As necessary, toggle **Approved** to **NO**. The default setting for **Enable Export of Raw Survey Responses** is **YES**. Toggle to NO to opt out of raw survey response export. [Read more about the confidentiality statement](https://go.microsoft.com/fwlink/?linkid=2238614).

To ensure customers meet their Data Subject Rights (DSR) obligations, Viva Glint provides an alternative solution, allowing customers to fulfill DSR requests without accessing the requestors raw survey responses. Read on.

> [!IMPORTANT]
> Even when an admin has opted out of raw survey response exports, the Glint admin can still access data if it meets **extreme circumstance** criteria. It's possible that Glint needs to disclose survey feedback when there is a good faith belief that disclosure is reasonably necessary to protect your safety, the rights and safety of Glint personnel or others, or to investigate, prevent or take action regarding suspected illegal activity, suspected fraud, situations involving potential threats to the physical safety of any person, or if otherwise required by law to do so.
>
> The privacy statement complies with GDPR notice requirements.

## Disable Raw Data Export access

**Important**: Disabling Raw Data Export (RDE) means that: 
- Admins can't access or export this survey data unless your organization believes extreme circumstance requirements exist. In this case, a Viva Glint admin can enable the export.
- Microsoft won't facilitate direct transfers to third parties, such as alternative survey platforms or data analytics consultants.
- The customer remains the data controller and Microsoft permanently prohibits customer access to non-RDE survey data at the *customers' explicit instruction*.

## Export company-level raw data

For closed surveys where raw survey responses were enabled, admins can export raw survey responses from Viva Glint. 

### Export raw response data for Recurring and Ad Hoc surveys

1. Go to **configuration** and select **Survey Programs.**
2. Select your survey program and go to the **Completed** cycles tab.
3. On the row with the appropriate cycle, select the ellipses (three dots) and then **Export Raw Survey Responses.**
4. In the export pane that appears:
   1. Choose whether to include **Comments**, **Survey Sent Date**, and **Use question's description instead of UUID** in the **Export Options** section.
   2. Select attributes that you want to include in the **Attributes** section.
   3. After making all selections, select **Export**.
5. Your .csv file downloads to your device. Larger files can take more time to generate; you receive an email when your file is ready to download.

### Export raw response data for Lifecycle and Always-On surveys

1. Go to **Configuration** and select **Survey Programs.**
2. Select your survey program and then the **Actions** menu.
3. Choose **Export Raw Survey Responses.**
4. In the export pane:
   1. Select a Start Date and End Date in the **Date Range** section.
   2. Choose whether to include **Comments**, **Survey Sent Date**, and **Use question's description instead of UUID** in the **Export Options** section.
   3. Select attributes that you want to include in the **Attributes** section.
   4. After you make all selections, select **Export**.
5. The .csv file downloads to your device. Larger files can take more time to generate; you receive an email when your file is ready to download.

### Raw survey response file layout

The fields included in your Viva Glint raw survey response exports vary based on the attributes that your organization sends, the selections that you make for your export, and the items included in your survey. The following columns will always be included, with a field for every survey item:

|Field Label  |Description   |Value Format|
|----------|-----------|------------|
|Survey Cycle Creation Date   |The date and time that surveys were generated for users.       |YYYY-MM-DD hh:mm:ss|
|Survey Cycle Completion Date|The date and time that surveys were completed by each user.    |YYYY-MM-DD hh:mm:ss|
|Survey Cycle Title|The name of the survey cycle.  |\<Month> \<Year> \<Program name> Survey|
|ItemText1  |Full text of survey item. |Numeric response value.|
|ItemText2  |Full text of survey item. |Numeric response value.|
|ItemText3  |Full text of survey item. |Numeric response value.|

>[!NOTE]
> - The export option is only be available to admins.
> -	The export option is only enabled for a survey cycle if the raw survey response export was enabled for the selected survey program before the survey went live.

>[!CAUTION]
> Once a survey is live, the choice to enable or disable raw survey response export can't be changed for that survey.




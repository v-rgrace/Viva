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
ms.date: 11/04/2024
---

# Access Viva Glint raw survey responses

In Microsoft Viva Glint, "raw survey responses" refers to unaggregated survey responses that are directly tied to a survey taker. 

## Who has access to raw survey responses?

By default, Viva Glint’s in-product reporting does not include raw survey responses and is reported in the aggregate. However, your organization may choose to make some surveys “identifiable,” meaning survey responses are directly linked to the survey taker. If a survey is identifiable, survey takers are informed before taking the survey. Learn more about [Viva Glint confidentiality and reporting](viva-glint-survey-privacy.md).

While raw survey responses are not included in Viva Glint default reporting, Viva Glint Administrators can export them unless export is disabled. Even when export of raw survey responses has been disabled, your organization may still access raw survey responses if it determines that certain Extreme Circumstances exist. Learn more about the [Extreme Circumstances exception](#exception-for-extreme-circumstances).

## Configuring raw survey response export

By default, raw survey responses are exportable for each new survey program, but Viva Glint admins can opt out of raw survey response exports. When setting up each Viva Glint program, the Viva Glint admin decides whether raw survey response exports are available. 

Admins can configure the Export Raw Survey Responses control at any time during a survey program, but the change only applies to future survey cycles. Closed cycles permanently conform to the setting established when the cycle launched. That is, if export was disabled when a survey cycle launched, enabling it later doesn't retroactively allow export of raw survey responses.

## Disabling export of raw survey responses permanently limits your access to this data

**Important: Disabling export of raw survey responses means that:**
- Your organization permanently loses the ability to access these raw survey responses unless you determine that certain Extreme Circumstances exist. Learn more about the [Extreme Circumstances exception](raw-data-extreme-circumstances.md). 
- If your organization leaves Viva Glint, you aren't able to take these raw survey responses with you.
- You aren't able to (and Microsoft isn't able to facilitate) transfer of these raw survey responses to a third party, such as an alternative survey platform or data analytics consultant.  

## Exception for Extreme Circumstances

Even if you have disabled export of raw survey responses, you can still identify a survey taker if your organization determines that Extreme Circumstances exist. 

### What does Extreme Circumstances mean? 

Extreme Circumstances exist if your organization determines that disclosure of a survey taker’s identity is necessary to investigate, prevent, or take action regarding illegal activities, suspected fraud, or situations involving potential threats to the safety of a person, or to otherwise comply with the law.

If your organization determines that Extreme Circumstances exist, you can make an Extreme Circumstances disclosure request, and Microsoft will identify the survey taker.

### Who determines whether Extreme Circumstances exist?

Your organization is solely responsible for determining whether Extreme Circumstances exist. Microsoft doesn't independently evaluate Extreme Circumstances disclosure requests. If your organization attests that Extreme Circumstances exist, Microsoft provides the requested identity of the survey taker.

[Learn how to make an Extreme Circumstances disclosure request](raw-data-extreme-circumstances.md).

## Responding to Data Subject Requests (DSRs) when export of raw survey responses is disabled

In some jurisdictions, Viva Glint users may have certain rights related to their personal data, including the rights to access, correct, delete, and restrict processing. Because raw survey responses are linked (or linkable) to identifiable survey takers, they are considered personal data. [Learn more about DSRs](/compliance/regulatory/gdpr-data-subject-requests).

If you need to provide a survey taker with their raw survey responses in order to fulfill a DSR, you can do so even if export of this data has been disabled. Viva Glint allows admins to send a survey taker’s raw survey responses directly to the survey taker without accessing or viewing this data. Learn how to [respond to DSRs in Viva Glint](raw-data-request-response.md).

## Configure raw survey response exports

By default, export of raw survey responses is enabled for each new Viva Glint survey program. However, the Viva Glint admin can disable export using a control in the Confidentiality section of Program Setup.

1.	Select Survey Programs in the Survey section.
2.	Select the survey and then Program Setup on the Program Summary page.
3.	Find the Confidentiality section of the Program Setup page.
4.	Here you will find a control entitled “Enable Raw Survey Response Export.” 
5.	By default, the control will be set to YES, meaning export is enabled.
6.	To disable export of raw survey responses, set the control to NO.

> [!NOTE]
> You cannot enable export of raw survey responses when a program is in Approved status. To enable raw survey response export, ensure Approved is set to NO. 

Opting out of response exports occurs within the **Confidentiality** section of *Program Setup*. Program Summary is accessible from the *Survey Programs* configuration page of the admin dashboard. 

1. Select **Survey Programs** in the **Survey** section.
1. Select the survey and then **Program Setup** on the *Program Summary* page.
2. The default setting for **Enable Export of Raw Survey Responses** is **YES**. Toggle to **NO** to opt out of raw survey response exports. [Read more about the confidentiality statement](viva-glint-survey-privacy.md).

## Export raw survey responses

If export is enabled for a survey program, you can export raw survey response by using the following procedures:

### Export raw survey responses for Recurring and Ad Hoc surveys

1.	Go to the **Configuration** page and select **Survey Programs.**
2.	Select your survey program and go to the **Completed cycles** tab.
3.	On the row with the appropriate cycle, select the ellipses (three dots) and then **Export Raw Survey Responses.**
1. In the export pane that appears:
   1. Choose whether to include Comments, Survey Sent Date, and Use question's description instead of UUID in the Export Options section.
   1. Select attributes to include.
   2. After making all selections, select **Export.**
5.	Your .csv file downloads to your device. Larger files can take more time to generate. You receive an email when your file is ready to download.

### Export raw survey responses for Employee Lifecycle and Always-On surveys

1.	Go to the **Configuration** page and select **Survey Programs.**
2.	Select your survey program and then the **Actions** menu.
3.	Choose **Export Raw Survey Responses.**
1. In the export pane that appears:
   1. Select a Start Date and End Date in the Date Range section.
   2. Choose whether to include Comments, Survey Sent Date, and Use question's description instead of UUID in the Export Options section.
   1. Select attributes to include.
   2. After making all selections, select **Export.**
5.	The .csv file downloads to your device. Larger files can take more time to generate. You receive an email when your file is ready to download.

## Raw survey response file layout

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
> - The export option is only available to admins.
> -	The export option is only enabled for a survey cycle if the raw survey response export was enabled for the selected survey program before the survey went live.

>[!CAUTION]
> Once a survey is live, the choice to enable or disable raw survey response export can't be changed for that survey.

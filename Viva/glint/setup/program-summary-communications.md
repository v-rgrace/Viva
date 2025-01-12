---
title: Communications setup in Program Summary
description: Notifying employees about a survey's start and sending reminders throughout the survey window are essential for improving survey participation.
ms.author: JudithWeiner
author: JudyWeiner
manager: MelissaBarry
audience: admin
f1.keywords: NOCSH
keywords: reminders, reminder times, additional languages, notifications, survey invite, disable survey email, disable survey invite
ms.collection: 
 - m365initiative-viva
 - selfserve
search-appverid: MET150
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 12/09/2024
---

# Communications setup in Program Summary

Notifying employees about a survey's start and sending reminders throughout the survey window are essential for improving survey participation. 

:::image type="content" source="../../media/glint/setup/program-summary-comms-intro.png" alt-text="Screenshot of where to access Communications setup from Program Summary." lightbox="../../media/glint/setup/program-summary-comms-intro.png":::

> [!NOTE]
> Always-On programs don't include a Communications section. Skip this step.

There are three sections to set up:

- Notification Timing
- Email Settings
- Configure Notifications

## Notification Timing

:::image type="content" source="../../media/glint/setup/program-summary-comms-notification-timing.png" alt-text="Screenshot of the Notifications Timing section in Communications setup.":::

Send survey invites and reminders between the times that you select. Your organization's default time zone is selected in [General Settings](manage-general-settings.md#company-information). If your organization chooses to [send emails based on users' time zones](time-zones.md), the text in this setting reflects that.

> [!IMPORTANT]
> Viva Glint can successfully process 10,000 - 15,000 surveys and email invites per hour. Factor in these processing limitations and the number of employees in your distribution list when selecting a delivery window.

## Email Settings

Use the Email Settings section to determine email addresses used to contact users and whether to use multiple languages in email templates.

:::image type="content" source="../../media/glint/setup/email-settings.png" alt-text="Screenshot of the Email Settings section in Communications setup.":::

### Choose where email notifications are sent

When [personal email](send-employee-attributes.md#optional-system-attributes) is set up as an optional system attribute, this email option becomes visible. Select **Company email and personal email** to better contact exiting employees.

### Send survey notifications in multiple languages in a single email

If your organization has employees in areas where local guidelines require you to communicate in multiple languages, consider switching this toggle to **On** and [setting up emails in multiple languages](multi-lang-emails.md).

## Configure Notifications

The following sections display as setup actions and each field can be edited by selecting the **pencil symbol** that displays when selecting a row.

:::image type="content" source="../../media/glint/setup/survey-comms-config.png" alt-text="Screenshot of the Configure Notifications section in Communications setup.":::

### Editing the survey invitation

Select **Survey Start** to activate the **Survey Invitation** slider window.

Check **Send notification** to ensure that the send date is correct.

### Disabling the survey invitation

If you want to include content that the Viva Glint platform doesn't support - like URLs, HTML, images, or  videos - toggle the **Send Notifications** setting to **Off** and use your own email service for survey notifications.

> [!TIP]
> Always send your organization a survey invite! Participation is essential for uncovering useful feedback.

:::image type="content" source="../../media/glint/setup/comms-invite-slider.png" alt-text="Screenshot of the Survey Invitation slider window for the Communications setup page.":::

### Use Reminders

To encourage users to participate, use the first, second, third, and final reminder email templates during the survey window.

> [!NOTE]
> Survey takers only receive reminders if they haven't completed their survey. 

Use the **Pencil** symbol to open the window and then:

- Change reminder email dates, which are preset.
- Preview your reminder. You can change the language and preview the message in other languages.

### Add survey reminders

The dropdown menu from the **Add survey Reminder** button lets admins to add reminders. Reminders display on the Communications page with an alarm symbol.

:::image type="content" source="../../media/glint/setup/program-summary-comms-add-reminder.png" alt-text="Screenshot of the Add Survey Reminder dropdown menu for the Communications setup page.":::

### Customize email content

Use this email [customization guidance](email-content-customization.md) to add custom text to your Glint survey emails.

## Notifications when survey results are available

The results notification email is a one-time notification to let users know that survey results are available. The email sends to users in roles with **live** reporting access 24-hours before the email to all others (including phased access). 

> [!IMPORTANT]
> For all users to receive a results notification, ensure that all roles are granted access (phased or live) in the **Reporting** section of the survey program before the survey closes. 

To set up the results notification email:

1. From the admin dashboard, go to **Configuration** and choose **Survey Programs**.
1. Select a survey and go to the **Communications** section in **Program Summary**.
1. Select the **Edit & Preview** option on the **Survey End** email.
   1. This email is turned off by default.
1. In the edit pane that appears, switch **Send notification** to **On**.
2. In the **Send** field, enter a number of days after survey end date to send the email.
   1. The default is three (3) and the maximum is 30 days.
2. Select **Save Changes** in the top right of the edit pane.

> [!IMPORTANT]
> Access must be scheduled to be live 24 hours before the results notification email is scheduled for sending.

> [!NOTE]
> To edit **Team Conversations** notifications, [follow this guidance](/viva/glint/reports/team-conversations-administrator-setup).

## Configure Nudges

Set up who in your organization receives [Nudges](/viva/glint/communicate/communicate-with-nudges) to promote continued action on feedback. 

:::image type="content" source="../../media/glint/setup/program-summary-comms-nudges-button.png" alt-text="Screenshot of the Configure Nudges button on the Communications setup page.":::

Select **Configure Nudges** to open the **Nudges** setup page. Follow the in-platform guidance.

:::image type="content" source="../../media/glint/setup/program-summary-comms-nudge-configuration.png" alt-text="Screenshot of the Nudges setup page on the admin dashboard.":::

## Final saving of communication edits 

After adding or editing reminder dates, select the **right facing arrow** and then **Save and Continue**.

## Next Step

> [!div class="nextstepaction"]
> [Coaching setup in Program Summary](program-summary-coaching.md).

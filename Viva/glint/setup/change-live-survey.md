---
title: Make changes to a live Viva Glint survey
description: Viva Glint suggests changing a live survey only when necessary.
ms.author: JudithWeiner
author: JudyWeiner
manager: MelissaBarry
audience: admin
f1.keywords: NOCSH
keywords: Edit live survey, edit program summary
ms.collection: 
 - m365initiative-viva
 - selfserve
search-appverid: MET150
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 11/15/2024
---

# Make changes to a live Viva Glint survey

Some elements of a live survey can be adjusted, but only make live edits when necessary.

> [!IMPORTANT]
> The term "item" refers to any question or statement posed in a Glint survey.

Preview your survey before launching. Then follow these practices:

| **Best Practice** | **Considerations** |
| --- | --- | 
|**Don't stop the survey**|Unless you need to completely replace a survey cycle, never *stop* a survey. Many edits can be made while the survey is enabled.|
|**Make email and reminder edits only at the cycle level**| Program level changes don't apply to a live survey.|
|**Keep the meaning of a question intact**| If you need to fix spelling, grammatical or translation errors:<ul><li>The adjusted item meaning should remain the same before and after edits </li><li> To ensure the integrity of the survey results, don't adjust any rating scale or multiple-choice options.</li></ul>|
|**Always Save and re-approve**| When making live edits, save changes and *reapprove* the survey before ending your session. [Use this guidance for approving, previewing, enabling, and disabling your survey](/viva/glint/setup/preview-manage-enable-engage-programs).|
|**Make text changes uniformly**| Text changes need to be made across all languages included in the survey.|

## Process to edit a survey item

There are three entry points to choose from:
-	From the **Question Library** on your admin dashboard; doesn't require survey to go into unapproved state
-	From **Survey Programs, Live** 
-	From **Upcoming Surveys**

**Allow Survey Resubmission** in the **Program Setup** section of **Program Summary** must be toggled to **Yes.** <br>
If not toggled to **Yes**, a pop-up informs you that the change to **Yes** happens automatically when edits are saved.

:::image type="content" source="../../media/glint/setup/before-question-edit.png" alt-text="Screenshot of alert box for live item editing." lightbox="../../media/glint/setup/before-question-edit.png":::

### Scenarios and considerations for live survey changes 

Sometimes changing a live survey may be beneficial. 

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| The text at the beginning (top) and end (bottom) of the survey | The *Intro* or *Thank You* text needs adjustments or corrections. | Newly edited text is featured immediately and *only* on surveys that haven't started. |
| Item text | The phrasing of an item needs to be edited. | Glint pushes your edits into production (that is, live survey and reporting).<br><p>**Note:** Republishing can cause a disruption to employees taking the survey at the moment this change is implemented. They can start over by refreshing their page.|
| Adding or removing an item | You want to add a new item or remove an item from a live survey. | An item *can't* be added or removed from a live survey except in an *Always-On* or *Employee Lifecycle program. |
| Item order | The survey items need to be reordered. | The newly edited order is featured immediately but *only* on surveys that haven't yet been started. |

## Fields which can be edited 

- **Language** - From languages prepopulated in the dropdown menu.
- **Question Type** - Rating, multiple choice, open-ended.
- **Reporting Label** - For easy identification of your item.
- **Question Text** - Consider if it's as it should be. Wording shows verbatim. The **+ button** allows you to edit the question. Try not to edit our standard survey items! Item edits may impact language translations and the item's intention. This change can subsequentlly affect the accuracy of the benchmark tied to the item.
- **Instruction Text** - Use this space to provide survey takers with helpful information about how to answer this item.
- **Comment Placeholder Text**
- **Leave your comments here** appears by default, but this text can be customized.**Rating Scale** - five (5) or seven (7) points
- Decide whether to include the rating **Label for all options** - The **Low Value** (1-strongly disagree) and **High Value** (5- strongly agree) appear by default. To define values 2, 3, and 4, toggle to **YES** and then assign their meaning. For example: 2 = disagree.
- Decide whether to **Allow Comments** - Toggle to **Yes** or **No.**
- Decide whether this item can be an **Optional Question** - Toggle to **Yes** or **No.**
- **Suggested Action Template** - Use the dropdown menu to attach this item to a previously configured Suggested Action Template to help managers act on feedback.

Select **Save Changes** when editing is complete.

## Edit your live survey

The information is broken out across **Program Summary** setup pages.

## Program Setup

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| **Various** | You want to edit the **Program Name** or **Allow Survey Resubmission** | Edits are visible only to users who haven't started their survey. |
| **Additional languages** | You want to add a new language as a survey option. | If custom translation text isn't provided, Glint's standard text translations are featured. |

## Distribution

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| **Add users** | Employees not yet included in your *Employee Attribute File* need to participate in the survey. | From the admin dashboard, select the **People** section and then **Send Survey**. Each new user is sent the email invitation immediately. From then on, these new users receive reminders according to the same schedule as all other users. |
| **Edit a Distribution List** | The list of employees included or excluded in the survey needs adjustment. | A Distribution List can be adjusted at any time but doesn't automatically send a survey invitation to new users. Those invites have to be sent manually. |

## Schedule

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| **Survey launch date** | You need to postpone the launch date of the survey. | To avoid potential challenges, make this update a minimum of 24 hours before the survey is scheduled to go live. |
| **Response window** | You want to decrease or increase the number of days within the survey window. | Adjust a minimum of 48 hours before the original survey end date.<br>Also, make sure your *Communications* emails align with any updated survey window planning.<br><p>**Note** : Live *Schedule* edits are applied at the cycle level. |

## Items (Questions)

[Read extended guidance on live survey item (question) edits here.](/viva/glint/setup/question-edit)

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| **The text at the beginning (top) and end (bottom) of the survey** | The **Intro** or **Thank You** text needs adjustments or corrections. | Newly edited text is featured immediately on surveys that haven't been started. |
| **Question text** | The phrasing of an item needs to be edited. |Survey item rephrasing propagates to future programs only. A live program isn't affected by any edit.|
| **Add or remove a survey item** | You want to add a new item or remove an item from a live survey. | An item *can't* be added or removed from a live survey except in an *Always-On* or **Employee Lifecycle** program. |
| **Item order** | The questions need to be reordered. | The newly edited item order is featured immediately on surveys that haven't been started. |

### Admin process for editing a question during a live survey

There are three entry points for editing a question:
-	From the Question Library on your admin dashboard (doesn't require survey to go into unapproved state)
-	From the *Survey Programs, Live* section
-	From the *Survey Programs, Upcoming* section

**Allow Survey Resubmission** in the **Program Setup** section of **Program Summary** must be toggled to **Yes.** <br>
If not toggled to **Yes**, a pop-up informs you that the change to **Yes** is made automatically when your edits are saved.

### Inform survey takers of a live edit

> [!IMPORTANT]
> All survey participants must be made aware of the opportunity to retake a survey if a question is changed while the survey is live.
> <br>
> They must also understand that if they retake a survey, their original answers are replaced.

**You are responsible to notify participants about any change and provide instructions on how to do so. Survey retake access:**
-	Survey takers can use the link from their original survey invitation email to retake their survey.
-	[Use this guidance to resend survey invites](/viva/glint/communicate/support-survey-participants#resend-survey-invites)

For participants who haven't started the survey, the survey automatically updates with the new version of all items and no notification is required.

### Confirm edits 

Review your edits to make sure your employees receive appropriate notice. 
 
1. Review the **Confirm your changes** window that opens.

   :::image type="content" source="../../media/glint/setup/confirm-changes-dialog-box.png" alt-text="Screenshot of the confirmation dialog box for editing live survey questions."lightbox="../../media/glint/setup/confirm-changes-dialog-box.png":::

2. If everything is as expected, select **Confirm.**

3. A one-time notification confirms that your item is updated.

## Reporting

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| **All items in the Reporting section** | Any section in the Reporting section needs adjustment. | Save all changes, then return to the **Program Summary** and adjust the Approve toggle to **Yes**. |
| **Benchmark update** | Your external comparison benchmark was updated. | If changes are made to the benchmark in a live program, be certain users with live access are aware so they aren't confused by different results from a past viewing. |
| **Aggregate Indices** | You need to edit or add an aggregate index. | If changes are made to indices in a live program, be certain users with live access are aware so they aren't confused by results that are different their last viewing. |
| **Driver Impact Outcomes** | You need to edit or add Driver Impact Outcomes. | If changes are made to Driver Impact Outcomes, be certain ausers with live access are aware so they aren't confused by different outcome options available in the Driver Impact report. |

## Communications

Live Communications edits only apply when made at the cycle level.

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
| **Reminders** | You need to add or delete email reminders, or otherwise edit existing text. | Future reminders can be added, edited, or deleted if adjusted at least the day before they're scheduled to be sent. Reminders can't be added, edited, or deleted, on the day that they're scheduled. |
| **Results Notification** | You want to turn this feature on or off, edit existing text, or adjust the number of days until the message is sent. | To avoid potential challenges, make changes at least 48 hours before the closing of the survey window. |

## Other Live changes 

| **Topic** | **Scenario** | **Considerations** |
| --- | --- | --- |
|**Driver labels** | The reporting label for an item needs adjustment. | Proceed as needed. |
| **Manager hierarchies** | Your reporting displays incorrect leadership hierarchies due to errors in your Employee Attribute File. | Change only after the close of the survey window. |
| **Add bulk survey participants** | An extra group of employees needs to be added to the platform. | Submit a delta file of the employees to be added. Then, manually send them the survey invite from within the **People** configuration page. |
| **Add users not in the Distribution List** | Employees outside of the Distribution List need to be included. | From the admin Configuration dashboard, select the **People** feature, then **Employee**, then **Action**, then **Send Survey**. |
| **Email timing** | You want to adjust the time emails are sent. | Adjust timing at the cycle level only and consider the user time zones. |



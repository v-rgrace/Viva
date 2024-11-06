---
ms.date: 02/02/2024
title: "Create and edit a Viva Connections dashboard"
ms.reviewer: evanatkin
ms.author: evanatkin
author: AtkinE
manager: elizapo
audience: Admin
f1.keywords:
- NOCSH
ms.topic: article
ms.service: viva-connections
ms.localizationpriority: high
ms.collection:
  - Strat_SP_modern
  - M365-collaboration
  - m365initiative-viva-connections
  - highpri
search.appverid:
- SPO160
- MET150
description: "Learn how to edit the Viva Connections dashboard from Teams and SharePoint, how to apply audience targeting, and how SSO works with some dashboard cards."
---

# Create and edit a Viva Connections dashboard

The Viva Connections dashboard provides fast and easy access to information and job-related tasks. Content on the dashboard can be targeted to users in specific roles, markets, and job functions.

The dashboard consists of cards that engage viewers with existing Microsoft Teams apps, Viva apps and services, partner apps, custom solutions using the SharePoint Framework (SPFx) framework, internal links, and external links.

![Screenshot that shows a Dashboard example for desktop and mobile.](../media/connections/vc-dashboard-flw.png)

## Edit the dashboard from Microsoft Teams

The Viva Connections dashboard can be edited right from Microsoft Teams. You need member or owner level permissions to get started.

![Diagram of how to create a Viva Connections Dashboard.](../media/connections/viva-dashboard-step.png)

> [!NOTE]
>
> - When setting up Viva Connections for the first time, you’ll be asked to choose a set of default cards based on the intended audience.
> - You can choose mobile and desktop views interchangeably as you’re authoring.
> - Image recommendations for cards in the dashboard: medium cards should be 300x150 to 400x200 with 2:1 aspect ratio and large cards 300x300 to 400x400 with 1:1 aspect ratio to prevent stretching in the mobile app.
> - Image URLS in card properties must be an absolute URL for the link to work in the mobile app.
> - It's recommended to limit the number of cards to about 20 on the dashboard for the best viewing experience.
> - Users will be able to [customize their dashboard on Viva Connections mobile](https://support.microsoft.com/office/753e0607-0bfd-4712-ad7e-18490dd565a2#bkmk_customize-viva-connections-mobile-dashboard) by reordering, hiding, and showing cards. These changes only affect the mobile experience for the user and will not affect their desktop or tablet experience.

1. Navigate to the Viva Connections app in Teams.

2. Next, select **Edit** in the dashboard section.

3. Select **+ Add a card**.

4. Select **Edit** (pencil icon) for each card to edit properties like the label, icon, image, and audience targeting settings where applicable.

5. Select **Delete** (trash can icon) to remove cards.

6. Preview the experience on all devices to ensure usability before publishing or republishing.

7. **Publish** or **Republish** when you're done to share the edits with others.

### How to edit the dashboard from SharePoint when you have a home site

If your organization has a [SharePoint home site](home-site-plan.md), you can set up and edit the dashboard from the SharePoint home site or in Microsoft Teams. You need [edit permissions](/sharepoint/customize-sharepoint-site-permissions) for the SharePoint home site to make changes.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE53Joj]

<br>
<br>

> [!NOTE]
> Images are an important aspect to making your cards rich and inviting. If you're a SharePoint admin, we recommend enabling a Content Delivery Network (CDN) to improve performance for getting images. Consider when storing images that /siteassets is by default a CDN source when Private CDN is enabled while /style library is the default source when the Public CDN is enabled. [Learn more about CDNs](/office365/enterprise/content-delivery-networks).

1. From the SharePoint home site, select the **Settings** gear at the top-right of the page.

2. Select **Manage Viva Connections**.

3. Select the **+ Create dashboard** or **View dashboard** button.

4. Select **+ Add a card**.

5. Select the type of card you want to add from the dashboard card toolbox and then use the instructions within this article to set up each type of card. As you’re building the dashboard, you can preview its appearance in mobile and desktop for different audiences.

6. When you're done adding cards and [applying targeting to specific audiences](use-audience-targeting-in-viva-connections.md), **Preview** the experience to ensure an ideal viewing experience.

7. Once you’re satisfied with how the dashboard looks in preview, select **Publish** or **Republish** at the top-right of your dashboard to make it available for use on your home site, in Teams, and in the Teams mobile app.

### Use the Dashboard web part for Viva Connections

> [!NOTE]
>
> - After editing content on the dashboard, it may take several minutes until the new content is available in the Dashboard web part.
> - For best results, we recommend placing the Dashboard web part in a right vertical section.

Once a dashboard is authored and published, you can use the Dashboard web part to display it on your Connections site. You can add the web part to any section on your SharePoint  page.

![Screenshot of the Viva Connections Dashboard web part highlighted in the Connections site.](../media/connections/vc-dashboard-web-part.png)

When added, it will automatically be populated with the cards from the existing dashboard on your site. You can set the maximum number of cards you want to display. [Learn how to use the Dashboard web part](/sharepoint/use-dashboard-web-part-on-home-site).

## Available dashboard cards

|Toolbox icon   | Description  |
|:-------------:|:--------------|
| [![Screenshot of the card designer icon with a link to an article for more information.](../media/connections/use-card-designer/card-designer-card-icon.png)](use-card-designer.md) | Create your own cards or use quick views for a more interactive experience utilizing the [adaptive cards framework.](/adaptive-cards/templating/)|
| [![Screenshot of the approvals card icon with a link to more information.](../media/connections/approvals-card-icon.png)](available-dashboard-cards.md#add-the-approvals-card) | Use [Approvals](/power-automate/get-started-approvals) to approve vacation requests, documents, and expense reports. |
| [![Screenshot of the assigned tasks card icon with a link to more information.](../media/connections/assigned-tasks-card-icon.png)](available-dashboard-cards.md#add-the-assigned-tasks-card) |   Use [Tasks](/microsoftteams/manage-planner-app) to manage your team's work, assign tasks, and track tasks. |
| [![Screenshot of the Assignments card icon with a link to more information.](../media/connections/create-dashboard/assignments-card-icon-no-border.png)](available-dashboard-cards.md#add-the-assignments-card) | Display a summary of upcoming and past due assignments for students. |
| [![Screenshot of the Courses card icon with a link to more information.](../media/connections/create-dashboard/courses-card-icon-no-border.png)](available-dashboard-cards.md#add-the-courses-card) | Display a summary of courses a student is enrolled in. |
| [![Screenshot of the Events card icon with a link to more information.](../media/connections/events-card-icon-no-border.png)](available-dashboard-cards.md#add-the-events-card) |   View and join upcoming events within your organization. |
| [![Screenshots of the News card icon with a link to more information.](../media/connections/news-card-icon-no-border.png)](available-dashboard-cards.md#add-the-news-card) |   Promote news from various sources that you wish to prominently display, including [boosted news from SharePoint.](https://support.microsoft.com/office/boost-news-from-organization-news-sites-46ad8dc5-8f3b-4d81-853d-8bbbdd0f9c83)     |
| [![Screenshot of the OneDrive card icon with a link to more information.](../media/connections/create-dashboard/onedrive-card-icon-no-border.png)](available-dashboard-cards.md#add-the-onedrive-card) |   View and access recent, shared, and favorite files from your OneDrive account. |
| [![Screenshot of the People card icon with a link to more information.](../media/connections/people-card-icon-no-border.png)](available-dashboard-cards.md#add-the-people-card) |   Provide an option to look up contact information and directly chat, email, or call with others in your organization. |
| [![Screenshot of the Quick links card icon with a link to more information.](../media/connections/create-dashboard/quick-links-card-icon-nb.png)](available-dashboard-cards.md#add-the-quick-links-card) |   Provide list of relevant links or files to users selected by admins. |
| [![Screenshot of the shifts card icon with a link to more information.](../media/connections/shifts-card-icon.png)](#add-the-shifts-card) | Display information about the next or current shift from the Shifts app in Teams. |
| [![Screenshot of the Stream play list card icon with a link to more information.](../media/connections/create-dashboard/stream-playlist-card-icon-nb.png)](available-dashboard-cards.md#add-the-stream-playlist-card) |   Display a list of videos to users that can be viewed in Microsoft Stream. |
| [![Screenshot of the Teams app icon with a link to more information.](../media/connections/teams-app-icon.png)](available-dashboard-cards.md#add-a-teams-app-card) |   Use to open a Teams personal app or bot specified by the dashboard author. |
| [Parner card or Microsoft App](available-dashboard-cards.md#add-a-partner-card-or-microsoft-app) | Use cards that integrate [partner services.](https://cloudpartners.transform.microsoft.com/resources/viva-app-integration)     |
| [![Screenshot of the Viva Topics Contribute icon and Topics Discover icon with a link to more information](../media/knowledge-management/viva-topics-cards-toolbox.png)](available-dashboard-cards.md#add-the-viva-topics-card) |  Use Topics cards to encourage knowledge discoverability, engagement, and sharing. |
| [![Screenshot of the Viva Learning card icon with a link to more information.](../media/connections/create-dashboard/viva-learning-card-icon-2.png)](available-dashboard-cards.md#add-the-viva-learning-card) |  Provide a link to the Viva Learning app that can be targeted to show to certain audiences. |
| [![Screenshot of the Viva Pulse card icon with a link to more information.](../media/connections/create-dashboard/pulse-card-icon-nb.png)](available-dashboard-cards.md#add-the-viva-pulse-card) | Provide a short status of a recently sent pulse with a link to the Viva Pulse app for users to learn more. |
| [![Screenshot of the web link card icon with a link to more information.](../media/connections/web-link-icon.png)](available-dashboard-cards.md#add-the-web-link-card) |  Access a site without leaving the Viva Connections app.  |

## Apply audience targeting to cards

[Audience targeting can be applied throughout](use-audience-targeting-in-viva-connections.md) the Viva Connections experience, including cards on the dashboard. Audience targeting creates a personalized viewing experience by filtering the most important content to specific groups. Use audience targeting to:

- Create custom views for distinct roles and regions.
- Generate as many different views as needed to create unique experiences.
- Ensure the intended audience sees the most important content.

### Set the target audiences for a card

1. If your page isn't already in **edit** mode, select **Edit** at the top-right of the dashboard page.
2. Select the card you want to target to one or more audiences, and select the **Edit card** pencil from the toolbar on the left.
3. In the property pane on the right, under **Audiences to target**, type or search for the audience groups you want to target.

   > [!NOTE]
   > If you've selected an audience group that you recently created or changed, it may take some time to see targeting applied for that group.

4. When a card is successfully audience targeted, a **people** icon in the lower-left corner of the card appears.

   ![Screenshot showing the audience targeting confirmation icon.](../media/connections/audience-targeting-icon.png)

### Preview your dashboard to see how it displays for different audiences

After creating or editing cards on the dashboard, make sure you preview the experience for each audience and on both desktop and mobile devices. What you see in *preview mode* approximates how the dashboard displays for certain audiences and devices. When you apply audience targeting to cards, you can preview how different people view the dashboard depending on the audience or device. While in preview-mode, make sure:

- Physical gaps aren't present between cards that might appear while previewing different audiences and devices. If you see gaps, rearrange cards so that every audience and device has a high-quality viewing experience.
- Icons, graphics, and images are easy to identify and understand.
- Buttons and links are active and go to their intended destinations.
- Labels and description text are helpful, easy to read, and make sense for the intended audience.

#### To preview different audiences

1. While in edit mode, select **Preview** on the top right.

   ![Screenshot showing the audience targeting icon.](../media/connections/preview-dashboard.png)

2. Open the **Select audiences to preview as** drop-down list. (if no cards are audience targeted, you'll see a disabled **Audience targeting** label).

   :::image type="content" alt-text="This screenshot shows the audience targeting group label." source="../media/connections/preview-audiences.png":::
3. Search for and select a group. Once added, the group is selected by default. You can select the group again in the **Select audiences to preview as** drop-down list to deselect it.

   ![Screenshot showing the audience targeting panel in preview mode.](../media/connections/preview-dash-full-page.png)

   - Cards targeted to a specific group display.
   - When one or more audiences are selected, cards that *don't* have audience targeting applied will also display.
   - If no audiences are targeted, only cards that *aren't* audience targeted will display. If there aren't any cards with audience targeting applied, none will display.
   - If you aren't part of one of the audiences you've selected, you'll only see cards that aren't audience targeted. If none of the cards are audience targeted, you won't see any cards.

#### Examples

In the following example, the preview is set for mobile devices and highlights the different views that can be created from a single dashboard.

| View 1                  | View 2                 |
| :-------------------: | :-------------------: |
|![Screenshot of one view created for a specific audiences.](../media/connections/preview-dash-1.png) | ![Image of a second view created for a specific audiences..](../media/connections/preview-dash-2.png) |

## How URLs and single sign-on works

For some cards, you'll use links to URLs. Depending on the location of the content, links to URLs might display content in Microsoft Teams or elsewhere and [Single sign-on (SSO)](/azure/active-directory/manage-apps/what-is-single-sign-on) behavior can differ. Get more information about how links to URLs and SSO behave depending on the location of the content you're linking to.

> [!NOTE]
> When SSO is not supported, users will be asked to enter their login credentials.

| Opens URL to… | On Teams mobile | On Teams desktop |
| :------------------- | :------------------- |:---------------|
| Teams App | Teams apps (like Shifts, Approvals, or Kudos) open within Teams and user doesn’t need to authenticate again. | Teams apps (like Shifts, Approvals, or Kudos) open within Teams and user doesn’t need to authenticate again. |
| Forms  | Forms open within Teams, user is asked to sign-in on the first time, and user doesn’t need to authenticate again if they stay signed in. | Forms open within Teams, user is asked to sign-in on the first time, and user doesn’t need to authenticate again if they stay signed in. |
| Viva Engage | Viva Engage opens within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| PowerApps  | PowerApps opens within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| Power Portals  | Power portals open within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| Stream   | Stream opens within Teams, user is asked to sign-in on the first time and user doesn’t need to authenticate again if they stay signed in. | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |
| External Links  | Web view opens within Teams and the user might need to authenticate again (depending on the site.)  | Opens a web browser session and the user might need to reauthenticate depending on browser and machine settings. |

## More resources

[Step-by-step guide to setting up Viva Connections](set-up-admin-center.md)

[Learn more about how to plan a dashboard](plan-viva-connections.md#step-1-plan-for-viva-connections)

[Design your own dashboard card with the card designer](use-card-designer.md)

[Available dashboard cards in Viva Connections](available-dashboard-cards.md)
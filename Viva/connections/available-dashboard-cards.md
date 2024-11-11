---
ms.date: 11/06/2024
title: "Available dashboard cards in Viva Connections"
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
description: "Add dynamic cards to the Viva Connections dashboard to help users perform tasks like accessing training materials, shift schedules, assigned tasks, and more."
---

# Available dashboard cards in Viva Connections

The Viva Connections dashboard uses dynamic cards that can be [targeted to specific users](create-dashboard.md#apply-audience-targeting-to-cards) to help them perform tasks like clock in for a shift, access training materials or links to department resources, look up contact information, manage assigned tasks, and more. If your organization has a specific task in mind, you can also use the [card designer](use-card-designer.md) to quickly build "custom" cards using a template, without the need for custom code.

## Edit the dashboard

You need member or owner level permissions to access the card designer from the dashboard card toolbox. See the article on [creating a Viva Connections dashboard and adding cards](create-dashboard.md#edit-the-dashboard-from-microsoft-teams) for information on getting started.

## Available dashboard cards

Select a dashboard icon for more information.

|Toolbox icon   | Description  |
|:-------------:|:--------------|
| [![Screenshot of the card designer icon with a link to an article for more information.](../media/connections/use-card-designer/card-designer-card-icon.png)](use-card-designer.md) | Create your own cards or use quick views for a more interactive experience utilizing the [adaptive cards framework.](/adaptive-cards/templating/)|
| [![Screenshot of the approvals card icon with a link to more information.](../media/connections/approvals-card-icon.png)](#add-the-approvals-card) | Use [Approvals](/power-automate/get-started-approvals) to approve vacation requests, documents, and expense reports. |
| [![Screenshot of the assigned tasks card icon with a link to more information.](../media/connections/assigned-tasks-card-icon.png)](#add-the-assigned-tasks-card) |   Use [Tasks](/microsoftteams/manage-planner-app) to manage your team's work, assign tasks, and track tasks. |
| [![Screenshot of the Assignments card icon with a link to more information.](../media/connections/create-dashboard/assignments-card-icon-no-border.png)](#add-the-assignments-card) | Display a summary of upcoming and past due assignments for students. |
| [![Screenshot of the Courses card icon with a link to more information.](../media/connections/create-dashboard/courses-card-icon-no-border.png)](#add-the-courses-card) | Display a summary of courses a student is enrolled in. |
| [![Screenshot of the Events card icon with a link to more information.](../media/connections/events-card-icon-no-border.png)](#add-the-events-card) |   View and join upcoming events within your organization. |
| [![Screenshots of the News card icon with a link to more information.](../media/connections/news-card-icon-no-border.png)](#add-the-news-card) |   Promote news from various sources that you wish to prominently display, including [boosted news from SharePoint.](https://support.microsoft.com/office/boost-news-from-organization-news-sites-46ad8dc5-8f3b-4d81-853d-8bbbdd0f9c83)     |
| [![Screenshot of the OneDrive card icon with a link to more information.](../media/connections/create-dashboard/onedrive-card-icon-no-border.png)](#add-the-onedrive-card) |   View and access recent, shared, and favorite files from your OneDrive account. |
| [![Screenshot of the People card icon with a link to more information.](../media/connections/people-card-icon-no-border.png)](#add-the-people-card) |   Provide an option to look up contact information and directly chat, email, or call with others in your organization. |
| [![Screenshot of the Quick links card icon with a link to more information.](../media/connections/create-dashboard/quick-links-card-icon-nb.png)](#add-the-quick-links-card) |   Provide list of relevant links or files to users selected by admins. |
| [![Screenshot of the shifts card icon with a link to more information.](../media/connections/shifts-card-icon.png)](#add-the-shifts-card) | Display information about the next or current shift from the Shifts app in Teams. |
| [![Screenshot of the Stream play list card icon with a link to more information.](../media/connections/create-dashboard/stream-playlist-card-icon-nb.png)](#add-the-stream-playlist-card) |   Display a list of videos to users that can be viewed in Microsoft Stream. |
| [![Screenshot of the Teams app icon with a link to more information.](../media/connections/teams-app-icon.png)](#add-the-teams-app-card) |   Use to open a Teams personal app or bot specified by the dashboard author. |
| [Varies](#add-a-partner-card-or-microsoft-app) | Use cards that integrate [partner services.](https://cloudpartners.transform.microsoft.com/resources/viva-app-integration)     |
| [![Screenshot of the Viva Topics Contribute icon and Topics Discover icon with a link to more information](../media/knowledge-management/viva-topics-cards-toolbox.png)](#add-the-viva-topics-card) |  Use Topics cards to encourage knowledge discoverability, engagement, and sharing. |
| [![Screenshot of the Viva Learning card icon with a link to more information.](../media/connections/create-dashboard/viva-learning-card-icon-2.png)](#add-the-viva-learning-card) |  Provide a link to the Viva Learning app that can be targeted to show to certain audiences. |
| [![Screenshot of the Viva Pulse card icon with a link to more information.](../media/connections/create-dashboard/pulse-card-icon-nb.png)](#add-the-viva-pulse-card) | Provide a short status of a recently sent pulse with a link to the Viva Pulse app for users to learn more. |
| [![Screenshot of the web link card icon with a link to more information.](../media/connections/web-link-icon.png)](#add-the-web-link-card) |  Access a site without leaving the Viva Connections app.  |

### Add the Approvals card

The Approvals card connects to [Approvals in Microsoft Teams](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) and is a way to streamline all of your requests and processes with your team or partners. You can create new approvals, view the ones sent your way, and see all of your previous approvals in one place.

![Screenshot of an approvals card.](../media/connections/approvals-card-example.png)

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Approvals** from the dashboard toolbox.

   ![Screenshot showing an approvals card.](../media/connections/approvals-card-1.png)

3. Select the pencil icon to **Edit** the card. In the property pane that opens on the right side of the screen, choose your card size from the **Card size** drop-down list.

   ![Screenshot showing an approvals card in the dashboard.](../media/connections/approvals-edit.png)

4. Once you’re satisfied with how the dashboard looks in preview, select **Publish** or **Republish** at the top-right of your dashboard to make it available for use on your SharePoint home site, in Teams, and in the Teams mobile app.

### Add the Assigned tasks card

The Assigned tasks card allows users to create and view tasks from the card or open the Planner app from the card. Task information is retrieved from the [Planner app](/microsoftteams/manage-planner-app) in Teams.

![Screenshot of an assigned tasks card.](/viva/media/connections/create-dashboard/assigned-tasks-card-demo.png)

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Assigned Tasks** from the dashboard toolbox.

   ![Screenshot showing a tasks card in the dashboard.](/viva/media/connections/create-dashboard/assigned-tasks-card-icon.png)

3. In the property pane on the right, choose your card size from the **Card size** drop-down list.

   > [!NOTE]
   >
   > The size of the card will affect how many buttons are available on the card. The **Add tasks** and **Open Planner** buttons appear on large cards (default size), while on medium sized cards only the **Add tasks** button is shown.

   ![Screenshot showing how to choose a card size.](/viva/media/connections/create-dashboard/assigned-tasks-card-properties.png)

4. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

For more information on using the Planner app, see the articles on how to [Manage the Planner app for your organization in Microsoft Teams](/microsoftteams/manage-planner-app#overview-of-planner) and [Getting started with Planner in Teams](https://support.microsoft.com/office/7a5e58f1-2cee-41b0-a41d-55d512c4a59c), or see the [blog post](https://techcommunity.microsoft.com/t5/planner-blog/create-planner-tasks-from-the-viva-connections-assigned-tasks/ba-p/4206587) announcing the Assigned tasks card.

### Add the Assignments card

The Assignments card displays a summary of upcoming and past due assignments. Students can select the card to view more details on their assignment list and open them in Microsoft Teams.

> [!NOTE]
>
> The Assignments card is only available to Education tenants.

![Screenshot of an Assignments card.](/viva/media/connections/create-dashboard/assignments-card-demo.png)

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Assignments** from the dashboard toolbox.

   ![Screenshot showing the Assignments card in the dashboard toolbox.](/viva/media/connections/create-dashboard/assignments-card-icon-border.png)

3. In the property pane on the right, choose your card size from the **Card size** drop-down list.

4. Enter a **Title** for the assignments card.

5. To change the card image, select **Change**, then select an image or upload your own.

6. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

   ![Screenshot showing the assignments property pane.](/viva/media/connections/create-dashboard/assignments-card-properties.png)

### Add the Courses card

The Courses card displays a summary of courses a student is enrolled in. Students can select the card to view their course list and open them in Microsoft Teams.

> [!NOTE]
>
> The Courses card is only available to Education tenants.

![Screenshot of the Courses card.](/viva/media/connections/create-dashboard/courses-card-demo.png)

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Courses** from the dashboard toolbox.

   ![Screenshot showing the Courses card in the dashboard toolbox.](/viva/media/connections/create-dashboard/courses-card-icon-border.png)

3. In the property pane on the right, choose your card size from the **Card size** drop-down list.

4. Enter a **Title** for the assignments card.

5. To change the card image, select **Change**, then select an image or upload your own.

6. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

   ![Screenshot showing the courses property pane.](/viva/media/connections/create-dashboard/courses-card-properties.png)

### Add the Events card

The events card can help your users stay informed and engaged with upcoming events in their organization, such as webinars, trainings, town halls, and celebrations. Users can view more upcoming events or join via teams via the links on the Events card. The card can be customized and even targeted to specific audiences so only relevant events are displayed.

The Events card is tied to the SharePoint Events web part. Site owners and members need to access their SharePoint site and use the SharePoint Events web part to add events to their site. For more information, see the article on [using the Events web part](https://support.microsoft.com/office/5fe4da93-5fa9-4695-b1ee-b0ae4c981909).

:::image type="content" source="../media/connections/events-card-demo.png" alt-text="Screenshot demonstrating the Events card as it displays upcoming events." lightbox="../media/connections/events-card-demo.png":::

> [!NOTE]
> Recurring events are not supported, even if you manually set up a recurrence in the events list that you are using. You'll need to create a new event for each occurrence.

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Events** from the dashboard toolbox.

   ![Screenshot of the Events card icon.](../media/connections/Events-card-icon-border.png)

3. Select the **edit pencil** to the left of the card to open the properties pane for the Event card.

4. In the property pane on the right, choose your card size from the **Card size** drop-down list.

5. Enter a **Title** for the event card.

   :::image type="content" source="../media/connections/events-card-properties.png" alt-text="Screenshot of the Events card properties pane.":::

6. Under Content, select a **Source** for your events: **Events list on this site**, **This site**, **This site collection**, **Select sites**, or **All sites**. If your site is connected to a hub site, you'll also able to select **All sites in the hub** or **Select sites from the hub**.

   > [!NOTE]
   >
   > - When you choose **Select sites**, you can search for the site you want to add, or select one or more sites from **Frequent sites**, or **Recent sites**. You can select up to 30 sites.
      >   - The **Select sites** option is not available in SharePoint Server, U.S. Government GCC High and DoD, and Office 365 operated by 21Vianet.
   > - If there is more than one **events list** on the site, you can select the one you want. If you don't have an existing list, the **Events** card creates an empty Events list for you, with the default settings of a Calendar list.
   > - If you choose to show events from multiple sites, and don't see all of your events displayed on the page, see [How events from multiple sites are found and displayed](https://support.microsoft.com/office/51891403-0ff7-44ab-b364-a44e86e50573).

7. If your list has **categories**, you can select one by which to filter the events you show.

8. Select a date range by which to filter your events in the **Date range** drop-down list. You can choose **All upcoming events** (the default), **This week**, **Next two weeks**, **This month**, or **This quarter**.

   :::image type="content" source="../media/connections/events-card-content.png" alt-text="Screenshot of the content section in the Events card properties pane.":::

9. Under the layout section, select how many events to be shown at once from the dropdown. Up to 30 events can be shown on one event card.

   :::image type="content" source="../media/connections/events-card-layout.png" alt-text="Screenshot of the layout section in the Events card properties pane.":::

10. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), **enable audience targeting**. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

    :::image type="content" source="../media/connections/events-card-audience-targeting.png" alt-text="Screenshot of the audience targeting section in the Events card properties pane.":::

11. When finished with your selection, you can close the panel. Your settings will autosave.

### Add the News card

Add the News card to the Viva Connections Dashboard to promote news from various sources that you wish to prominently display, [including boosted news from SharePoint](https://support.microsoft.com/office/boost-news-from-organization-news-sites-46ad8dc5-8f3b-4d81-853d-8bbbdd0f9c83). If you choose a boosted news post, they'll display in the News card during the boost period.

![Screenshot of a News card.](../media/connections/top-news-card-example.png)

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **News** from the dashboard toolbox.

    ![Screenshot of the News card icon.](../media/connections/news-card-icon-border.png)

3. Select the **edit pencil** to the left of the card to open the properties pane for the News card.

4. Add a title and select a card size.

5. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information, see the section on [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

6. For a news source, select one of the following options:

   - **Boosted posts**: Displays any SharePoint boosted news posts from the organization's news sites only. The word "Boosted" displays at the top of the card.  

   - **From this site**: Pulls news from the hub site that the current site is a part of.

   - **From all sites in this hub**: Pulls news from all sites within your SharePoint hub.

   - **Select sites**: Pulls news from one or more individual sites (if selected, a list of sites associated with your SharePoint hub displays).

   - **Recommended for current user**: Displays news posts for the current user from people the user works with; managers in the chain of people the user works with, mapped against the user's own chain of management and connections; the user's top 20 followed sites; and the user's frequently visited sites.

   :::image type="content" source="../media/connections/news-card-properties.png" alt-text="Screenshot showing the News card properties pane.":::

### Add the OneDrive card

The OneDrive card (previously known as Files) connects individuals to their own recent, shared, or favorite files in their OneDrive account. Users can review files they have access to from their Connections experience and open them from the OneDrive card.

> [!NOTE]
>
> Office files like Word, PowerPoint, and Excel will be opened in their respective Teams app. All other file types will be opened in their respective web or local app.

:::image type="content" source="../media/connections/create-dashboard/onedrive-card-demo.png" alt-text="Screenshot demonstrating the OneDrive card displaying recently accessed files." lightbox="../media/connections/create-dashboard/onedrive-card-demo.png":::

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **OneDrive** from the dashboard toolbox.

    :::image type="content" source="../media/connections/create-dashboard/onedrive-card-icon-border.png" alt-text="Screenshot of the OneDrive card icon.":::

3. Select the **edit pencil** to the left of the card to open the properties pane for the OneDrive card.

4. In the property pane on the right, enter a **Title** for the OneDrive card.

5. Choose your card size from the **Card size** drop-down list.

    :::image type="content" source="../media/connections/create-dashboard/onedrive-card-card-size.png" alt-text="Screenshot showing card size options in the OneDrive card properties panel.":::

6. Select a **Source** for files to be displayed from:
    - **Recent**: Recent files the user accessed display.
    - **Shared**: Files that shared with the user display.
    - **Favorites**: Files that the user marked as "favorite" display.

7. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), enter one or more Microsoft 365 groups into the **Audience targeting** field. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

    :::image type="content" source="../media/connections/create-dashboard/onedrive-card-source-audience-targeting.png" alt-text="Screenshot showing file source and audience targeting options in the OneDrive card properties panel.":::

### Add the People card

The People Search card automatically retrieves contact information from members of your organization using [Microsoft Entra ID](/entra/fundamentals/new-name). Users can access the People Search card to look up contact information and can jump into chat, email, or a call with the contact directly from the card view.

:::image type="content" source="../media/connections/people-card-demo.png" alt-text="Screenshot demonstrating the People card in action looking up contact information." lightbox="../media/connections/people-card-demo.png":::

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **People** from the dashboard toolbox.

   ![Screenshot of the People card icon.](../media/connections/people-card-icon-border.png)

3. Select the **edit pencil** to the left of the card to open the properties pane for the People card.

4. In the property pane on the right, choose your card size from the **Card size** drop-down list.

5. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

   :::image type="content" source="../media/connections/people-card-properties.png" alt-text="Screenshot of the People card properties pane.":::

### Add the Quick links card

Use the Quick links card to provide a list of relevant links or files selected by admins to users. Users can select the link to be taken to the respective web page or file.

:::image type="content" source="../media/connections/create-dashboard/quick-links-demo.png" alt-text="Screenshot of the Quick links card in action.":::

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Quick links** from the dashboard toolbox.

    :::image type="content" source="../media/connections/create-dashboard/quick-links-card-icon.png" alt-text="Screenshot of the Quick links card icon.":::

3. Select the **edit pencil** to the left of the card to open the properties pane for the Quick links card.

4. In the property pane on the right, enter the **title** for the Quick links card.

5. To change the card image, select **Change**, then select an image or upload your own.

6. Select a **card size** for the Quick links card.

    :::image type="content" source="../media/connections/create-dashboard/quick-links-properties.png" alt-text="Screenshot of the Quick links properties pane showing card customization options.":::

7. Under links, select **+ Add link** to add a URL, SharePoint page, or files. Added links show below the **+ Add link** button. You can add up to 20 links.

8. Once added, links can be edited in the following ways:

    - **Rearrange** – Select and drag to the left of the link to reposition it within your quick link list.
    - **Delete** – Select the trashcan to delete the selected link.
    - **Edit** – Select the arrow to edit the link URL, title, and thumbnail image.

9. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

   :::image type="content" source="../media/connections/create-dashboard/quick-links-properties-links-at.png" alt-text="Screenshot of the Quick links properties pane showing where you can manage links and audience targeting.":::

### Add the Shifts card

The Shifts card shows users information about their next or current shift from the Shifts app in Teams. They can also clock in and out and track break time when Time clock is enabled in Teams.

![Screenshot of a shifts card.](../media/connections/shifts-card-example.png)

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Shifts** from the dashboard toolbox.

   ![Screenshot showing a Shifts app card.](../media/connections/shiftsicon.png)

3. In the property pane on the right, choose your card size from the **Card size** drop-down list.

4. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

### Add the Stream playlist card

The Stream playlist card displays a list of videos to users that can be viewed in Microsoft Stream by selecting an existing playlist from a SharePoint site. For more information, see the article on [creating a playlist from SharePoint](/stream/streamnew/stream-playlists-new-creation#create-a-playlist-from-sharepoint).

> [!NOTE]
>
> The Stream playlist card is currently rolling out and will be fully available by early September 2024.

:::image type="content" source="../media/connections/create-dashboard/stream-playlist-demo.png" alt-text="Screenshot showing the Stream playlist card in action.":::

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Stream playlist** from the dashboard toolbox.

    ![Screenshot of the Stream playlist icon.](../media/connections/create-dashboard/stream-playlist-card-icon.png)

3. Select the **edit pencil** to the left of the card to open the properties pane for the Play list card.

4. In the property pane on the right, choose your card size from the **Card size** drop-down list.

5. Under source, select a **SharePoint site** that has the playlist you wish to display. You can search for a SharePoint site by its title, URL, or select from a list of frequented sites.

   :::image type="content" source="../media/connections/create-dashboard/stream-playlist-properties-1.png" alt-text="Screenshot of the Stream playlist properties pane showing options for selecting a source from SharePoint":::

6. Under playlist, select the **playlist** from the drop-down of available playlists found from your selected source.

7. Enter a **Title** and **Description** for the selected playlist.

8. Under sort, select one of the following options:
    - **Playlist Order**: Videos play in the order set within the selected SharePoint playlist.
    - **Last Created**: Videos play in order based on the date they were last created.
    - **Last Updated**: Videos play in order based on the date they were last updated.

9. Under Image, select **Auto-selected** or **Custom image**:
    - **Auto-selected**: Displays an image for your playlist that comes from your selected SharePoint page.
    - **Custom image**: Select custom image then Change to upload your own image or select an existing image from your site or from an online source (for example, web search, OneDrive, Site).

10. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

    :::image type="content" source="../media/connections/create-dashboard/stream-playlist-properties-2.png" alt-text="Screenshot of the Stream playlist properties pane showing playlist customization options.":::

### Add the Teams app card

A Teams app card allows you to create a card for an existing Teams app.

![Screenshot of a teams app card.](../media/connections/teams-app-card-example.png)

1. While in **edit** mode, select **+ Add a card** from the dashboard.

2. Select **Teams app** from the web toolbox.

   :::image type="content" alt-text="Screenshot that shows the icon to select to add a Teams app card." source="../media/connections/teams-app-icon.png":::

3. In the **property** pane on the right side of the page, select your options.

   ![Teams app property pane.](../media/connections/teamsapp.png)

4. Select a size for the card from the **Card size** drop-down list.

5. Search for the Teams app you want to use, and then select it from the list.
6. Set the card-display options:

   - Enter a title for the card in the **Card title** text box. (This title won't change your page title; it's the title that is displayed on the top of the card.)
   - Enter a description for the card in the **Card description** text box. This description is displayed in larger text under the title.

7. If you want to target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

### Add a partner card or Microsoft app

The Viva Connections dashboard and mobile experience can be extended and customized using cards, which are based on [adaptive cards](https://adaptivecards.io/) and the [SharePoint Framework (SPFx)](/sharepoint/dev/spfx/sharepoint-framework-overview). These adaptive cards are used to display data, complete tasks, and connect to Teams Apps, Websites, and mobile apps on Viva Connections. They provide a low-code solution to bring your line-of-business apps into the dashboard.

To create custom experiences on Viva Connections dashboard and Viva Connections Mobile App, developers must use the SPFx to create custom Adaptive Card Extensions (ACE). To learn more about creating ACE, see the following tutorial: [Build your first SharePoint Adaptive Card Extension](/sharepoint/dev/spfx/viva/get-started/build-first-sharepoint-adaptive-card-extension). Learn more about [Viva Connections extensibility.](/sharepoint/dev/spfx/viva/overview-viva-connections)

#### Add a partner card

There are three ways to get partner apps and solutions integrated with the Viva Connections dashboard. The following image shows an example of a partner card.

![Screenshot of a partner card.](../media/connections/partner-card-example.png)

##### Option 1: Discover and request apps from the Viva Connections card toolbox

Partner cards and an entry point to browse more cards in the app store will automatically display in the card toolbox. Depending on your level of permissions, you might need to request the app before it can be used on the dashboard. [Learn more about managing partner apps](/sharepoint/use-app-catalog).

> [!NOTE]
>
> - Site owners managing the Viva Connections dashboard will need to request partner apps before they are available in the card toolbox.
> - Some partner apps require a service plan agreement with your organization.

:::image type="content" alt-text="This screenshot is of the card toolbox section that displays partner cards." source="../media/connections/partner-card-toolbox.png":::

1. While in edit-mode, select **+ Add card** from the dashboard.
2. Partner options appear in the **Suggested cards** section. Select one of the cards displayed or browse more cards by selecting **Add more cards**.
3. Request the cards you’d like to add to the toolbox and the requests will be sent to the App Catalog Admin for their approval.
4. You'll receive an email to confirm if your request has been approved or denied by the App Catalog Admin.
5. Once your request has been approved, refresh the page to see the new card display in the toolbox.

##### Option 2: Acquire the app from a Microsoft AppSource or the SharePoint store

- If you're building a dashboard, you can [request the app directly](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/explore-and-deploy-sharepoint-framework-solutions-from-partners/ba-p/2645289), but you need approval from an admin of the tenant-level app catalog to continue with the installation
- If you're an **admin** of a tenant-level app catalog, you can deploy business apps directly.
You can acquire apps from non-Microsoft developers by browsing the [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=sharepoint) or [SharePoint store](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/explore-and-deploy-sharepoint-framework-solutions-from-partners/ba-p/2645289) (recommended).

[Get step-by-step guidance](https://techcommunity.microsoft.com/t5/microsoft-sharepoint-blog/explore-and-deploy-sharepoint-framework-solutions-from-partners/ba-p/2645289) on how to request and deploy an app, and add an app to your site. For tenant admin, [learn how to manage apps](/sharepoint/use-app-catalog#work-with-sharepoint-store-apps) in the App Catalog.

##### Option 3: Acquire the app directly from the partner developer

 > [!NOTE]
 > SharePoint administrative permissions are required to complete this task.

You can request apps directly from the Viva Connections partner developers and partners. Admin permissions are required to [add the app to tenant level app catalog.](/sharepoint/use-app-catalog)

#### Add a Microsoft app as a card on the dashboard

A Microsoft app card allows you to create a card that links to Microsoft apps (For example: Shifts, Approvals, Task, etc.). Microsoft apps cards are available out of the box when Viva Connections is enabled.

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select the Microsoft App you want to add from the web toolbox.

   ![Screenshot of how to find a Microsoft app in the card picker window.](../media/connections/3p-apps-1.png)

3. Select your options in the property pane on the right side of the page.

4. When you **Republish**, the card appears on your dashboard.

### Add the Viva Topics card

Topics has two different cards. The **Topics Contribute card** can be used to reach people who are known knowledge managers and are already engaged with topics and knowledge areas. Topics and knowledge areas are dynamically displayed in the card based on the viewers interests, current projects, and expertise. The **Topics Discover card** can be used to view topics and knowledge areas for people who could be interested in learning more or contributing to a topic.

[Learn more about the two different cards](/microsoft-365/topics/topics-card-viva-connections).

![Screenshot Topics Contribute card.](../media/knowledge-management/viva-topics-contribute-card.png)

### Add the Viva Learning card

The [Viva Learning](/viva/learning/overview-viva-learning) card provides users quick-links to recommended trainings, and can be set to target specific trainings to certain individuals. Users can easily access their required trainings by selecting the Viva Learning link.

Content in the cards is dynamic and changes according to settings in Viva Learning. The following are three examples of Viva Learning card states that display different information depending on the viewer and Viva Learning settings.

![Screenshot of the Viva Learning card displaying general learning opportunities.](../media/connections/create-dashboard/viva-learning-card-1.png)  ![Screenshot of the Viva Learning card notifying the user of a required training due.](../media/connections/create-dashboard/viva-learning-card-2.png)  ![Screenshot of the Viva Learning card notifying user of upcoming required trainings.](../media/connections/create-dashboard/viva-learning-card-3.png)  

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Viva Learning** from the dashboard toolbox.

   ![Screenshot of the Viva Learning card icon in the dashboard toolbox.](../media/connections/create-dashboard/viva-learning-card-icon.png)

3. In the property pane on the right, choose your card size from the **Card size** drop-down list.

   ![Screenshot of the Viva Learning property pane.](../media/connections/create-dashboard/viva-learning-card-settings.png)

4. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

### Add the Viva Pulse card

Invite managers and team leads to send requests for feedback or view feedback results using the [Viva Pulse](/viva/pulse/introduction-to-viva-pulse) card. The card provides a way for feedback authors to access and interact with active or recently closed feedback pulses. This provides feedback authors and feedback providers with a direct link to their account in the Viva Pulse Teams app.

> [!NOTE]
>
> - It’s recommended admins set up the Viva Pulse app for their organization and pin it as an app in Microsoft Teams so users can fully experience the Viva Pulse card. For more information, see the article on [manage, install, and pin Viva Pulse in the Teams admin center](/viva/pulse/setup-admin-access/manage-install-pin-viva-pulse-in-teams-admin-center).
> - Users will only see the Viva Pulse card if their organization is licensed for Viva Pulse.

Content in the card is dynamic and changes according to the [users role](/viva/pulse/introduction-to-viva-pulse#roles) in Viva Pulse and if a feedback pulse is active. The following are examples of Viva Pulse card states that display different information depending on the viewer’s role and if any active or recently closed feedback pulses are available.

The Pulse card tells feedback authors the number of responses an active or recently closed pulse received and provides a link to feedback results in their Viva Pulse account for the recently closed pulse. When multiple feedback results are available, authors are directed to their **Pulses sent** tab within the Viva Pulse Teams app.

   :::image type="content" source="../media/connections/create-dashboard/pulse-card-author-closed-state.png" alt-text="Screenshot showing two states of the Viva Pulse card.":::

When no open pulses are available, the card displays **send a pulse**, which brings the author to the Viva Pulse Teams app where they can create a new request for feedback to be sent out.

   :::image type="content" source="../media/connections/create-dashboard/pulse-card-author-send-pulse.png" alt-text="Screenshot showing the send a pulse state of the Viva Pulse card.":::

> [!NOTE]
>
> - Viva Pulse requires a license to send pulse requests for feedback and to review results. A license is **not required** to respond to a pulse. For more information on Viva Pulse licensing, see the article on [Licensing requirements](/viva/pulse/get-started/licensing-requirements).
> - The Viva Pulse card requires the Viva Pulse app to be enabled in Microsoft Teams for the card to display information

To add the Viva Pulse card to your dashboard:

1. While in edit mode, select **+ Add a card** from the dashboard.

2. Select **Viva Pulse** from the dashboard toolbox.

      :::image type="content" source="../media/connections/create-dashboard/pulse-card-icon.png" alt-text="Screenshot of the Viva Pulse card icon.":::

3. In the property pane on the right, choose your card size from the **Card size** drop-down list.

4. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

      :::image type="content" source="../media/connections/create-dashboard/pulse-card-properties.png" alt-text="Screenshot of the Viva Pulse card properties.":::

For more information on using Viva Pulse as a feedback author or feedback recipient, see [the Viva Pulse documentation here](https://support.microsoft.com/topic/34c94efe-185d-480e-94a2-27e013a5204b).

### Add the Web link card

Add a web link card when you want your users to go to an internal or external link on a web site.

![Screenshot of a web link card.](../media/connections/link-card-example.png)

1. While in **edit** mode, select **+ Add a card** from the dashboard.

2. Select **Web link** from the web toolbox.

   :::image type="content" alt-text="This screenshot shows the icon to select to add a web link card." source="../media/connections/web-link-icon.png":::

3. In the property pane on the right side of the page, select your options.

   ![Screenshot showing how to choose options.](../media/connections/choosing-options.png)

4. Select a size for the card from the **Card size** drop-down list.
5. Enter the URL for your link in the **Link** text box.
6. Set the card-display options:

   - Enter a title for the card in the **Card title** text box. (This title won't change your page title; it's the title that is displayed on the top of the card.)
   - Enter a description for the card in the **Card description** text box. This description is displayed in larger text under the title.

7. Under **Thumbnail**, select one of the following options:

   - **Auto-selected**: This option when chosen automatically displays an image at the top of your card that comes from your page.
   - **Custom image**: This option when chosen enables the **Change** button. You can select this button to choose an image you want to use.

8. Under **Card icon**, select one of the following options that enable the icon to be displayed on the left side of the card title:

   - **Auto-selected**: This option when chosen automatically displays a built-in icon associated with the page.
   - **Custom image**: This option when chosen enables the **Change** button. You can select this button to choose an image you want to use.
   - **Icon**: This option when chosen enables the **Change** button. You can select this button to choose from a set of stock icons.

9. To target your card to specific audiences (that is, the card only displays in the dashboard to the audience you specify), select one or more groups to target. For more information on audience targeting, see [Audience targeting](create-dashboard.md#apply-audience-targeting-to-cards).

## More Resources

[Create a Viva Connections dashboard and add cards](create-dashboard.md)

[Design your own dashboard card with the card designer](use-card-designer.md)

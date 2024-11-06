---
ms.date: 11/06/2024
title: "Design your own dashboard card with the card designer"
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
description: "Use the Card Designer to quickly build custom interactive cards that can link to sites, open media and apps, and more without the need for custom code."
---

# Design your own dashboard card with the card designer

Use the Card Designer to create cards that can link to other sites, open media, display a location, open a teams app, and more. Card designer gives users the ability to quickly build "custom" cards without the need for custom code by using a template with the option to create a secondary view, also called a quick view.

Quick view is a powerful tool that enables the card designer to create cards that go beyond the traditional dashboard cards to create something interactive and informative using [Adaptive Card](https://adaptivecards.io/) JavaScript Object Notation (JSON). You're able to "code" a single quick view by using the power of Adaptive Card markup to make their cards dynamic. The result can be previewed within the card designer before sharing with others.

> [!NOTE]
>
> To design your own cards using quick view, you should be familiar with JSON and Adaptive Card templates. For more information, see [Adaptive Cards Templating](/adaptive-cards/templating/).

:::image type="content" source="../media/connections/use-card-designer/card-designer-card-example.png" alt-text="Screenshot showing an example of a large card created with the card designer for celebrating birthdays with a button to congratulate displayed." lightbox="../media/connections/use-card-designer/card-designer-card-example.png":::

## Edit the dashboard

You need member or owner level permissions to access the card designer from the dashboard card toolbox. See the article on [creating a Viva Connections dashboard and adding cards](create-dashboard.md#edit-the-dashboard-from-microsoft-teams) for information on getting started.

## Use a card template

The card designer has a set of card view templates that can be used to easily create cards with helpful information, links, and media. The following steps walk you through creating a new large sized card using the image template to create a link for users.

1. While in **edit** mode, select **+ Add a card** from the dashboard.

2. Select **Card designer**.

   :::image type="content" alt-text="Screenshot that shows the icon to select to add a Card designer card." source="../media/connections/use-card-designer/card-designer-card-icon.png":::

3. After selecting the Card designer card, select the **Edit** icon to open the property pane.

4. As you create your card through selecting options, a preview of how the card looks appears to the left of the options.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-properties-overview.png" alt-text="Screenshot showing an overview of the card designer properties pane." lightbox="../media/connections/use-card-designer/card-designer-properties-overview.png":::

5. Under **Template type**, select one of three **templates** to apply:
   - **Heading**: Create a card with a simple heading.
   - **Image**: Create a card with a heading and image.
   - **Description**: Create a card with a heading and description.

   > [!NOTE]
   >
   > Buttons are disabled when selecting the Image template for a medium sized card, but a card action can still be assigned to trigger when the user selects the card.

   Depending on the template type chosen, fields matching the template type populates in the **card content** section. For example, if you chose the Image template, you can enter values for the Image and Heading properties in their respective text boxes.

6. Select a **card size**:

   - **Medium**: the default card size and allows you to add one button to the Heading and Description templates.
   - **Large**: takes the space of two medium cards together and allows the use of two buttons.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-layout-and-size.png" alt-text="Screenshot showing options under the layout and size category in the properties pane.":::

7. Under **Card icon** select one of the following options:

   - **Custom image**: Select **custom image** then **Change** to upload your own image or select an existing image from your site or from an online source (for example, web search, OneDrive, Site).
   - **Library**: Select an icon from a pre-existing list of available icons.
   For example, select **Library** then **Change** to choose a new icon.

   > [!NOTE]
   >
   > When uploading custom images for your icons, we recommend using PNG images between 24x24 and 32x32 pixels.

8. Enter a **Title** to be displayed at the top of your card.

9. Enter a **Heading**.

10. Depending on the template type chosen, enter values for the properties corresponding to your selection below the heading field. For this example, the image template is being shown:

    - **Image**: Select **change** to upload your own image or select an existing image from your site or from an online source (for example, web search, OneDrive, Site).

      :::image type="content" source="../media/connections/use-card-designer/card-designer-adding-image.png" alt-text="Screenshot showing options under the card content category in the properties pane.":::

> [!NOTE]
>
> - Image recommendations for cards in the dashboard: medium cards should be 300x150 to 400x200 with 2:1 aspect ratio and large cards 300x300 to 400x400 with 1:1 aspect ratio to prevent stretching in the mobile app.
> - Image URLS in card properties must be an absolute URL for the link to work in the mobile app.

11. Under card action, select an action to be performed when a user selects the card. Depending on the action selected, more fields appear to customize the action.

> [!NOTE]
>
> The card action cannot be disabled.

- **Show the quick view**: Select to use JSON code to create a more interactive dashboard card. If selected, the **Save** button changes to **Next**, which leads to more settings for customizing your quick view card. One quick view is available for each card, which can be opened as the card action, or by using a button. For steps on using quick view, refer to [add a quick view to a card](#add-a-quick-view-to-a-card).
- **Go to a link**: Enter a URL to direct users to.
- **Go to teams app**: the user is directed to the specified teams app by the URL provided (admins can also use the appID to direct users to the appropriate Teams app). For more information, see [Deep link to an application](/microsoftteams/platform/concepts/build-and-test/deep-link-application?tabs=teamsjs-v2#configure-deep-link-manually-using-your-app-id).

    For example, selecting **Go to a link** from the dropdown displays a field for entering the link.

12. Under **Link**, enter the **URL** you wish users to be directed to.

13. Buttons can be toggled on and off (where available). If enabled, the same values found under card action can be selected for the **Primary** and **Secondary** buttons.

> [!NOTE]
>
> When using a medium sized card, only one button can be enabled using the heading or description template. The image template will disable the use of buttons when medium size is selected.

   For this example, the **Primary button** is set to direct users to the same link as the card action. The **Secondary button** is disabled.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-set-card-actions.png" alt-text="Screenshot showing options under the actions category in the properties pane.":::

14. Under **Audiences to target** enter one or more groups to target so only those audiences specified see the card in the dashboard. For more information, see [audience targeting in Viva Connections](use-audience-targeting-in-viva-connections.md).

    :::image type="content" source="../media/connections/use-card-designer/card-designer-audience-targeting.png" alt-text="Screenshot showing options under the audience targeting category in the properties pane.":::

15. Select **Save** to save the updates to your card.

### Add a quick view to a card

Quick view allows you to add adaptive card JSON code to Dashboard cards to provide a more comprehensive, interactive, and engaging experience to users. By using static or dynamic data sources (like [SharePoint Representational State Transfer (REST) API](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service?tabs=csom#construct-rest-urls-to-access-sharepoint-resources) or [Microsoft Graph API](/graph/call-api)), cards can be created that provide information within the Connections experience, without the user having to navigate away.

To get started, follow the steps in [use a card template](#use-a-card-template) up to selecting a **Card action**.

1. Under **card action** select **Show the quick view**.

2. Finish setting up your card by enabling or disabling buttons and selecting actions for active buttons.

   > [!NOTE]
   >
   > One quick view is available for each card, which can be opened as the card action, or by using a button.

3. Select **Next** to display the quick view layout.

4. A preview of how the card looks on the dashboard displays to the left of the options.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-quickview-layout.png" alt-text="Screenshot selecting show the quick view from a dropdown of options under the actions category in the properties pane." lightbox="../media/connections/use-card-designer/card-designer-quickview-layout.png":::

   > [!NOTE]
   >
   > The [Adaptive Card designer](https://www.adaptivecards.io/designer/) tool can be used to help create the JSON Template and Data code for your card. For more information on the adaptive card structure and creating adaptive cards, see [Getting Started - Adaptive Cards](/adaptive-cards/authoring-cards/getting-started).

5. In the **Template JSON** field, enter your JSON code that contains the structure of your Adaptive Card.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-template-json.png" alt-text="Screenshot showing the quick view options in the properties pane.":::

6. Under **Type of Content**, select one of the following options for your data set:

   - **Static**: displays static information and must be manually updated.
   - **Dynamic**: integrates with data sources from SharePoint API or Microsoft Graph to automatically update content.

   > [!NOTE]
   >
   > Selecting **Dynamic** content will display additional options allowing you to select the data source and API endpoint.

#### Selecting Static as the type of content

1. In the **Data JSON** field, enter your JSON code that contains the data to be displayed within your Adaptive Card.

2. In the **Audiences to target** field, enter any audiences you wish to target the card to.

3. Select **Save** to your updates.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-static-content-preview.png" alt-text="Screenshot showing static content selected with the Data JSON field displayed in the properties pane and a preview of the finished card." lightbox="../media/connections/use-card-designer/card-designer-static-content-preview.png":::

#### Selecting Dynamic as the type of content with SharePoint as the data source

1. From the **Data Source** dropdown, select **SharePoint API**.

2. In the **API endpoint**, enter the REST URL endpoint you wish to use.

   For example, if you wanted to retrieve the title of a SharePoint site, you would enter `title` in the **API Endpoint** field (since `web/` is already part of the default prefix). See this article for more [examples of SharePoint REST endpoints](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service?tabs=csom#sharepoint-rest-endpoint-examples).

3. The **Data JSON response preview** will open and display the code used. A preview of how the card looks on the dashboard appears to the left of the property pane.

4. In the Audiences to target field, enter any audiences you wish to target the card to.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-dynamic-sharepoint-api.png" alt-text="Screenshot showing dynamic content selected with SharePoint API as the endpoint and the Data JSON field displayed in the properties pane." lightbox="../media/connections/use-card-designer/card-designer-dynamic-sharepoint-api.png":::

5. Select **Save** to save your updates to your custom card.

#### Selecting Dynamic as the type of content with Microsoft Graph as the data source

1. From the **Data Source** dropdown, select **Microsoft Graph**.

2. Select the **Graph version** from the dropdown (where version is the target service version, usually 1.0).

3. In the **API endpoint**, enter the REST URL endpoint you wish to use.

   For example, if you wanted to retrieve the profile and photo of a specific user, you would enter the Microsoft Graph REST URL `me/photo/$value` in the **API Endpoint** field. See more [common use cases in 1.0 for Microsoft Graph REST API](/graph/api/overview?view=graph-rest-1.0&source=recommendations#common-use-cases&preserve-view=true) here.

4. The **Data JSON response preview** will open and display the code used and a preview of how the card looks on the dashboard appears to the left of the property pane.

5. In the **Audiences to target** field, enter any audiences you wish to target the card to.

   :::image type="content" source="../media/connections/use-card-designer/card-designer-dynamic-graph-api.png" alt-text="Screenshot showing dynamic content selected with Microsoft Graph API as the endpoint and the Data JSON field displayed in the properties pane." lightbox="../media/connections/use-card-designer/card-designer-dynamic-graph-api.png":::

6. Select **Save** to save updates to your custom card.

## More Resources

[Create a Viva Connections dashboard and add cards](create-dashboard.md)

[Available dashboard cards](available-dashboard-cards.md)
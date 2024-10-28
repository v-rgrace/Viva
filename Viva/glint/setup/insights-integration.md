---
title: Send Viva Glint survey results to Viva Insights 
description: Connect sentiments about how people work with sentiments about how people feel by sending Viva Glint survey feedback to Viva Insights Power BI.
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
ms.date: 11/15/2024
---

# Send Viva Glint survey results to Viva Insights 

HR analysts and other leaders in your organization can bring Microsoft Viva Glint survey scores into Microsoft Viva Insights to learn how people feel–Glint-along with how people work - Insights.  This integration gives your organization a complete picture of the employee's experience.

*Applies to: Viva Glint administrator, Viva Insights administrator* 

This article discusses how to import survey results – employee-level survey responses, question/item text, question/item labels, categories, survey names, rating scales, and survey closed date – from Glint into Insights. 

## Workflow 

1. The Viva Insights admin sets up a new import in the advanced insights app. 
1. The Viva Insights admin contacts the Viva Glint admin to share Viva Glint survey data. The Viva Glint admin selects specific survey programs and sends the data to Viva Insights.
1. Viva Insights validates and processes the data so it’s ready for use. 

## What data can be sent to Viva Insights?

>[!IMPORTANT]
>By sending data to Viva Insights, you agree to have Microsoft Viva Glint data sent and stored within [Microsoft Viva Insights](/../viva/insights/introduction).

This consent screen displays when you begin this integration. **Agree to terms** before moving forward by selecting **Get Started.**

:::image type="content" source="../../media/glint/setup/insights-new-authorization.png" alt-text="Screenshot of the authorization agreement." lightbox="../../media/glint/setup/insights-new-authorization.png":::

**Data that can be sent:**

- Data from recurring or ad-hoc surveys with [confidentiality thresholds](/viva/glint/setup/manage-confidentiality-thresholds) is equal to or above the Viva Glint default of five respondents.
- Rating item scores, but no comments.
- All Viva Glint languages supported for question/item labels (names) and question/item text are sent to Viva Insights Power BI.

## 1 - Set up the Viva Insights integration from your admin dashboard

*This guidance is for the Viva Glint admin.*

The Viva Insights admin sets up the import and contacts you to verify that you can now share Glint survey data. The Viva Glint admin follows this procedure:

1. From the Glint admin dashboard, select **Configure** and then **Viva Insights** from the **Microsoft Viva Integrations** section.

   :::image type="content" source="../../media/glint/setup/insights-dashboard-card.png" alt-text="Screenshot of where to access the Viva Insights integration feature from the admin dashboard.":::

2. Use the **Learn More** button for more information about the integration.

3. Select **Set up integration** from the **Send Data to Viva Insights** section.

   :::image type="content" source="../../media/glint/setup/send-glint-data-to-insights.png" alt-text="Screenshot of the Set up integration button." lightbox="../../media/glint/setup/send-glint-data-to-insights.png":::
   
### Sync with Entra ID

If you find discrepancies between Glint active users and their Entra IDs in MAC, remedy the discrepancies by following [Prerequisites to the integration](/viva/solutions/glint-insights-integration-overview#prerequisites-to-the-integration) on the integration overview page. 

To resync the data to pick up the Entra ID changes: 
 - To resend Glint data to Insights, remove and then re-add the survey programs. 

In the future, this resync occurs automatically. 

## 2 - Send and manage data

*This guidance is for the initial sending of data to Insights only.*

1. On the **Send Data to Viva Insights** page, **Select Programs** by enabling the checkbox next to the recurring or ad hoc program listed. You can choose more than one program.

   :::image type="content" source="../../media/glint/setup/send-to-insights.png" alt-text="Screenshot of the Send data to Viva Insights button." lightbox="../../media/glint/setup/send-to-insights.png":::

2. Select **Send data to Viva Insights.** You see this confirmation:

   :::image type="content" source="../../media/glint/setup/glintsights-confirm-v2.png" alt-text="Screenshot of confirmation message that your data is sent to Viva Insights.":::

3. Select **Close.**

## Send more survey programs to Viva Insights

1. In the **Send Data to Viva Insights** section, after your first data send, the button displays **Manage Integration**. Use this button to send more programs to Insights.

   :::image type="content" source="../../media/glint/setup/manage-integration-button.png" alt-text="Screenshot of Manage Integration dialog box and button.":::

2. Select **+ Add Programs.**

3. In the **Add Program** window, select **Add** next to any program. You can select multiple programs.

4. A confirmation message displays. 

5. Be sure that the name of the program you added now shows under **Programs** on the **Send data to Viva Insights** page.
   
   > [!IMPORTANT]
   > Selecting a program sends data for every closed program cycle and automatically sends data for future cycles. In Viva Insights, map which program data to display on the Viva Insights dashboard.

## 2 - Data validation and processing

*Applies to Viva Glint admin and Viva Insights admin*

After the Glint admin sends data, the Insights app validates it and provides status messages about the import. [Learn about the validation process, what status messages mean, and how to manage data errors.](/viva/insights/advanced/admin/import-survey-glint#3-data-validation-and-processing), 

If processing fails, try running the import again, and resending your survey data. If you’re still getting a failed status, [file a support ticket](/../../microsoft-365/admin/get-help-support).

## Glint data deletions result in Insights data deletion

As your company’s data controller, Microsoft Viva Glint admins can submit a user data deletion request to comply with a General Data Protection Regulation (GDPR) data subject request. 

User data is deleted from the **People** feature on the Viva Glint admin dashboard. Any data deleted from Glint is deleted from Insights, as well. [Find data deletion instructions here.](/viva/glint/setup/delete-user-data).

## Remove a program after initial setup

After sending data to Viva Insights, you can continue to manage your integration. Stop sharing future data with Viva Insights by removing the program. 

1. Return to your Viva Glint admin dashboard and follow the initial setup instructions. The Setup integration button now reads **Manage integration**.

1. Select **Manage Integration**.

1. Hover over the ellipses next to the program to reveal the actions available. Select **Remove program.**

   :::image type="content" source="../../media/glint/setup/send-data.png" alt-text="Screenshot of how to remove programs." lightbox="../../media/glint/setup/send-data.png":::

[**Connect to Viva Insights using the Power BI Connector**](/../viva/insights/advanced/analyst/power-bi-connector)

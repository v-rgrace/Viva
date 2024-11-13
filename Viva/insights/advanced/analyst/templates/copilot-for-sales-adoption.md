---
ms.date: 11/07/2024
title: Copilot for Sales adoption report
description: Learn how to use the Copilot for Sales adoption Power BI template to understand how your company's sales team is using Copilot for Sales.
author: zachminers
ms.author: v-zachminers
ms.topic: article
ms.localizationpriority: medium 
ms.collection:
- viva-insights-advanced
- viva-copilot
- magic-ai-copilot 
ms.service: viva-insights
search.appverid: 
- MET150 
manager: anirudhbajaj
audience: Admin
---

# Copilot for Sales adoption report

The **Copilot for Sales adoption** report helps leaders understand Copilot for Sales usage across their organization. The insights can help you accelerate Copilot for Sales adoption, and help members of your sales team transform their work with Copilot for Sales.

This report has five sections. These sections help you answer the following business questions: 

* How does Copilot for Sales usage compare across groups? How does it compare across apps? 

* Which Copilot for Sales actions are contributing to key sales tasks? 

Lastly, the **Learn more** section provides an overview of research articles and case studies about the adoption of Copilot for Sales. 

To populate the report in Power BI, you’ll need to set up and successfully run the predefined **Copilot for Sales adoption** query in Viva Insights.

## Prerequisites

Before you can run the query and populate the report in Power BI, you’ll need to: 

* Be assigned the role of **Insights Analyst** in Viva Insights. [Learn more about how to assign roles](../../../advanced/setup-maint/assign-user-roles.md). 

* Have the June 2022 (or newer) version of Power BI Desktop installed. If you have an earlier version of Power BI installed, uninstall it before installing the new version. Then go to [Get Power BI Desktop](https://www.microsoft.com/power-platform/products/power-bi/getting-started-with-power-bi) to download and install the latest version. 

* Make sure the employees you would like to include as part of the measured population have the Copilot for Sales app installed.

## Report setup

### Run query

1. In the [Viva Insights analyst experience](https://analysis.insights.viva.office.com/), select **Create analysis**.
2. Under **Templates**, navigate to **Copilot for Sales adoption** and select **Set up analysis**. The template can also be found underneath the **Copilot** section.
3. Under **Query setup**:
    
    1. Type a **Query name**.
    1. Select a **Time period**. **Time period** defaults to **Last 6 months**.
    1. Set **Auto-refresh** (optional). You can set the query to automatically update by checking the **Auto-refresh** box. When you select the **Auto-refresh** option, your query automatically runs and computes a new result every time Viva Insights gets updated collaboration data for licensed people.

       > [!NOTE]
       > If organizational data used in an auto-refreshing query changes (for example, an attribute name is altered or an attribute is removed), the query might stop auto-refreshing.

     4. Type a **Description** (optional).   
     5. Change the metric rule (optional). To set a new metric rule, select **More settings**. Then, pick a new rule from the list. [Learn more about metric rules](../../analyst/metric-rules.md).

        > [!NOTE]
        > The **More settings** pane also contains **Group by** settings. Power BI queries are set to **Group by Week**, and you're not able to edit this field.

4. Under **Predefined template metrics**, view a list of preselected metrics, which appear as gray tags. These metrics are required to set up the Power BI report and you can’t remove them. However, you can add other metrics by selecting **Add metrics**.

    > [!IMPORTANT]
    > Low-quality or missing organizational data might affect your metrics and result in warnings or errors. [Learn more about data quality notifications](../../analyst/data-quality-analyst-experience.md).

5. In **Select which employees you want to include in the query**, add filters to narrow down the employees in scope for your report. Don’t remove the predefined “Is Active” filter. [Learn more about filter and metric options](../../analyst/filters.md). If you notice a warning or error here, it's because one of your attributes is missing from your organizational data or it's of low quality.

6. Under **Select which employee attributes you want to include in the query**, add up to 20 organizational attributes. Once the query runs, you can use these attributes to group and filter the reports.

    > [!IMPORTANT]
    > This PowerBI query needs some specific attributes to run, and we've preselected them for you. These attributes appear in gray and you can't remove them. We might also include some attributes that help your template, but aren't required for your query to run. These attributes appear in blue and you can remove them.
    >
    > If you notice attributes marked with yellow warnings, that attribute's quality is low. If you notice attributes marked in red and the query's **Run** button disabled, then your organizational data is missing that attribute.
    >
    > [Learn more about attributes and data quality](../../analyst/data-quality-analyst-experience.md).

7. Select **Run** on the upper right. The query might take a few minutes to run.

### Link report to query

1. Open the downloaded template.

2. If you're prompted to select a program, select **Power BI**.

3. When you're prompted by Power BI:

    1. Paste in the partition and query identifiers. 
    2. Set the **Minimum group size** for data aggregation within this report's visualizations in accordance with your company's policy for viewing Viva Insights data. 
    3. Select **Load** to import the query results into Power BI. 

4. If prompted by Power BI, sign in using your organizational account. Power BI then loads and prepares the data. For large files, this process might take a few minutes.

    > [!IMPORTANT]
    > You need to sign in to Power BI with the same account you use to access Viva Insights. If available, select **Organizational account** from the left. You might have to sign in more than once.
    >
    > :::image type="content" source="../../images/analyst-pbi-org-account1.png" alt-text="Screenshot that shows signing into to Power BI on the Organizational account tab":::

## Report settings

### Settings page

View and set the following parameters on the **Settings** page. You can find **Settings** on the right panel of the introduction page. You can also adjust the report settings as you go through the report pages through the **Settings** icon.

* **Time period for the report** – Select the time period for which you want to view data in the report.
* **Group by** – Select the primary group-by attribute shown in all the report pages. You can change this attribute at any time and all report pages will show group values by the new attribute.
* **Apply filters** (optional) – Select the organizational attribute and values you want to use to filter the employees shown in this report.
* **Customize active Copilot for Sales user definition** – Customize the usage frequency for active Copilot users. You can choose between:

  * At least one active day in the selected time period
  * At least one active day per four weeks
  * At least one active day per week 

  A day is marked as active if the user took at least one action with Copilot on that respective day. 

* **Report language** – Change the language for your report.

## About this report

The **Copilot for Sales adoption** report includes the following report pages to help you better understand and accelerate Copilot for Sales adoption across the company. 

**Copilot for Sales adoption summary**

Provides an overview of Copilot for Sales adoption across the company, and get a baseline view of the number of employees actively using Copilot for Sales features and which direction adoption is trending. This page also provides a quick overview of the top-most used Copilot for Sales feature. Lastly, it highlights the organization with the highest Copilot for Sales usage.

**How does Copilot usage compare across groups?**

Gain insight into which groups in your company are leaders in Copilot for Sales adoption. Use this page to: 

* Understand the breakdown of active Copilot for Sales users by group (left-side card) 

* Understand the usage frequency by exploring the average number of Copilot for Sales actions taken per person per week and per month, by group  

Active Copilot for Sales users are defined as users who have used Copilot for Sales at least once in the selected time period. You can update this definition in the Settings menu.

**What Copilot for Sales actions are contributing to key sales tasks?**

Understand how your sales employees are using Copilot for Sales to complete different sales tasks. The cards on this page show the total number of Copilot user actions taken or the unique number of active Copilot for Sales users in each Microsoft 365 app broken out by key sales tasks. The tasks include: 

* Manage customer email interactions 

* Manage sales meetings 

* Update and access CRM in the flow of work

**How does Copilot for Sales usage compare across apps?**

Learn more about how Copilot for Sales usage differs by app across organizations and functions. The table shows the number of active Copilot for Sales users in each Microsoft 365 app broken out by group. Active Copilot for Sales users are defined as users who have used Copilot at least once in the selected time period. You can update the definition in the Settings menu.

**What is the breakdown of Copilot for Sales usage across groups?**

Dive one layer deeper and explore different usage metrics at the same time for different groups in a side-by-side view. Use the metric filter at the top to select the metrics you would like to include and compare in the table. Metrics include "Active Copilot for Sales users," "Monthly active Copilot for Sales users," "Weekly active Copilot for Sales users," "Average number of actions performed," and "measured employees." Metric definitions can be found in the glossary.

**What is the Copilot for Sales usage trend across groups?**

Explore how Copilot for Sales usage has changed over time for different groups in your company. Explore how Copilot usage is changing over time, using the left-side card. The trendline shows the total weekly number of Copilot or Sales user actions or unique active Copilot for Sales users in the filtered groups for the selected time period. The table on the right shows the number of unique active Copilot for Sales users per month and the month-over-month change.

**Learn what our research says about the adoption of Copilot for Sales**

The articles in this section range from practical guides on how to get started with Copilot, to research findings related to the adoption and perceived impact of employees using Copilot for Sales within various Microsoft apps and services.

**Glossary**

View this report's [metric definitions](..//..//reference/metrics.md#copilot-for-sales-metrics).

## Power BI tips, FAQs, and troubleshooting

[Learn more about how to share the report and other Power BI tips, troubleshoot any issues, or review the FAQ](../../analyst/templates/power-bi-faq-troubleshoot.md).

### Related topics

* [Access query results and modify existing queries](../../analyst/query-results.md) 

* [Filters](../../analyst/filters.md)
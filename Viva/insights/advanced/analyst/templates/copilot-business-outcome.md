---
ms.date: 11/15/2024
title: Copilot Business Outcome report
description: Learn how to use the Microsoft 365 Copilot Business Outcome Power BI template to understand how Copilot usage impacts business results at your company.
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

# Copilot Business Outcome report

The **Copilot business outcome** report can help you understand how Microsoft 365 Copilot usage relates to the business outcomes that matter the most to your organization. Relevant business outcome measures are defined and uploaded into Viva Insights by you, and can include a wide range of productivity metrics depending on the function or business unit using the report. For example, “average monthly deals closed” might be a relevant outcome measure for your Sales team.  

 This report has a summary page illustrating how Copilot usage relates to business outcome measures. The report also has three deep dive pages, each helping you answer a different business question:  

* Which Copilot usage behaviors influence specific business outcomes? And what are the groups in my organization with the biggest opportunity to boost Copilot usage?  

* How do the employees who are responsible for favorable business outcomes use Copilot?  

* How can I increase potential Copilot assisted hours and value among employees who are not as active with Copilot?

To populate the report in Power BI, you’ll need to **upload business outcome data** into Viva Insights and set up and successfully run the predefined **Copilot business outcome query**.

## Prerequisites  

Before you can run the query and populate the report in Power BI, you’ll need to:  

* Be assigned the role of **Insights Analyst** in Viva Insights. [Learn more about how to assign roles](..//..//setup-maint/assign-user-roles.md).  

* Have the June 2022 (or newer) version of Power BI Desktop installed. If you have an earlier version of Power BI installed, uninstall it before installing the new version. Then go to [Get Power BI Desktop](https://www.microsoft.com/power-platform/products/power-bi/getting-started-with-power-bi) to download and install the latest version.  

* Make sure you have Business outcome data uploaded in Viva Insights using one of the ingestion options.   

* Make sure the employees you would like to include as part of the measured population have both a Viva Insights license and a Microsoft 365 Copilot license assigned. Also make sure that the measured population has Business outcome data available in Viva Insights.

### Uploading business outcome data in Viva Insights  

There are two ways to upload your business outcome data in the Microsoft Viva Insights’ advanced insights app: through individual .csv files that you as an Insights Administrator upload directly to Viva Insights;  or through an Azure blob import that you, your source system admin, and your Azure contributor set up. Learn more about how to import business data [using Azure](..//..//admin/import-business-data-azure.md), or [using a manual .csv upload](..//..//admin/import-business-data-csv.md).

### What are sample business outcome metrics to consider?  

The [Copilot Scenario Library](https://adoption.microsoft.com/copilot-scenario-library) offers detailed business outcome-focused guidance, use cases, and additional information relevant for each functional area.

## Report setup

### Run query

1. In the [Viva Insights analyst experience](https://analysis.insights.viva.office.com/), select **Create analysis**.

2. Under **Templates**, navigate to **Copilot Business Outcome report** and select **Set up analysis**. The template can also be found under the **Copilot** section.

3. Under **Query setup**:
    
    1. Type a **Query name**.
    1. Select a **Time period**. **Time period** defaults to **Last 3 months**.
    1. Set **Auto-refresh** (optional). You can set the query to automatically update by selecting the **Auto-refresh** box. When you select the **Auto-refresh** option, your query automatically runs and computes a new result every time Viva Insights gets updated collaboration data for licensed people.

       > [!NOTE]
       > If organizational data used in an auto-refreshing query changes (for example, an attribute name is altered or an attribute is removed), the query might stop auto-refreshing.

     4. Type a **Description** (optional).   
     5. Change the metric rule (optional). To set a new metric rule, select **More settings**. Then, pick a new rule from the list. [Learn more about metric rules](../../analyst/metric-rules.md).

        > [!NOTE]
        > The **More settings** pane also contains **Group by** settings. This Power BI query is set to **Group by Month**, and you can't change this setting.

4. Under **Select business outcome metrics of interest**, select one or more metrics that include your business outcome data. Select the dataset type and name of the dataset that has the business outcome measures you are looking for. You can select up to 5 metrics maximum.  

5. Under **Predefined template metrics**, view a list of preselected metrics, which appear as gray tags. These metrics are required to set up the Power BI report and you can’t remove them. However, you can add other metrics by selecting **Add metrics**.

    > [!IMPORTANT]
    > Low-quality or missing organizational data might affect your metrics and result in warnings or errors. [Learn more about data quality notifications](../../analyst/data-quality-analyst-experience.md).

6. In **Select which employees you want to include in the query**, add filters to narrow down the employees in scope for your report. Don’t remove the predefined “Is Active” filter. [Learn more about filter and metric options](../../analyst/filters.md). If you notice a warning or error here, it's because one of your attributes is missing from your organizational data or it's of low quality.

7. Under **Select which employee attributes you want to include in the query**, add up to 20 organizational attributes. Once the query runs, you can use these attributes to group and filter the reports.

    > [!IMPORTANT]
    > This PowerBI query needs some specific attributes to run, and we've preselected them for you. These attributes appear in gray and you can't remove them. We might also include some attributes that help your template, but aren't required for your query to run. These attributes appear in blue and you can remove them.
    >
    > If you notice attributes marked with yellow warnings, that attribute's quality is low. If you notice attributes marked in red and the query's **Run** button disabled, then your organizational data is missing that attribute.
    >
    > [Learn more about attributes and data quality](../../analyst/data-quality-analyst-experience.md).

8. Select **Run** on the upper right. The query might take a few minutes to run.

## Access query results

You can access the report in two different ways:  

* View the report in the browser. Use this option if you only want to View the report.  

* Open the Power BI template in Power BI desktop and connect to your query results. Use this option if you want to customize the report or share it with others in your organization by publishing the report to the Power BI Service.

### View report in the browser  

To view the report in the browser, go to the **Query results page** and select the eye icon in the View column. Select **Open in new tab** if you want to keep the report in the background while doing other tasks in Advanced insights.

### Open the Power BI template in Power BI Desktop

1. Go to the Query results page and select the Power BI icon in the Actions column to download the Power BI template and get the query and partition identifiers. You’ll need these identifiers later.  

2. Open the downloaded template.  

3. If you're prompted to select a program, select **Power BI**.  

4. When you're prompted by Power BI:  

    1. Paste in the partition and query identifiers.  
    2. Set the **Minimum group size** for data aggregation within this report's visualizations in accordance with your company's policy for viewing Viva Insights data.  
    3. Select **Load** to import the query results into Power BI.  

5. If prompted by Power BI, sign in using your organizational account. Power BI then loads and prepares the data. For large files, this process might take a few minutes.

    > [!IMPORTANT]
    > You need to sign in to Power BI with the same account you use to access Viva Insights. If available, select **Organizational account** from the left. You might have to sign in more than once.
    >
    > :::image type="content" source="../../images/analyst-pbi-org-account1.png" alt-text="Screenshot that shows signing into to Power BI on the Organizational account tab":::

## Report settings

### Report-level settings  

 View and set the following parameters on the **Settings** page. You will be introduced to the settings when first loading the Copilot business outcome report. You can also adjust the report settings as you go through the report pages through the **Settings** icon on the top-right corner of each page.  

* **Business outcome settings** – Define a threshold of favorable business outcomes for each business outcome measure included in the report.

* **Copilot usage category settings** – Customize the default Copilot usage categories. Copilot usage categories are based on Average monthly Copilot actions taken and the default thresholds for the Low, Medium and High Copilot usage categories are defined by the 25th and 27th percentiles.  
* **Report language** – Change the language for your report.

### Page-level settings  

On each report page you will be able to find the following settings at the top of the page:  

* **Time period for the report** – Select the start and end date for which you want to view data in the report.  

* **Apply filters** (optional) – Select the organizational attribute and values you want to use to filter the employees shown in this report.

On some of the report pages or cards you will be able to find two additional settings:  

* **Group by** – Select the primary group-by attribute shown in all the report pages. You can change this attribute at any time and all report pages will show group values by the new attribute.  

* **Business outcome metric filter** – Select the business outcome metric for which you’d like to focus the insights on the respective card or page.

## About this report  

The **Copilot business outcome** report includes the following report pages to help you better understand the relationship between Copilot usage and your business outcomes.

### Copilot business outcome summary  

This page provides an initial overview of business outcome scores for employees who use Copilot for Microsoft 365 more or less frequently. Microsoft WorkLab studies show consistent usage of AI is associated with higher feelings of productivity, work enjoyment, and meeting relief.   

* The card on the left summarizes the difference in average business outcome scores for employees grouped by their average monthly Copilot usage frequency. The usage frequency value counts the average number of days per month Copilot was used at least once.

    > [!IMPORTANT]
    > These differences have not been evaluated for statistical significance. Also, Copilot usage is unlikely to be the only variable responsible for any metric differences shown in this report, especially at the beginning of your organization’s AI transformation. Differences between groups and business conditions, including role responsibilities and seasonality, might influence business outcome scores. Additionally, the amount of time it takes for AI to impact any given metric will vary.

* The card on the right summarizes the top Copilot features used by employees with favorable business outcomes to get their work done. The definition of “favorable” can be customized on the query setup page.

### Identify how Copilot usage influences a specific business outcome  

This page allows you to focus on a particular business outcome and explore the influences of Copilot usage patterns.

* After selecting the business outcome of interest, the analysis on the left side identifies how Copilot usage behaviors may influence the business outcome. It uses a Power BI visual called “Key Influencers”, which analyzes your data, ranks the Copilot factors that matter, and displays them as odds. Although this Al visualization uses regression models, always keep in mind the factors beyond Copilot usage that may influence the business outcome that are omitted from these predictive models.  identifies how Copilot usage behaviors may influence the business outcome. It uses a Power BI visual called “Key Influencers”, which analyzes your data, ranks the Copilot factors that matter, and displays them as odds. Although this Al visualization uses regression models, always keep in mind the factors beyond Copilot usage that may influence the business outcome that are omitted from these predictive models.

* The right side of this page provides a breakdown of a key Copilot usage behavior metric (identified on the left), across teams or functions. This chart may inform what teams or functions you want to focus your adoption efforts on by going after those with the lowest Copilot usage (in terms of frequency, breadth, or consistency of use). Use the “Group by” slicer to select the HR attribute to use for this breakout. For example, if this report includes sales function-specific business outcome metrics such as “win rate” or “deals closed,” consider breaking out the information by different sales teams. If the business outcome metric is a more generic metric that could apply to different organizations or functions, consider breaking out the information by organization, team, function, or job family.

### How Copilot helps employees with favorable business outcomes get their work done

This section highlights how employees with favorable business outcomes use Copilot in their individual work as well as their work with others. Research from Microsoft’s Work Trend Index ([AI at Work Is Here. Now Comes the Hard Part](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part)) shows regular experimentation with AI as the most significant predictor of “power users,” which is defined as users familiar with generative AI who use it at least several times a week and report saving more than 30 minutes a day with it.

* After specifying the business outcome of interest, this page will use the definition of “favorable business outcome,” as defined by the user during query setup. The left side highlights the top Copilot features used by employees with favorable business outcomes for the selected business outcome. The metric displayed in the bar chart shows the percent net additional usage of the respective Copilot feature by those with favorable business outcomes compared to other employees.

* The insight on the right side explores how employees with favorable business outcomes are using Copilot to help them collaborate with colleagues. The table shows the percentage of meetings summarized by Copilot (out of the total number of meetings for the employees in this group), and the percentage of emails sent with Copilot assistance (out of the total number of emails sent).

### Opportunities to boost Copilot assisted value  

This page helps you identify opportunities to boost Copilot’s potential assisted hours and value. Copilot assisted hours is an estimate of the total time employees were assisted by Copilot over the selected time period. The metric is computed based on your employees’ actions in Copilot and multipliers derived from [our research on Copilot users](https://www.microsoft.com/en-us/worklab/work-trend-index/copilots-earliest-users-teach-us-about-generative-ai-at-work). Copilot assisted value represents the conversion to a dollar value based on a default average wage of $72 per person per hour. Select “How we calculate Copilot assisted value” to further explore the underlying calculations and customize the average wage numbers for your organization. To get started, select one of the two metrics in the dropdown menu at the top of the page.

* The chart on the left shows the difference in average Copilot assisted hours or value for employees in the low and high Copilot usage groups. The definitions for these categories can be customized in the Settings menu.

* The chart on the right shows the potential additional Copilot assisted hours and value that can be gained when boosting Copilot adoption among employees with inactive or low Copilot usage. The numbers are broken out by team. This insight takes the number of inactive or low Copilot usage and multiplies this number by the difference in average Copilot assisted hours/value between the inactive or low Copilot usage group and the high Copilot usage group.

The Copilot assisted hours metric should be viewed as a general estimate, based on the most relevant Copilot usage data and research currently available. The underlying calculation methodology will evolve over time as new information becomes available.

### Glossary  

View this report's metric definitions.

### Power BI tips, FAQs, and troubleshooting

[Learn more about how to share the report and other Power BI tips, troubleshoot any issues, or review the FAQ](..//..//analyst/templates/power-bi-faq-troubleshoot.md).

### Related topics  

* [Access query results and modify existing queries](..//..//analyst/query-results.md)  

* [Filters](..//..//analyst/filters.md) 
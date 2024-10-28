---
title: Create RaaS reports for Workday
ms.author: bhaswatic
author: bhaswatic
manager: elizapo
ms.reviewer: chrisarnoldmsft
ms.date: 10/28/2024
audience: admin
ms.topic: article
ms.service: viva-learning
search.appverid: MET150
ms.collection:
  - enabler-strategic
  - m365initiative-viva-learning
  - highpri
  - Tier1
ms.localizationpriority: medium
description: Learn how to create RaaS reports for catalog, user, assignment, and completion data in Workday for Viva Learning.
---

# Create RaaS reports for catalog, user, assignment, and completion data

This article consists of steps required for enabling catalog, user, assignment, and completion data sync in Workday and Viva Learning integration. 
Admins are required to create a custom RaaS report on the Workday portal. Once you have created integration system user of Workday portal and have provided all security access, follow these steps to create the required RaaS reports.  


> [!NOTE]
> All RaaS reports (catalog, user data, LRS) should be created from same user account or a single user should be given report ownership at Workday portal. This username should be inserted under Reporting URL attribute in Viva Learning Manage Provider. Review this example: `https://wd2-impl-services1.workday.com/ccx/service/customreport2/microsoft_dpt6/username/Viva_Learning_Catalog_Report.`

> [!NOTE]
> Admins need to create a custom report manually. This is a one time process. We are only supporting the report structure mentioned in this support article, any other changes in reports are not recommended.

1. Ensure that the **Workday to AAD user sync** is in place for your tenant.  
2. Enable inbound user provisioning with Workday to ensure that all users in Workday are synced to Azure Active Directory (AAD).
3. If you're already a Microsoft 365 customer, Workday to AAD user sync should be in place for your tenant. 

Check with your organization admins for details around same. Otherwise, you can refer to the steps mentioned here to enable the provisioning. [Tutorial: Configure Workday for automatic user provisioning with on-premises Active Directory](/entra/identity/saas-apps/workday-inbound-tutorial)

## Create RaaS report on the Workday portal for catalog sync

This report should be created from the primary Admin account of Workday to avoid any privacy and security related concerns. Currently we're syncing historic and present assignments.

1. Sign in to the **Workday Portal**.
   1. Sign in to Workday Portal.
   1. Search for the task "Create Custom Report."

2. Configure the report parameters.
   1. Title the Report Name as `Viva Learning Catalog Report`. The report name must exactly match this string.
   1. Set the Report Type as "Advanced."
   1. Mark checkbox "Enable as Web service."
   1. Mark checkbox “Optimized for performance.”
   1. In the "Data Source" field, go to "All" and select "Learning content." Select **OK**.

3. Add report fields.
   1. Once you select **OK**, Data Source has "Learning Content" as a value. Remove any existing value in the Data Source Filter field and add "Manageable Learning Content".
   1. Add the fields in "Columns" as outlined in the following schema. You see three objects for field "rating"; select the one with a hash (#) icon next to it.

   | Business object| Field | Column heading override| Column heading override XML alias|
   | --- | ---- | ---- | --- |
   | Learning content | Workday ID | LearningObjectId | LearningObjectId|
   | Learning Content | Title | Title | Title |
   | Learning Content | Description | Description | Description |
   | Learning Content | Link to Learning content | DeepLinkUrl | DeepLinkUrl |
   | Learning Content | Duration in Minutes | Duration | Duration |
   | Learning Content | Inactive Status | Inactive | Inactive |
   | Learning Content | Learning Content Type | ContentType | ContentType |
   | Learning Content | Content Provider | ContentProvider | ContentProvider |
   | Learning Content | Exclude from Search and Browse | IsNonSearchable | IsNonSearchable |
   | Learning Content | Rating | Rating | Rating |
   | Learning Content | Skill Level | DifficultyLevel | DifficultyLevel |
   | Learning Content | Topic | Topics | Topics |
   | Learning Content | Skills | Skills | Skills |
   | Learning Content | Third Party Content Thumbnail Image URL | ExternalImageURL | ExternalImageURL |
   | Language | User Language Code | Locale | Locale |
   | Learning Content | Last Updated | LastUpdated | LastUpdated |
    

   :::image type="content" alt-text="Screenshot of Edit Custom Report" source="../media/learning/wd-s2.2-3.png" lightbox="/Viva/media/learning/wd-s2.2-3.png":::

4. Under "Group Column Headings", add the below fields:

   | Business Object | Group column heading | Group column heading XML Alias |
   | --- | --- | --- |
   | Languages | Languages | Languages |
   | Learning content | learningContent_group | learningContent_group| 

5. Add filters to the report under "Filter section" 
        
   | And/Or | `(` | Field | Operator | Comparison type | Comparison value | `)` | Indexed | 
   | --- | --- |-- |----  | --- | ---- | ---|-----| 
   | And | | Learning Content Type | exact match with the selection list | Prompt the user for the value |  Prompt #1 || Yes | 
   | And | |  Last Updated | greater than or equal to | Prompt the user for the value | Prompt #2 | | Yes | 
   | And | | Last Updated | less than or equal to | Prompt the user for the value | Prompt #3 | | Yes |


    :::image type="content" alt-text="Screenshot of the formatted fields for filter values." source="../media/learning/workday-filters-for-catalog-raas.png" lightbox="../media/learning/workday-filters-for-catalog-raas.png":::

6. **Add the Prompts:** Go to **Prompts**. Mark "Display Prompt Values in Subtitles" and add following prompt values. You can directly copy and paste these values. 

   | Field | Prompt qualifier | Label for prompt | Label for prompt XML alias | Default type | Default value | Required | 
   | - | - | - | - | - | - | -| 
   | Learning Content Type | Prompt #1 | contentType | contentType | No default value | | Yes | 
   | Last updated | Prompt #2 | Start_Date | Start_Date | No default value | | Yes | 
   | Last updated | Prompt #3 | End_Date | End_Date | No default value | | Yes |
    

   :::image type="content" alt-text="Screenshot of the formatted fields for prompt values." source="../media/learning/workday-prompts-for-catalog-raas.png" lightbox="../media/learning/workday-prompts-for-catalog-raas.png":::

7. Go to **Advanced** and select the field **Optimized for Performance**.

   > [!NOTE]
   > After isEffective date changes, it is not possible to turn on optimized for performance. Considering the data volumns in hand, we can advise customers to uncheck this field.

8. Share the report with Integrated System User (ISU), which you created while enabling catalog sync. Go to the **Share** section in report, select the option "share with specific authorized groups and users" and add ISU name in the **Authorized users** field.  

   :::image type="content" alt-text="Screenshot of the Edit Custom Report window for the Catalog Report" source="../media/learning/wd-s2.2-8.png" lightbox="/viva/media/learning/wd-s2.2-8.png":::

9. Save the report. Select **OK**. 

    :::image type="content" alt-text="Screenshot of the final report" source="../media/learning/wd-s2.2-9.png" lightbox="/viva/media/learning/wd-s2.2-9.png":::

    1. Generate report URL. This URL is required as an input parameter on Viva Learning Admin tab. The same user who created the report should generate the URL.

        1. Select the report > **Web Service** > **View URLs**.

           :::image type="content" alt-text="Screenshot of the view urls section of a custom report." source="/viva/media/learning/wd-s2.2-10.png"  lightbox="/viva/media/learning/wd-s2.2-10.png" :::

        1. In next window, select any contentType and any date range and select **OK**.

           :::image type="content" alt-text="Screenshot of the View URLS Web Service window with the option to edit content types and dates" source="../media/learning/wd-s2.2-11.png" lightbox="/viva/media/learning/wd-s2.2-11.png":::

        1. Select **JSON**, this opens a new window.
  
           :::image type="content" alt-text="Screenshot of the new window that opens when you select JSON." source="../media/learning/wd-s2.2-12.png" lightbox="../media/learning/wd-s2.2-12.png":::

    1. In the next window, provide the Workday credentials and sign in. It downloads the JSON.

    1. Copy the URL from browser and append it post Viva_Learning_Catalog_Report. That is, the report name 

        1. for example, for Microsoft test tenant the URL is: `https://wd2-impl-services1.workday.com/ccx/service/customreport2/microsoft_dpt6/svasireddy/Viva_Learning_Catalog_Report?Start_Date=2023-03-01-08:00&End_Date=2023-05-14-07:00&contentType!WID=9882927d138b100019b928e75843018d&format=json`  
        1. After appending, the final URL for test tenant: `https://wd2-impl-services1.workday.com/ccx/service/customreport2/microsoft_dpt6/svasireddy/Viva_Learning_Catalog_Report` 
        1. Save the final URL, this is used as an input config parameter on Admin portal while enabling the configuration.  

    1. Once configuration is complete on the Admin portal, within the next 24 hours delta sync calls the report API, and accordingly data reflect in Viva Learning. Refer to this document for details on enabling integration on Admin portal. 

> [!NOTE]
> Assignments with the completion status “manually waived” are not shown on the Viva Learning UX. 

## Create RaaS report on Workday portal for user data sync

 Create this report from the primary Workday admin account to avoid any privacy and security related concerns. Currently we're syncing historic and present assignments. 

1. **Sign in to the Workday Portal**.
    1. **Sign in** 
    1. Search for the task "Create Custom Report" 

1. Configure the report parameters 
    1. Name the report "Viva Learning Users Report". The report name must match this string. 
    1. Indicate report type as "Advanced."
    1. Check "Enable as Web service" 
    1. Check "Optimized for performance" 
    1. In the "Data source," go to "All" and select "Workers for HCM reporting." Select **OK**.

1. Add report **Fields**.

1. Add the fields in "Columns."

    | Business object | Field | Column heading override | Column heading override XML alias | 
    |  - | - | - | - |
    | Worker | Workday ID | UserId | UserId | 
    |Worker | Preferred Name – First Name | FirstName | FirstName | 
    |Worker | Preferred Name – Last Name | LastName | LastName |
    | Worker | User Name | UserName | UserName |
    | Worker | Worker is Terminated | Terminated | Terminated | 
    |Worker | Public Primary Work Email Address | Email_Address | Email_Address |
    |     Worker  |     Employee ID  |     Employee_ID  |     Employee_ID  |

    :::image type="content" alt-text="Screenshot of the table in the View Custom Report for the Viva Learning Users report." source="../media/learning/wd-s2.3-raas1.png" lightbox="/viva/media/learning/wd-s2.3-raas1.png":::

   1. **Add filters to the report**

      1. Add following values in "Filter on Instances". Follow the steps mentioned below for adding calculated field. 
    
         | And/Or | Field | Operator | Comparison type | Comparison value |
         | - | - | - | - | - |
         | And | Hire Date | greater than or equal to | Prompt the user for the value | Starting Prompt | 
         |And | Hire Date | less than or equal to | Prompt the user for the value | Ending Prompt |

    1. Add the Prompts: Go to Prompts. Mark "Display Prompt Values in Subtitles" and add following prompt values. You can directly copy paste these values.  

       | Field | Prompt qualifier | Label for prompt | Label for prompt XML alias | Default type | Default value | Required | Don't prompt at run time| 
       | - | - | - | - | -| - | - | - |
       | Contingent Worker type | Contingent_Worker_Type | No default value | | | Yes |
       | Employee Type | Employee_Type | No default value | | | Yes | 
       | Worker Types | Worker_Types | No default value | | | Yes | 
       | Include Terminated workers | Include_Terminated_Workers | Specify default value | Yes | | Yes |
       | Hire Date | Starting Prompt | Start_Date | Start_Date | No default value | | Yes | 
       | Hire Date | Ending Prompt | End_Date | End_Date | No default value | | Yes | |

    1. Go to **Advanced** and select the field `Optimized for Performance.` 

    1. Share the report with Integrated System User (ISU) and respective security group that you created while enabling content sync. Go to the **Share** section in report, select the option "share with specific authorized groups and users" and add group name and user name in Authorized Groups and **Authorized users** field.

    1. Save the report. Select **OK**. 

    1. Once configuration is complete on Admin portal, within the next 24 hours delta sync calls the report API, and accordingly data reflect in Viva Learning. Refer to this document for details on enabling integration on Admin portal. 


## Create RaaS report on Workday portal for assignment by organization and their completion status

This report should be created from the primary Workday admin account to avoid any privacy and security related concerns. Currently we're syncing historic and present assignments. Here, learner record sync is abbreviated as **LRS**.

 
1. **Sign in to the Workday Portal**
    1. **Sign in**.
    2. Search for the tasks "Create Custom Report."

2. Configure the report parameters 
    1. Name the report "Viva Learning LRS Assignments Report". The report name must match this string. 
    2. Set Report Type as "Advanced."
    3. Mark checkbox "Enable as Web service."
    4. In the "Data Source" field, go to "All" and select "Learning Assignments Records”. Select **OK**.

3. Add report fields.
    1. Once you select **OK**, the "Data Source" automatically sets the value as "Learning Assignment Records." For the "Data Source Filter" field, remove any existing value and add "Assignment Records for ~Person~from Learning Organization". You can copy this value and paste in the field directly.
    1. Add the fields in "Columns" as outlined below. You see two objects for “Learning Assignment," select the one with a blue icon next to it.
    
    |Business object | Field | Column heading override | Column heading override XML alias| 
    | - | - | - | - | 
    | Learning Assignment | Workday ID | AssigmentId | AssigmentId
    Worker | Workday ID | LearnerId | LearnerId| 
    | Learning Content | Workday ID | LearningObjectId | LearningObjectId| 
    | Learning Assignment | Due Date | DueDate | DueDate|
    |Learning Assignment | Assignment Status | CompletionStatus | CompletionStatus| 
    | Learning Assignment | Assigned Date | AssigmentDate | AssigmentDate| 
    |Assigned By | Workday ID | AssignerId | AssignerId |
    |Learning Assignment |  Assignment Record Completion Moment | CompletionDate | CompletionDate | 
    | Learning Assignment | Required | AssignmentType | AssignmentType | 

    > [!NOTE]
    > The In progress status from Workday doesn't sync to Viva Learning.

4. Under "Group Column Headings", add the following fields.

   | Business object | Group column heading XML alias | 
   | - | - | 
   | Assigned By | Assigned_By_group |
   | Learning Assignment | Learning_Assignment_group |
   | Learning Content | Learning_Content_group |
   | Worker | Worker_group |

5. Under Prompt mark "Display Prompt Values in Subtitles" and, add following the prompt values. You can directly copy and paste these values. In the 'Default Value' field for "learning Organization for Learning Assignment," provide the default value of the top organization (root organization) for which you need the report that is being pivoted.

   | Field | Label for Prompt XML Alias | Default Type | Default value | Required | Don't Prompt at Runtime |
   | - | - | - | - | - | - | 
   |  Learning Organizations for Learning Assignment | Learning_Organizations_for_Learning_Assignment | No default Value | | Yes | | 
   | Include Subordinate Organizations | Include_Subordinate_Organizations | Specify default value | Yes | Yes | Yes | 

6. Add date filters to the report for delta sync. 
        
    1. Go to "Filters". Select “+”, In “And/Or” select And. in "Field" select "create calculated field for report".
    1. In next screen, write "Field name" as ModifiedDate and select "Function" as Build Date. Select **OK**.
    1. In next screen, add following values under Date Fields and select **OK**.

       | Field | Value |
       | - | - | 
       | Extract Year from Date Field | Last Functionally Updated |
       | Extract Month from Date Field | Last Functionally Updated |
       | Extract Day from Date Field | Last Functionally Updated |

    1. Add following values in remaining fields of the start filter:

       | Field | Value |
       | - | - |
       |Field | Modified Date|
       | Operator | Greater than or equal to |
       | Comparison Type | Prompt the user for the value and ignore the filter condition if the value is blank |
       | Comparison Value | Starting Prompt | 

    1. Add another filter and with following values and select “OK”.

       | Field | Value |
       | - | - | 
       |Field | ModifiedDate|
       | Operator | Less than or equal to | 
       |Comparison Type | Prompt the user for the value and ignore the filter condition if the value is blank |
       | Comparison Value | Ending Prompt | 
   
      :::image type="content" alt-text="Screenshot of the filter on instances for the self-enrollment completion fields." source="../media/learning/workday-assignment-raas-10.png" lightbox="../media/learning/workday-assignment-raas-10.png":::

    **Modify the prompts**

    1. Go to **Prompts**. 

        1. Select **Populate Undefined Prompt Defaults**. This selection adds the start and ending prompt for Modified date, which is defined in the previous step.

           :::image type="content" alt-text="Screenshot of the self-enrollment completion prompts" source="../media/learning/workday-assignment-raas-11.png" lightbox="../media/learning/workday-assignment-raas-11.png":::

        1. Add following values in the new prompts and select **OK**.

           - For Starting Prompt, add value `Start_Date` in fields **Label for Prompt** and **Label for Prompt XML Alias**
           - For Ending Prompt, add value `End_Date` in fields **Label for Prompt** and **Label for Prompt XML Alias**

    1. Go to **Advanced**. Uncheck the field **Optimized for Performance**

    1. Save the report. Select **OK.**

    1. Share the report with Integrated System User (ISU) and the respective security group, which you created while enabling content sync.

    1. Within the next 24 hours LRS sync calls the report API and accordingly data reflect in Viva Learning, provided Admin has enabled LRS on Admin portal. Refer to this document for configuration steps on Admin portal.

> [!NOTE]
> The assignments with the completion status of "manually waived" aren't displayed in the Viva Learning user experience. 

## Create RaaS report on the Workday portal for completion status of self-enrollment

This report should be created from the primary Workday admin account to avoid any privacy and security related concerns. Currently we're syncing historic and present assignments. 
 
1. **Sign in to the Workday Portal**.

   1. **Sign in**.
   2. Search for "Create Custom Report."

1. Configure the report parameters 

   1. Name the report "Viva Learning Self Enrollment Report". The report name must match this string. 
   2. Set Report Type as "Advanced."
   3. Mark checkbox "Enable as Web service."
   4. In the "Data Source" field, go to "All" and select "Learning Enrollments”. Select **OK**.

1. Add report fields.

   1. Once you select **OK**, the "Data Source" automatically sets the value as "Learning Enrollments." Leave the "Data Source filter" field blank.
    
   1. Add the fields in "Columns" as per below schema. You see two objects for “learning Enrollment, select the one with a blue icon next to it.

      | Business object | Field | Column heading override | Column heading override XML alias |
      | - | - | - | - |
      |Learning Enrollment | Workday ID | EnrollmentId | EnrollmentId |
      | Learning Enrollment Participant | Workday ID | LearnerId | LearnerId |
      | Learning Content Detail | Workday ID | LearningObjectId | LearningObjectId |
      | Learning Enrollment | Completion Status | CompletionStatus | CompletionStatus |
      | Learning Enrollment | Completion Date | CompletionDate | CompletionDate |

      :::image type="content" alt-text="Screenshot of the Workday self enrollment report" source="../media/learning/workday-self-enrollment-report.png" lightbox="../media/learning/workday-self-enrollment-report.png":::

   1. Under "Group Column Headings", add these fields: 

      | Business object | Group column heading XML alias |
      | -- | -- | 
      | Learning Content Detail | Learning_Content_Detail_group |
      | Learning Enrollment | Learning_Enrollment_group | 
      | Learning Enrollment Participant | Learning_Enrollment_Participant_group | 

    1. Add filters to the report for delta sync.

       1. Go to "Filters". Select “+”, In “And/Or” select And. in "Field" select "create calculated field for report".
       1. In next screen, write "Field name" as ModifiedDate and select "Function" as Build Date. Select **OK**.
       1. In next screen, add following values under Date Fields and select **OK**.

          | Field | Value |
          | - | - |
          | Extract Year from Date Field | Last Functionally Updated |
          | Extract Month from Date Field | Last Functionally Updated |
          | Extract Day from Date Field | Last Functionally Updated |

       1. Add following values in remaining fields of the start filter:

          |Field | Value|
          | - | - |
          | Field | ModifiedDate |
          | Operator | Greater than or equal to |
          | Comparison Type | Prompt the user for the value and ignore the filter condition if the value is blank |
          | Comparison Value | Starting Prompt |

       1. Add another filter and with following values and select **OK**.

          |Field | Value|
          | - | - |
          | Field | ModifiedDate |
          | Operator | Less than or equal to |
          | Comparison Type |  Prompt the user for the value and ignore the filter condition if the value is blank |
          | Comparison Value | Ending Prompt |
        
       1.	Go to filter and add 2 new "And" filters and input following values:
        
          |     And/Or    |     (    |     Field    |     Operator    |     Comparison   type    |     Comparison   value    |     )    |     Indexed    |
          |---|---|---|---|---|---|---|---|
          |     And    |          |     Modified Date    |     greater than or   equal to    |     Prompt the user   for the value    |     Starting Prompt    |          |          |
          |     And    |          |     Modified Date    |     less than or   equal to    |     Prompt the user   for the value    |     Ending Prompt    |          |          |
          |     And    |          |     Learning   Assignment    |     Is empty    |          |          |          |          |
          |     And    |          |     Completion   Status    |     In the selection   list    |     Value specified   in the filter    |     Completed    |          |     Yes    |
        
        
    :::image type="content" alt-text="Screenshot of the self-enrollment completion filters in Workday" source="../media/learning/workday-self-enrollment-completion-filters.png" lightbox="../media/learning/workday-self-enrollment-completion-filters.png":::

## Modify the prompts

1. Go to **Prompts**.

    1. Select **Populate Undefined Prompt Defaults**. This selection adds the start and ending prompt for the Modified date, which is defined in previous step.
    
       :::image type="content" alt-text="Screenshot of the Workday self enrollment completion prompts." source="../media/learning/workday-self-enrollment-completion-prompts.png" lightbox="../media/learning/workday-self-enrollment-completion-prompts.png":::

    2. Add following values in the new prompts and select “OK”.

       - For Starting Prompt, add value StartDate in fields Label for Prompt and Label for Prompt XML Alias
       - For Ending Prompt, add value EndDate in fields Label for Prompt and Label for Prompt XML Alias

1. Go to **Advanced.** Uncheck the field **Optimized for Performance**. 

1. Save the field. Select **OK**.

1. Share the report with Integrated System User (ISU) and respective security group, which you created while enabling content sync. Go to the **Share** section in the report, select “Share with specific authorized groups and users” and add group name and user name in Authorized Groups and Authorized users field. 

1. Within the next 24 hours, the LRS sync calls the report API and accordingly reflects the data in Viva Learning. This depends on whether the admin has enabled LRS on Admin portal. Refer to this document for configuration steps on the Admin portal.

> [!NOTE]
> Lessons are not supported in self-enrollment completion status.

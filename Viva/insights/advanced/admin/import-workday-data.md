---
ROBOTS: NOINDEX,NOFOLLOW
ms.date: 10/29/2024
title: Import organizational data from Workday
description: Learn how to set up a connection and import your data from Workday to the Viva Insights advanced insights app
author: zachminers
ms.author: v-zachminers
ms.topic: article
ms.localizationpriority: medium
ms.collection: viva-insights-advanced
ms.service: viva-insights
manager: anirudhbajaj
audience: Admin
---

# Import organizational data from Workday

>[!IMPORTANT]
> This feature is for private preview customers only. Features in preview might not be complete and could undergo changes before becoming available in the broader public release.

Your organizational data can appear in the Microsoft Viva Insights’ advanced insights app in one of four ways:

* Through Microsoft Entra ID, which is the default source
* Through a .csv file that you as an Insights Administrator upload
* Through an API-based import that you, your source system admin, and your Microsoft 365 admin set up
* Through a connection between Workday and Viva Insights

This article talks about the fourth option: importing data through a Workday connection.

## Prerequisites

Before you can set up a connection between Workday and Viva Insights, you'll need the following information about your Workday environment from your Workday admin:

* Tenant name
* Subdomain
* Username
* ClientID
* Complete steps within Workday described in later section

## For the first import

If this isn’t the first time you’re importing data from Workday, jump to [For all imports](#for-all-imports).

### 1. Set up your Workday connection

*Applies to: Insights Administrator*

1. In the advanced insights app's admin experience, go to either the **Data hub** or the **Organizational data** page.
    1. On the **Data hub** page, select **Start** under **Data source > Workday**.
    2. On the **Organizational data** page's **Data connection** tab, select **Manage data sources**. Then, select **Start** under **Workday**. 
2. Under **Set up Workday connection**:
    1. Enter a name for your connection.
    2. The Authorization type is pre-selected to be **OAuth with client credential**.
    3. Contact your Workday admin to complete the steps in Workday described below.
    4. Under **Import organizational data from Workday**, select **Download certificate**. A x509 certificate file will download called "publicKey.pem." Open the file in a text editor and copy its contents. Share this with the Workday admin.
    5. Enter the Workday **Tenant name**, **subdomain**, and **ClientID** provided by the Workday admin.
    6. For **username**, enter the name of the ISU created by the Workday admin.
    7. Select how frequently you want Workday to send data to Viva Insights: weekly or monthly.
    8. Read the acknowledgment note and select **Accept**.

### 2. Steps within Workday

*Applies to: Workday admin*

1. Open Workday. Search for "Create Integration System User" and select it. This is a system user not associated with a real person.

    :::image type="content" source="../images/org-data-workday-01.png" alt-text="Screenshot of the search field for Create Integration System user.":::

2. Under **Create Integration System User**, fill out each field, then select **OK**.  

    :::image type="content" source="../images/org-data-workday-02.png" alt-text="Screenshot of the page to Create Integration System User.":::

3. Create a security group. In Workday, search for “Create Security Group” and select it.

4. Select **Integration System Security Group (Unconstrained)**.

    :::image type="content" source="../images/org-data-workday-03.png" alt-text="Screenshot of the page to create a security group.":::

5. Add the Integration System User to this group.

6. Search for "Maintain security group" and select **Maintain Permissions for Security Group**.

    :::image type="content" source="../images/org-data-workday-04.png" alt-text="Screenshot of the page to maintain permissions for the security group.":::

7. Next to **Operation**, select **Maintain**. Next to **Source Security Group**, select your created security group.

    :::image type="content" source="../images/org-data-workday-05.png" alt-text="Screenshot of the page to select your created security group.":::

8. Select the "+" icon to add a new **Domain Security Policy Permission**.
    1. Leave the **Selected** checkbox selected.
    2. Next to **View/Modify Access**, select **Get Only**. 
    3. For **Domain Security Policy**:  
        1. Add **Worker Data: Public Worker Reports**
        2. Add **Worker Data: Organization Information**
        3. Add **Worker Data: Private Work Email Integration**
        4. Add **Worker Data: Current Staffing Information**

        :::image type="content" source="../images/org-data-workday-06.png" alt-text="Screenshot of the page to add domain security policies.":::

9. Search for "Activate Pending Security Policy Changes" and select it.

10. Add a descriptive comment about the change and select **OK**.

11. Select **Confirm**, then select **OK**. You now have a new system user with the proper permissions they need to get worker data.

### 3. Register an API Client

1. Search for "Register API Client" and select it.

    :::image type="content" source="../images/org-data-workday-08.png" alt-text="Screenshot of the page to search for an API client.":::

2. Fill out the following fields: 
    1. Give the client an appropriate name, such as "VivaConnectorClient."  
    2. For the client grant type, select **Jwt Bearer Grant**.
    3. For **x509 certificate**:  
        1. Select **Create x509 Public Key**.
        2. Give the certificate an appropriate name, such as "VivaX509Certificate."
        3. Paste the contents of the publicKey.pem file shared by the Insights admin from the earlier step.
        4. Select **OK**.
        5. Ensure this certificate is selected for the field **x509 Certificate**.
    4. For **Integration System User**, enter the user you created earlier.
    5. Leave the access token type as "Bearer."
    6. Under **Scope (Functional Areas)**, search for and select "Staffing" and "Contact Information."  
    7. Leave **Include Workday Owned Scope** cleared.  
    8. Select the default values for the remaining fields.

3. Select **OK**.

    :::image type="content" source="../images/org-data-workday-09.png" alt-text="Screenshot of the API client.":::

4. A few new fields should populate below **Restricted to IP Ranges**. Save the following information and share them with the Insights admin to enter in Viva Insights:
    1. "ClientID"
    2. The first segment of the Workday REST API Endpoint, between "https://" and "workday.com." This is your Workday subdomain name.
    3. The last segment of the Workday REST API Endpoint. This is your Workday Tenant Name.


## For subsequent imports

If you’ve already set up your connection and imported a first set of data to Workday, follow these steps to edit your connection:

In the advanced insights app's admin experience, go to either the **Data hub** or the **Organizational data** page.

1. On the **Data hub** page, select **Start** under **Data source > Workday**.

2. On the **Organizational data** page's **Data connection** tab, select **Manage data** sources. Then, select **Manage** under **Workday**.

You’ll arrive at the **Edit Workday connection** page.

1. Enter your workday credentials: tenant name; subdomain; username; and ClientID.

2. If you want to turn on or off Workday’s ability to send data to Viva Insights, select or clear the **Enabled** checkbox.

3. If you want to update how often Workday data goes to Viva Insights, use the dropdown menu beneath **Refresh schedule**.

4. Read the acknowledgment note and select **Accept**.


## For all imports

### How Workday sends data to Viva Insights

When you connect Workday to Viva Insights, Workday sends over a set of predefined source columns. These columns are mapped to Viva Insights data fields. You can't change these predefined fields right now, but you'll be able to in the future.

To upload additional reserved or custom fields beyond the below list, use a .csv upload in parallel with Workday to upload those fields. Data from the .csv upload will add to the data from Workday. Ensure that the.csv file contains all the EffectiveDates as Workday upload dates to prevent data overrides. You can determine the upload dates for Workday from the Import history in Data connections.

#### Field mapping

The following table shows how Workday fields correspond to Viva Insights fields. For specific details about each Viva Insights field, including data type and formatting requirements, refer to the [Attribute reference in Prepare organizational data](/viva/insights/advanced/admin/prepare-org-data).

|Workday field|Viva Insights field|
|----|----|
|`responseData.worker.workerData.personalData.contactData.emailAddressData`|PersonId
|`responseData.worker.workerData.employmentData.workerJobData.positionData.managerAsOfLastDetectedManagerChangeReference.ID` and `responseData.worker.workerData.workerID`|	ManagerId
|`responseData.worker.workerData.organizationData.workerOrganizationData.organizationData.organizationName`| Organization
| Date of upload | EffectiveDate |
|`responseData.worker.workerData.employmentData.workerJobData.positionData.effectiveDate`|EffectiveDate
|`responseData.worker.workerData.employmentData.workerJobData.positionData.jobProfileSummaryData.managementLevelReference.ID`| LevelDesignation
|`responseData.worker.workerData.employmentData.workerJobData.positionData.jobProfileSummaryData.jobFamilyReference.ID`|FunctionType
|`responseData.worker.workerData.employmentData.workerJobData.positionData.jobProfileSummaryData.managementLevelReference.ID`|Layer
|[No mapping from Workday]	| HourlyRate
`responseData.worker.workerData.employmentData.workerStatusData.hireDate`|	HireDate
|[No mapping from Workday]	|SupervisorIndicator
|[No mapping from Workday]	| OnsiteDays
|`responseData.worker.workerData.employmentData.workerJobData.positionData.businessSiteSummaryData.locationReference`|Location


## Validation

After you connect Workday to Viva Insights, the advanced insights app starts validating your Workday data.

After this phase completes, validation has either succeeded or failed. Depending on the outcome, you'll either receive a success status or a failure status in the Import history table on the **Data connections** screen.

For information about what happens next, go to the appropriate section:

- [Validation succeeds](#validation-succeeds)

- [Validation fails](#validation-fails)

### Validation succeeds

After successful validation, Viva Insights starts processing your new data. Processing can take between a few hours and a day or so. During processing, you’ll see a “Processing” status on the **Import history** table.

After processing completes, it's either succeeded or failed. Depending on the outcome, you’ll either find a “Success” or “Validation failed” status in the **Import history** table.

#### Processing succeeds

When you find the “Success” status in the **Import history** table, the import process is complete.

After you receive the “Success” status, you can:

* Select the view (eye) icon to see a summary of the validation results.
* Select the mapping icon to see the mapping settings for the workflow.

#### Processing fails

If processing fails, you’ll find a “Processing failed” status in the **Import history** table. You can try to import your data again.

>[!Note]
>Processing failures are generally due to backend errors. If you’re seeing persistent processing failures and you’ve corrected the data in your import file, log a [support ticket](/microsoft-365/admin/get-help-support) with us.


### Validation fails

If data validation fails, you'll see a "Validation failed" status in the **Import history** table. For validation to succeed, the Workday admin needs to correct errors and push the data to Viva Insights again. Under **Actions**, select the download icon to download an error log. Send this log to the Workday admin so they know what to correct before sending the data again. 

The data source admin might find the following section helpful to fix data errors in their export file.

### Suspended state

If you see a "Suspended" status in the **Import history** table or when you select **Manage data sources**, this means your authorization credentials have expired. You’ll need to update your credentials and reconnect the data source.

#### Guidelines for correcting errors in data

*Applies to: Workday admin*

When any data row or column has an invalid value for any attribute, the entire import will fail until the data source admin fixes the source data. Refer to [File rules and validation errors](rules-validation-errors.md) for specific formatting rules that might help resolve errors you encounter.

Unless you’re updating data for existing employees, keep in mind that **PersonId**, **ManagerId**, **Organization**, and **EffectiveDate** are required for all rows. If you’re *just* updating data for existing employees, **PersonId** and **EffectiveDate** are required for all rows.

>[!Note]
>If you don't enter a value for **EffectiveDate**, Viva Insights will assign the date of upload.

## Related topic

[Prepare organizational data](prepare-org-data.md)

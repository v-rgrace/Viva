---
title: FAQs for Configuring Workday in Microsoft Viva Learning 
ms.author: bhaswatic
author: bhaswatic
manager: elizapo
ms.reviewer: chrisarnoldmsft
ms.date: 12/09/2024
audience: admin
ms.topic: article
ms.service: viva-learning
search.appverid: MET150
ms.collection:
  - enabler-strategic
  - m365initiative-viva-learning
  - highpri
ms.localizationpriority: medium
description: FAQs for how to configure and manage Workday for Microsoft Viva Learning.

---

# FAQs in Configuring Workday in Microsoft Viva Learning

This article outlines answers for frequently asked questions about the integration between Workday and Microsoft Viva Learning.

## When will the content reflect in the Viva Learning app after configuration?

We estimate 24 - 48 hours for a full sync, depending on the assignment size.

## When will assignments reflect in Viva Learning app after configuration?

We estimate 24 - 48 hours for a full sync, depending on the assignment size.

## What are the sync frequencies?


|     Data Type    |     Sync   frequency    |
|---|---|
|     Catalog     |     Delta   sync runs every 24 hours, capture delta for last 24 hrs    |
|     Workday   hosted thumbnails    |     Delta   sync runs every 24 hours, capture delta for last 24 hrs    |
|     3P   Thumbnails    |     Delta   sync runs every 24 hours, capture delta for last 24 hrs    |
|     User RaaS    |     Full sync   every 12 hours    |
|     Assignments    |     Delta   sync runs every 12 hours, capture delta for last 12 hrs    |
|     Assignment   completions    |     Delta   sync runs every 12 hours, capture delta for last 12 hrs    |
|     Self-enrolment   completions    |     Delta   sync runs every 12 hours, capture delta for last 12 hrs    |

These frequencies might vary for some customers in any custom implementation.

## How can I trigger the manual full sync?

Admins can trigger the manual sync from the Manage Providers within the Viva Learning Admin tab. Admins require Global Admin, Knowledge Admin, and Knowledge Manager permissions. The full trigger option is available for catalog sync.

## What if the admin user creating the refresh token leaves the organization?

The refresh token is tied to a Workday account, which is the *Information System User* and not any specific user. This refresh token is additionally available in the context of the client which an admin creates in Workday. This client isn't tied to the admin user who created it. It's available to all the admins in the tenant.

## Is there any other “grant type" apart from `refresh_token`?

No, Workday only supports the `refresh_token` grant type for system-to-system integrations. Types like `client_credentials` aren't supported.

## How is the refresh token stored?
 
The refresh token can be stored as an encrypted object, similarly to password and user IDs.

## What are the required permissions for the user creating the report and providing the permissions?

This action requires the **Get Only** access to the **Reports: Learning Record** domain. For more information, see the steps mentioned for enabling learner record sync (LRS).

## How do I execute the RaaS reports?

Once a RaaS report is created, you can execute or run it from the Workday portal.

## How does Viva Learning generate access token for OAuth?

The refresh token is generated based on client ID, client secret and refreshes token. The admin needs to update all three fields in the MAC portal. The refresh token is a nonexpiring one analogous to the client secret or passwords that we stored for other providers. The refresh token’s infinite time to live (TTL) shouldn’t be a concern.

## What happens if the sync fails?

If the sync fails, the admin can export the catalog logs for details around sync errors.

## How can I edit scopes in API client?

Go to the View API Client task. You can select the client under API Clients for Integration and update the scope.

![A screenshot of the Workday API client with the option to upgrade the scope.](/viva/media/learning/workday-FAQ-1.png)


## How can I filter the providers integrated into Workday in Catalog RaaS?

This scenario isn't supported.

## How can I test if my report is working as expected?

Go to **Report** and select **Run** or **Test** and then add desired time field values. If configured correctly, the report successfully runs.

![A screenshot of the action window with the option to run the report.](/viva/media/learning/workday-FAQ-4.png)

## How does Viva Learning store thumbnail images?

Thumbnail images for providers integrated in Workday (for example, LinkedIn configured in Workday) are ingested using the RaaS report. Thumbnail image for Workday-hosted content is pulled through the APIs. Viva Learning also supports the thumbnail image format supported by Workday.

## What if an API configuration isn't added in Viva Learning?

API is a required field for configuration.

## What is the payload size limit in the RaaS reports?

For a single report API call, a maximum of 3 million records (2GBs) is returned and the maximum execution time of single API call is 30 mins. 
You can make a maximum of 75,000 requests in a 24 hour period (15k requests per hour). Report execution timeout is 30 mins but can hit a session or http gateway timeout before that time. For more information, see the [Workday support article on RaaS](https://docs.workato.com/connectors/workday/workday_raas.html).

## What happens to the courses if `InNonSearchable` is `True` in Workday?

These courses aren't available for search in Viva Learning. 

## What happens to the courses if `IsEffectiveDate` is set to the future?

The course isn't ingested in Viva Learning.

## What special characters can be stored in content title and description?

Special characters can be added on Workday in the content title and description. Viva Learning doesn't support the different text formatting for descriptions that are available in Workday.

## What if the client ID, secrets and auth token are expired?

You need to regenerate it from the Workday portal and reconfigure Workday on Viva Learning with new parameters. 

## Does Viva Learning supports learning journeys or paths from Workday?

We don't support these scenarios.

## Are permissions from Workday supported in Viva Learning?

We don't support these scenarios.

## Can you provide a list of the endpoints that Viva Learning is accessing?

To fetch RaaS reports, Viva Learning uses REST API. The URL for this report isn't fixed and depends on the user and Workday account name. The following [SOAP APIs](https://community.workday.com/sites/default/files/file-hosting/productionapi/Learning/v39.2/Learning.html) endpoints are used to fetch thumbnail images for Workday hosted content:

- [Get Learning Digital Courses](https://community.workday.com/sites/default/files/file-hosting/productionapi/Learning/v39.2/Get_Learning_Digital_Courses.html)
- [Get Learning Blended Courses](https://community.workday.com/sites/default/files/file-hosting/productionapi/Learning/v39.2/Get_Learning_Blended_Courses.html)
- [Get Learning Lesson](https://community.workday.com/sites/default/files/file-hosting/productionapi/Learning/v39.2/Get_Learning_Lessons.html)
- [Get Learning Programs](https://community.workday.com/sites/default/files/file-hosting/productionapi/Learning/v39.2/Get_Learning_Programs.html)

## Which of the RaaS reports are indexed? Can reports handle large data volumes?

|RaaS report | Indexed? |
|--|--| 
| Catalog RaaS | **Indexed** | 
| User RaaS | **Indexed** | 
| LRS RaaS | **Not indexed**. The org ID-based report filtering is in place to handle large data sets| 
| Self enrollment RaaS | **Not indexed**. Unlike the LRS RaaS, this report isn't filterable on org ID. | 

## What are the guidelines in server migration?

If the server migration is expected to change the Workday Web Services (WWS) endpoint, RaaS URL, and deep links to courses, reach out to Viva Learning product team. 
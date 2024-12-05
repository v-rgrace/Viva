---
title: Access Viva Glint with Microsoft Entra ID
description: To access the Microsoft Viva Glint application, a Global administrator must first register Viva Glint in a Microsoft Entra tenant.
ms.author: SarahBerg
author: SarahAnneBerg
manager: elizapo
audience: admin
f1.keywords: NOCSH
keywords: Access, authentication, login, AAD, Azure Active Directory, Azure AD, sign in 
ms.collection: 
 - m365initiative-viva
 - selfserve
search-appverid: MET150
ms.topic: article
ms.service: viva-glint
ms.localizationpriority: high
ms.date: 12/05/2024
---

# Access Viva Glint with Microsoft Entra ID

To access the Microsoft Viva Glint application, a Microsoft 365 Global Administrator must register Viva Glint in a Microsoft Entra tenant. A Viva Glint Administrator must also import users to the Viva Glint app. Users must exist in both Microsoft Entra ID and Viva Glint with the same email address to successfully access the application.

If you don't already have a Microsoft Entra user account, you can [create one for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).

> [!NOTE]
> To add a Support or Partner user to Viva Glint, follow this guidance: [Add an external user to Viva Glint.](add-external-user.md)

## Set up and manage a Viva Glint Microsoft Entra tenant

For information on tenant creation, user and group creation, bulk user maintenance, authentication options, how to enable single sign-on, and federation, see the following articles:

- [Set up a Microsoft Viva Glint tenant](viva-glint-tenant-provision.md)
- [Create users and groups in Microsoft Entra ID](/training/modules/create-users-and-groups-in-azure-active-directory/)
- [Perform bulk user maintenance in Microsoft Entra ID](/training/modules/manage-user-accounts-licenses-microsoft-365/7-perform-bulk-user-maintenance-azure-active-directory)
- [What authentication and verification methods are available in Microsoft Entra ID?](/azure/active-directory/authentication/concept-authentication-methods)
- [Enable single sign-on for an enterprise application](/azure/active-directory/manage-apps/add-application-portal-setup-sso)
- [What is federation with Microsoft Entra ID?](/entra/identity/hybrid/connect/whatis-fed)
- [Microsoft Entra Connect and federation](/entra/identity/hybrid/connect/how-to-connect-fed-whatis)
- [Microsoft Entra federation compatibility list](/entra/identity/hybrid/connect/how-to-connect-fed-compatibility)

> [!NOTE]
> Users must exist in Entra with a Member Type of "Member" (not "Guest") to successfully access Viva Glint.

## Import users to Viva Glint

The Global administrator adds service administrators to Microsoft Entra ID and Viva Glint for initial access. As the service administrator, see information below to add other users (HR, leadership, managers, individual contributors) to Viva Glint.

> [!NOTE]
> Email addresses for users in Viva Glint must match email addresses tied to users in Microsoft Entra ID. Coordinate with the Global administrator for your Viva Glint Microsoft Entra tenant to ensure that these email addresses match.

### Understand prerequisites for importing users

To import users to Viva Glint, first follow critical data preparation steps:

- [Prepare and finalize data with the Employee Attribute Template](/viva/glint/setup/create-employee-attribute-template)
- [Review data with checklists](/viva/glint/setup/data-checklist)
- [Set up attributes in Viva Glint](/viva/glint/setup/send-employee-attributes)

### Import users

After employee data preparation and attribute setup:

- [Upload employee data to Viva Glint](/viva/glint/setup/choose-upload-method)

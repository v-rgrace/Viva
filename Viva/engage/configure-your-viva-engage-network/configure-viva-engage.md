---
title: "Configure your Viva Engage network"
f1.keywords:
- NOCSH
ms.author: donnabouldin
author: Starshine89
manager: elizapo
ms.date: 11/19/2024
audience: Admin
ms.topic: article
ms.localizationpriority: medium
ms.custom: Adm_Yammer
ms.service: viva-engage
search.appverid:
- MET150
- MOE150
- YAE150
ms.assetid: f886e916-fe64-41de-be52-38d458250fa5
description: "Use the Viva Engage admin tools to set up your Viva Engage network. Covers options for configuration, design, admins, usage policy, external networks, and activity stream keys."
---

# Configure your Viva Engage tenant

Configuring the Viva Engage tenant requires [Engage administrator](/viva/engage/eac-key-admin-roles-permissions#engage-administrator) privileges. Administrators don't need to be assigned a Viva Engage license to configure Viva Engage core or premium.
  
As you get started with Viva Engage, review the links in the [Viva Engage admin help](../eac-overview.md) for other tasks you might want to do, such as [reviewing security and compliance settings](../manage-security-and-compliance/security-and-compliance.md).

To ensure that your users have a consistent experience, complete these tenant configuration tasks in the Viva Engage admin center before inviting users to Microsoft Viva Engage Enterprise.
  
To access the Viva Engage tenant settings:
  
- In Viva Engage, select the settings icon and go to the admin center.
- In the admin center, on the **Setup and configuration** tab, select **Tenant settings**.

>[!NOTE]
> Because Viva Engage is powered by Yammer technology, configuring the tenant through the Yammer admin center publishes changes to both Yammer and Viva Engage. We are working to bring these configuration options to the Viva Engage admin center as part of our admin roadmap.

## Set the tenant name

> [!IMPORTANT]
> For Microsoft 365 Viva Engage tenants, the name in the Microsoft 365 company profile overrides the tenant name setting in Viva Engage. To change the company profile settings, see [Change your organization's address, technical contact, and more](/microsoft-365/admin/manage/change-address-contact-and-more)

- On the **Tenant settings** page, set the tenant name.

## Set a usage policy

To ensure that content is office‐appropriate, you may want to create a usage policy for engagement. For instructions and best practices, see [set up a usage policy](../set-up-usage-policy.md).

## Upload a tenant logo

As an Engage admin, network admin, or verified admin, you can choose to upload the org’s logo on the Viva Engage tenant. This logo appears on the user’s home feed and leadership corner header.

- Use the **Tenant logo** setting to add an image. Only one image can be uploaded at a time.

## Choose a language for system messages

The system generates messages in response to user actions. These messages let the user know if the action was successful. Actions that trigger system messages include changes to the network configuration and within the app.
  
- From the **Language** setting, choose a language for system messages.
 All future system messages appear in the language you choose. Existing system messages appear in the previous language.

## Set media configurations through the Engage admin center

To access the Yammer admin center:

- From the Viva Engage admin center, on the **Setup & Configuration** tab, select **Tenant settings**. On the Tenant settings page, under **Other**, select **Manage other tenant configurations through the Yammer admin center**.

- From Viva Engage, select the settings icon, and select **Edit Network admin Settings**.

## Turn private messages on or off

You can control whether private messages are allowed on the network at any given time. When you turn this feature off, you remove all reference to private messages in the Engage Inbox and the Share menu on any conversation thread.

Private message content remains ingested for eDiscovery. Users can navigate to old messages through notifications and search, but they can't reply to old messages while the feature is off for the network.

- On the **Configuration** page, in the **Enabled Features** section, select whether to disable private messages.

## Restrict file upload permissions and GIFs

In Viva Engage, users can attach files, including images and videos, to posts and replies. Files in community posts or replies are stored in the community's SharePoint library, while those in storyline posts or replies are stored in the author's OneDrive. Learn more about [file storage for communities.](https://support.microsoft.com/office/where-are-my-viva-engage-files-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443) and [file storage in Storyline.](/viva/engage/eac-storyline)

If your network is not yet [Native Mode](/viva/engage/overview-native-mode), attachments to posts and replies in communities not connected to a Microsoft 365 group are uploaded to Azure Cloud storage. Learn more about [file storage for non-native networks](https://support.microsoft.com/office/where-are-my-viva-engage-files-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443) and how to identify which communities are backed by Microsoft 365 groups and which are backed by Azure Cloud storage.

Configure the types of files that users can attach and upload in the Conversation settings page of the Admin center.

1. Sign in to Viva Engage as a network administrator.
2. Go to the [Viva Engage Admin center.](/viva/engage/eac-overview)
3. Select **Tenant settings**, then in the **Conversation settings** section, select **Edit**. <br>
4. In the **Conversation settings** section, select an option in the **File uploads** section.

    - **Allow all files** (default). People can attach and upload files in any format

    - **Allow only images and videos**. People can attach and upload images and videos, only. File type is determined by the file extension. 
    - **Disable uploads**. Users cannot attach files, including images and videos. Disabling uploads will not affect existing uploaded files.

5. In the **GIFs** section you can enable or disable adding GIFs directly within Viva Engage. GIF selection uses Tenor, a third-party service


**Additional Infromation** 

   - Attachments—file uploads—are enabled by default.
   - GIFs are enabled by default.
   - When attachments are enabled, people can attach an unlimited number of files, images or videos, up to 5 GB each, to a message or reply.
   - File types are determined based on the file’s extension. When **Allow all files** or **Allow only images and videos** is selected, you can attach pdf files, image files, video files, Microsoft Office files, and more. Each post can have a maximum of 100 files.  
   - When file uploads are restricted or disabled, people can continue to share links in their posts. Viva Engage does not support blocking links.
   - For networks in Native Mode [link to article], all files are checked for viruses when uploaded. For more information, see [Virus detection in SharePoint Online.](/defender-office-365/anti-malware-protection-for-spo-odfb-teams-about)
   - If your network is not in native mode, virus checking applies only to
       - Files attached to posts and replies on a storyline.
        - Files attached to posts and replies in a community attached to a Microsoft 365 group.
        - There is no virus check for files uploaded to communities in non-native networks that are not connected to Microsoft 365 groups. Admins can export the files to perform an offline virus scan on them. Custom scripting can automate this process. Learn more about [file storage for non-native networks.](https://support.microsoft.com/en-us/office/where-are-my-viva-engage-files-stored-fadfdefa-e00d-40b6-94cb-a9ddb171a443)



  
## Enable or restrict the use of third-party apps

The growing network of partners and developers in Viva Engage continue to build third-party applications using an API. To find the list of current apps, go to the [App Directory](https://go.microsoft.com/fwlink/?LinkId=524143). There, you can find integrations with Microsoft SharePoint, Microsoft Flow, Microsoft Dynamics, and many other business applications.
  
- On the **Configuration** page, in the **Enabled Features** section, specify whether to allow third-party applications.

  > [!CAUTION]
  > Clearing this setting prevents users from adding or accessing these applications. Note that all users, including verified admins, will lose access to apps that were added prior to clearing this setting.

  > [!NOTE]
  > This setting does not apply to Microsoft 365 connectors that can be added to Microsoft 365 groups. To disable use of these connectors in Viva Engage, use the following PowerShell command:  
  > Set-OrganizationConfig -ConnectorsEnabledforYammer:$false`
  >
  > For more information, see [Manage Microsoft 365 Groups with PowerShell](/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

## Allow Tenor GIFs in messages

By default, users can attach GIFs provided by Tenor, a third-party company, to posts.

> [!NOTE]
> The GIF search in Viva Engage defaults to Tenor's "young audience" and "strict" filters to keep GIFs appropriate in a school or work setting. If you see inappropriate GIFs in a search, send email to <support@tenor.com> with a link to the GIF.

You can turn off this feature so that users don't see GIFs from Tenor.

- From the **Configuration** page, in the **Enabled Features** section, turn off **Show Tenor GIFs Search**.

## Control how links are displayed

By default, when you create a message with a URL, Viva Engage fetches content associated with third-party websites, including title, summary, images, and GIFs. Existing URLs are cached and retained until the cache expires.

You can turn off the display of this data for links.

- On the **Configuration** page, in the **Enabled Features** section, enable or disable **Fetch URL Content**.

## Allow message translation

Enable this feature to allow users to translate messages from [any language supported by Microsoft Translator](https://www.microsoft.com/en-us/translator/languages.aspx) into the network's default language. To enable this feature, the network admin must accept a Terms and Services agreement for Microsoft's proprietary translation technology.

When this feature is enabled, users have a **Translate** option with any message posted in a language different than the language they've selected in **Preferences** in their Viva Engage settings.
  
- On the **Configuration** page, in the **Enabled Features** section, select whether to allow **Message Translation**.

## Allow abbreviated mentions

Enable this feature to allow users to @mention other users without their full name. For example, Carole Poland can be mentioned as Carole.

- On the **Configuration** page, in the **Enabled features** section, select **@mention custom usernames**.

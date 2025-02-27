---
title: "Office 365 Reports in the Admin Center - SharePoint activity"
ms.author: kaarins
author: kaarins
manager: pamgreen
audience: Admin
ms.topic: overview
f1_keywords:
- 'O365M_ReportsSPActivity'
- 'O365E_ReportsSPActivity'
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: "Get the SharePoint activity usage report to know about the activity of every SharePoint user, the number of files shared, and the storage utilization."
---

# Office 365 Reports in the Admin Center - SharePoint activity

As an Office 365 admin, the **Reports** dashboard shows you the activity overview across various Office 365 products in your organization. It enables you to drill in to get more granular insight about the activities specific to each product. Check out the [Activity Reports in the Microsoft 365 admin center](activity-reports.md).
  
For example, you can understand the activity of every user licensed to use SharePoint by looking at their interaction with files. It also helps you to understand the level of collaboration going on by looking at the number of files shared.
  
> [!NOTE]
> Some functionality is introduced gradually. This means that you may not yet see this feature or it may look different than what is described in the help articles. But don't worry - if you don't see it yet, it's coming soon! 
  
If you want to understand the amount of activity happening against each SharePoint site and the storage utilization, view the [SharePoint site usage report](sharepoint-site-usage.md).
  
> [!NOTE]
> You must be a global administrator in Office 365 or an Exchange, SharePoint, Skype for Business administrator, or reports reader to see Office 365 reports. 
  
## How do I get to the to the SharePoint activity report?

1. In the Microsoft 365 admin center, select **Reports** from the left menu or click on the **Reports** widget.<br/>![Check out new Office 365 activity reports](../media/2554deff-b840-4aa5-b2b2-83683996fedc.png)
  
2. Use the **Select a report** drop-drop at the top left and select **SharePoint activity**.<br/> ![Select a report](../media/fb7bb8ea-eeb7-48c9-b739-601f41ddee16.png)
  
## Interpreting the SharePoint activity report

You can get a view into SharePoint activity by looking at the **Files** and **Users** views.<br/> ![SharePoint Activity Report](../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|||
|:-----|:-----|
|1.  <br/> |The **SharePoint activity report** can be viewed for trends over the last 7 days, 30 days, 90 days, or 180 days. However, if you click into a particular day in the report, the table (7) will show data for up to 28 days from the current date (not the date the report was generated).  <br/> |
|2.  <br/> |Each report has a date for when this report was generated. The reports usually reflect a 24 to 48 hour latency from time of activity.  <br/> |
|3.  <br/> |The **Files** view helps you understand the unique numbers of licensed users that perform file interactions with files stored on SharePoint sites.  <br/> |
|4.  <br/> |The **Pages** view shows you the number of unique pages visited by users.  <br/> |
|5.  <br/> |The **Users** view helps you to understand the trend in the number of active users. A user is considered active if he or she has executed a file activity (save, sync, modify, or share) or visited a page within the specific time period.  <br/> NOTE: A file activity can occur multiple times for a single file, but will count only as one active file. For example, you can save and sync the same file multiple times over a specified time period, but it will count only as one single active file and one single synced file in the data           |
|6.  <br/> | On the **Files** chart, the Y axis is the count of unique files that a user either saved, synced, modified, or shared.  <br/>  On the **Users** chart, the Y axis is the number of unique users that either performed a file interaction (save, sync, modify, or share) on a site.  <br/>  On the **Pages** chart, the X axis is the count of unique pages the users visited.  <br/>  The X axis on all charts is the selected date range for this specific report.  <br/> |
|7.  <br/> |You can filter the series you see on the chart by clicking on an item in the legend. For example, on the **Files** chart, click or tap **Viewed or edited**, **Synced**, **Shared internally**, or **Shared externally** to see only the info related to each one. Changing this selection doesn't change the info in the grid table.  <br/> |
|8.  <br/> | The table shows you a breakdown of the activities at the per-site level.  <br/> ![SharePoint Activity report columns expanded](../media/c90607a8-3189-4eb5-af0e-1ec748c22c6b.png) <br/> **User name** is the email address of the user who performed the activity on the SharePoint Site.  <br/> **Last activity date (UTC)** is the latest date a file activity was performed or a page was visited for the selected date range. To see activity that occurred on a specific date, select the date directly in the chart.  <br/> ![Select a specific date in the chart](../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> This will filter the table to display file activity data only for users who performed the activity on that specific day.  <br/>  **Files viewed or edited** is the number of files that the user uploaded, downloaded, modified, or viewed.  <br/>  **Files synced** is the number of files that have been synced from a user's local device to the SharePoint site.  <br/>  **Files shared internally** is the count of files that have been shared with users within the organization, or with users within groups (that might include external users).  <br/>  **Files shared externally** is the number of files that have been shared with users outside of the organization.  <br/>  **Pages visited** are the visits to unique pages by the user.  <br/>  **Deleted** indicates that the user's license was removed.  <br/>  **NOTE:** Activity for a deleted user will still display in the report as long as he or she was licensed at some time during the selected time period. The Deleted column helps you to note that the user may no longer be active, but contributed to the data in the report.            Deleted date is the date on which the user's license was removed.  <br/>  Product assigned are the Office 365 products that are licensed to the user.  <br/> |
|9.  <br/> |Click or tap the **Manage columns** icon ![Manage Columns](../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) to add or remove columns from the report.  <br/> |
|10.  <br/> |You can also export the report data into an Excel .csv file, by clicking or tapping the **Export** ![Export](../media/b5d12006-a2b4-4db5-af41-40f9e7aec07f.png) link. This exports data for all users and enables you to do simple sorting and filtering for further analysis. If you have less than 2000 users, you can sort and filter within the table in the report itself. If you have more than 2000 users, in order to filter and sort, you will need to export the data.  <br/> |
|||
   


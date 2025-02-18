---
title: "Set an individual user's password to never expire"
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: 
- M365-subscription-management 
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: f493e3af-e1d8-4668-9211-230c245a0466
description: "Learn how to set some individual user passwords to never expire, using Windows PowerShell."
---

## Set password expiration policies in Azure AD

::: moniker range="o365-worldwide"

> [!TIP]
> Need help with the steps in this topic? We’ve got you covered. Make an appointment at your local Microsoft Store with an Answer Desk expert to help resolve your issue. Go to the [Microsoft Stores page](https://go.microsoft.com/fwlink/?LinkID=2041482) and choose your location to schedule an appointment.

::: moniker-end

A global administrator for a Microsoft cloud service can use the Microsoft Azure AD Module for Windows PowerShell to set user passwords not to expire. You can also use Windows PowerShell cmdlets to remove the never-expires configuration or to see which user passwords are set to never expire. 

This guide applies to other providers, such as Intune and Office 365, which also rely on Azure AD for identity and directory services. Password expiration is the only part of the policy that can be changed.

> [!NOTE]
> Only passwords for user accounts that are not synchronized through directory synchronization can be configured to not expire. For more information about directory synchronization, see [Connect AD with Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).
>






## Password Policies management by using PowerShell

### How to check the expiration policy for a password

* Run one of the following commands:

   * To see if a single user’s password is set to never expire, run the following cmdlet by using the UPN (for example, *user@contoso.onmicrosoft.com*) or the user ID of the user you want to check:
```
Get-AzureADUser -ObjectId <user id or UPN> | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  
Example:
```
Get-AzureADUser -ObjectId userUPN@contoso.com | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

 * To see the **Password never expires** setting for all users, run the following cmdlet: 
 
```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
 }
```  

* To get a report of all the users with PasswordNeverExpires in Html on the desktop of the current user with name  **ReportPasswordNeverExpires.html**


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Html | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.html
```  

* To get a report of all the users with PasswordNeverExpires in CSV on the desktop of the current user with name **ReportPasswordNeverExpires.csv**


```
Get-AzureADUser -All $true | Select-Object UserprincipalName,@{
    N="PasswordNeverExpires";E={$_.PasswordPolicies -contains "DisablePasswordExpiration"}
} | ConvertTo-Csv -NoTypeInformation | Out-File $env:userprofile\Desktop\ReportPasswordNeverExpires.csv
```  


### Set a password to expire

Run one of the following commands:

   * To set the password of one user so that the password expires, run the following cmdlet by using the UPN or the user ID of the user:

 `Set-AzureADUser -ObjectId <user ID> -PasswordPolicies None`

   * To set the passwords of all users in the organization so that they expire, use the following cmdlet:

 `Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies None`

### Set a password to never expire

Run one of the following commands:

   * To set the password of one user to never expire, run the following cmdlet by using the UPN or the user ID of the user: 

`Set-AzureADUser -ObjectId <user ID> -PasswordPolicies DisablePasswordExpiration`
   * To set the passwords of all the users in an organization to never expire, run the following cmdlet: 

`Get-AzureADUser -All $true | Set-AzureADUser -PasswordPolicies DisablePasswordExpiration`

   > [!WARNING]
   > Passwords set to `-PasswordPolicies DisablePasswordExpiration` still age based on the `pwdLastSet` attribute. If you set the user passwords to never expire and then 90+ days go by, the passwords expire. Based on the `pwdLastSet` attribute, if you change the expiration to `-PasswordPolicies None`, all passwords that have a `pwdLastSet` older than 90 days require the user to change them the next time they sign in. This change can affect a large number of users. 

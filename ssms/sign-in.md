---
title: Sign in or Switch User Accounts in SQL Server Management Studio
description: Learn how to sign in to SQL Server Management Studio (SSMS).
author: erinstellato-ms
ms.author: erinstellato
ms.reviewer: randolphwest, maghan, mbarickman
ms.date: 05/19/2025
ms.service: sql-server-management-studio
ms.topic: how-to
ms.collection:
  - data-tools
---
# Sign in or switch user accounts in SQL Server Management Studio

[!INCLUDE [sql-asdb-asdbmi-asa](includes/applies-to-version/sql-asdb-asdbmi-asa.md)]

In this article, you learn how to sign in to SQL Server Management Studio (SSMS), add and switch user accounts, update your profile, sign out of your account, and the benefits to signing in. To learn how to access multiple user accounts in SSMS, see [Access multiple accounts](/visualstudio/ide/sign-in-access-multiple-accounts). For guidance on how to add your public GitHub or GitHub Enterprise account to your SSMS keychain, see [Work with GitHub accounts in Visual Studio](/visualstudio/ide/work-with-github-accounts).

## Sign in to your account

When you sign in to SSMS, you can access your Azure account and synchronize your settings across devices.

To add another account, see [Add and switch user accounts in SSMS](#add-and-switch-user-accounts-in-ssms).

1. Launch SSMS. When you open SSMS for the first time, you're prompted to sign in and provide some basic registration information.

   > [!NOTE]  
   > Sign in isn't required to use SSMS. If you choose to not sign in when you first open SSMS, it's easy to do so later. Look for the **Sign in** link in the upper-right corner of the SSMS environment.

1. Choose a Microsoft account or a work or school account. If you don't have one, you can [create a Microsoft account for free](https://support.microsoft.com/help/4026324/).

You can see that you've successfully signed in, in the upper-right corner of the SSMS environment. Unless you sign out, you automatically sign in to SSMS whenever you start it, and any changes to synchronized settings are automatically applied.

### Sign in from the SSMS application

If you choose to not sign in when you first open SSMS, you can sign in later.

1. Select the **Sign in** icon in the upper-right corner of the SSMS environment, and then choose an account to sign into.

1. On the **Sign in** page, select a connected account under **Use one of these accounts**, or select **Use another account** to sign in with another account.

1. Follow the prompts to enter the new account credentials.

## Benefits: why sign in?

While you don't have to sign in, there are many advantages to doing so.

| Benefit | Description |
| --- | --- |
| Auto-connect to Azure | Access to your Azure account in SSMS without being prompted again for credentials for the same account. |

## Add and switch user accounts in SSMS

If you have multiple accounts, you can add them all to SSMS so that you can access the resources from any account without having to sign in to it separately.

After you add multiple accounts on one machine, that group of accounts roams with you if you sign in to SSMS on another machine. However, if your account credentials don't roam, you'll be prompted to enter credentials for those other accounts the first time you attempt to use the resources on a new machine.

To authenticate and access Azure resources from SSMS, sign in to SSMS with an account that has access to Azure resources.

There are several types of accounts you can add:

- Add a standard Azure account:

  1. Select the icon with your profile name in the upper-right corner of the SSMS environment.
  1. Select **Add another account** and then choose an account to sign into.
  1. On the **Sign in** page, select the account or choose **Use another account**.
  1. Follow the prompts to enter the new account credentials.

- Add a [GitHub account](/visualstudio/ide/work-with-github-accounts)

- Add a [Multifactor authentication (MFA) account](/visualstudio/ide/work-with-multi-factor-authentication)

## Remove an account

You can remove any of the accounts you've added to SSMS. When you remove an account, only that specific account is affected and any resources associated with that account are no longer accessible. However, if you select **Sign out**, [all accounts are signed out](#sign-out-of-all-accounts).

1. Select the icon with your profile name in the upper-right corner of your SSMS environment.

1. Select **Account Settings** to view the list of accounts signed in to SSMS.

1. Select **Remove account** for the account you want to remove.

1. Confirm the removal on the dialog that appears.

## Sign out of all accounts

Signing out of SSMS removes all accounts, settings no longer roam across devices, and associated resources aren't accessible anymore.

To sign out of all accounts:

1. Select the icon with your profile name in the upper-right corner of your SSMS environment.

1. Select **Sign out**.

You can also use the **Account Settings** dialog to sign out of all accounts.

## Related content

- [Access multiple accounts in SQL Server Management Studio](sign-in-access-multiple-accounts.md)
- [Work with GitHub accounts in Visual Studio](/visualstudio/ide/work-with-github-accounts)
- [Sign in to Visual Studio with accounts that require multifactor authentication (MFA)](/visualstudio/ide/work-with-multi-factor-authentication)

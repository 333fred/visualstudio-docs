---
title: Sign in 
description: Learn why to sign in to Visual Studio, how to sign in, and how to add and switch user accounts.
ms.custom: "contperf-fy21q1"
ms.date: 05/23/2023
ms.topic: how-to
ms.assetid: b9531c25-e4cf-43ae-b331-a9f31a8cd171
author: anandmeg
ms.author: meghaanand
manager: jmartens
ms.technology: vs-ide-general
ms.workload:
- multiple
---
# Sign in to Visual Studio on Windows 

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]

In this article, you'll learn how to sign in to Visual Studio, add and switch user accounts, update your profile, sign out of your account, and the benefits to signing in.  If you are looking to learn how to use multiple accounts for sign-ins, check out our article, [Access multiple accounts associated with the Visual Studio sign-in account](sign-in-access-multiple-accounts.md).

You can get subscription support and search the frequently asked questions about subscriptions, accounts, and billing [on our Subscription support page](https://visualstudio.microsoft.com/subscriptions/support/).

<a name="sign-in"></a>

## Sign in with a Microsoft or organizational account

::: moniker range="<=vs-2019"

1. Launch Visual Studio. When you open Visual Studio for the first time, you're asked to sign in and provide some basic registration information.

   ![Sign-in prompt](../ide/media/vs2019_signinpopup.png)
   
   > [!NOTE]
   > If you choose not to sign in when you first open Visual Studio, it's easy to do so later. Look for the **Sign in** link in the upper-right corner of the Visual Studio environment.

::: moniker-end

::: moniker range="vs-2022"

1. Launch Visual Studio.  When you open Visual Studio for the first time, you're asked to sign in and provide some basic registration information.

   ![Sign-in prompt](../ide/media/vs-2022/visual-studio-sign-in-pop-up-vs-2022.png)

   > [!NOTE]
   > If you choose not to sign in when you first open Visual Studio, it's easy to do so later. Look for the **Sign in** link in the upper-right corner of the Visual Studio environment.

::: moniker-end

2. Choose a Microsoft account or a work or school account.  If you don't have one, you can [create a Microsoft account for free](https://support.microsoft.com/help/4026324/microsoft-account-how-to-create). 

3. Choose your preferred color theme and other UI settings.  Visual Studio [remembers these settings and synchronizes](../ide/synchronized-settings-in-visual-studio.md) them across all Visual Studio environments you have signed in to. You can change the settings later if you open the **Tools** > **Options** menu in Visual Studio.

You can see that you're successfully signed in the upper-right corner of the Visual Studio environment. Unless you sign out, you're automatically signed in to Visual Studio whenever you start it, and any changes to synchronized settings are automatically applied.

::: moniker range="<=vs-2019"

   ![Currently logged in user in VS2019](../ide/media/vs2019_username.png)

::: moniker-end

::: moniker range="vs-2022"

   ![Currently logged in user in VS2022](../ide/media/vs-2022/visual-studio-sign-in.png)

::: moniker-end

<a name="benefits"></a>
## Benefits: why sign in? 

While you don't have to sign in, there are many advantages to doing so.   

|Benefit|Description|
|---|---|
|[Extend your Visual Studio trial period](../ide/how-to-unlock-visual-studio.md)|Use Visual Studio Professional or Visual Studio Enterprise **for an additional 90 days**, instead of being limited to the trial period of 30 days.|
|[Unlock Visual Studio](../ide/how-to-unlock-visual-studio.md)|Unlock Visual Studio if you use an account that's associated with a [Visual Studio subscription](/visualstudio/subscriptions/using-the-subscriber-portal) or an Azure DevOps organization.|
|[Synchronize](../ide/synchronized-settings-in-visual-studio.md) your settings|Settings that you customize, such as key bindings, window layout, and color theme, apply immediately when you sign in to Visual Studio on any device.|
|Auto-connect to Azure services|Connect to services, such as Azure and Azure DevOps Services, in the IDE without prompting again for credentials for the same account.|
|Use Community edition without interruptions|While it's not required to sign in, you might periodically get prompts to sign-in if you haven't done so. Please sign in to the IDE to continue using Visual Studio Community without interruptions.|
|[Get 'Visual Studio Dev Essentials'](https://visualstudio.microsoft.com/dev-essentials/)|This program includes free software, training, support, and more.|

<a name="profile"></a>

## Update your account profile

1. Go to **File > Account Settings...** and select the **Manage Visual Studio profile** link.
1. In the browser window, select **Edit profile** and change the settings that you want.
1. When you're done, select **Save changes**.

<a name="add-and-switch"></a>

## Add and switch user accounts

If you have multiple Microsoft accounts and/or work or school accounts, you can add them all to Visual Studio so that you can access the resources from any account without having to sign in to it separately.

After you add multiple accounts on one machine, that set of accounts roams with you if you sign in to Visual Studio on another machine.

> [!NOTE]
> Although the account names roam, the credentials do not. You'll be prompted to enter credentials for those other accounts the first time you attempt to use their resources on a new machine.

### Add an additional account to Visual Studio

::: moniker range="<=vs-2019"

To add an additional account to Visual Studio:

1. Choose **File** > **Account Settings**.
1. From **All Accounts**, choose an account by using the **+** or the **Add** dropdown.
1. On the **Sign in to your account** page, select the account or choose **Use another account**. Follow the prompts to enter the new account credentials.

(Optional) Now you use the Add Connected Service dialog and see the Azure services associated with the account you just added. You should see all the services associated with the specified subscription. Even though you're not currently signed into Visual Studio with the second account, you are signed in to that account's services and resources. [Learn more about accessing the resources associated with accounts in Visual Studio](./sign-in-access-multiple-accounts.md).

::: moniker-end

::: moniker range="vs-2022"

To add an additional account to Visual Studio:

1. Select the icon with your profile name in the upper-right corner of the Visual Studio environment.
1. Select **Add another account** and then choose an account to sign into.
1. On the **Sign in to your account** page, select the account or choose **Use another account**. Follow the prompts to enter the new account credentials.

You can also add an additional account from the **Account settings** dialog:

1. Select the icon with your profile name in the upper-right corner of the Visual Studio environment. Then, select **Account settings** to manage your accounts. You can also open the Account Settings dialog by going to **File** > **Account Settings...**.
1. From **All Accounts**, choose an account by using the **+ Add** dropdown.
1. On the **Sign in to your account** page, select the account or choose **Use another account**. Follow the prompts to enter the new account credentials.

::: moniker-end

### Add a GitHub account to Visual Studio

::: moniker range="<=vs-2019"

Starting with Visual Studio 2019 version 16.8, you’ll be able to add both GitHub and GitHub Enterprise accounts to your keychain. You’ll be able to add and leverage them just as you do with Microsoft accounts, which means that you’ll have an easier time accessing your GitHub resources across Visual Studio.

::: moniker-end

::: moniker range="vs-2022"

You can add both GitHub and GitHub Enterprise accounts to your keychain. You can add and leverage them just as you do with Microsoft accounts, enabling you to easily access your GitHub resources across Visual Studio.

::: moniker-end

For detailed instructions, see [Work with GitHub accounts in Visual Studio](work-with-github-accounts.md).

### Add a multi-factor authentication (MFA) enabled account to Visual Studio

::: moniker range="<=vs-2019"

Starting with Visual Studio 2019 version 16.6, users can access resources secured via CA policies such as MFA. To use this enhanced workflow, you'll need to opt into using your system's default web browser as the mechanism to add and reauthenticate Visual Studio accounts.  For detailed instructions, see [Work with accounts that require multi-factor authentication (MFA)](work-with-multi-factor-authentication.md)

::: moniker-end

::: moniker range="vs-2022"

You can also access resources secured via CA policies such as MFA. To use this enhanced workflow, you'll need to opt into using your system's default web browser as the mechanism to add and reauthenticate Visual Studio accounts.  For detailed instructions, see [Work with accounts that require multi-factor authentication (MFA)](work-with-multi-factor-authentication.md)

::: moniker-end

## Sign out of your account

::: moniker range="<=vs-2019"

1. Select the icon with your profile name in the upper-right corner of the Visual Studio environment.
1. Select **Account settings....**.
1. Select **Sign out**.

::: moniker-end

::: moniker range="vs-2022"

Select the icon with your profile name in the upper-right corner of the Visual Studio environment and then select **Sign out**.

:::image type="content" source="../ide/media/vs-2022/visual-studio-profile-sign-out.png" alt-text="Screenshot showing Visual Studio sign out option":::

You can also sign out by using the Account settings dialog. Select **Account settings** and then select **Sign out**. You can also open the Account Settings dialog by going to **File** > **Account Settings...**.

:::image type="content" source="../ide/media/vs-2022/visual-studio-sign-out-vs-2022.png" alt-text="Screenshot showing Visual Studio sign out on Account Settings dialog.":::

::: moniker-end

---
title: "Team Foundation Version Control (TFVC)"
description: "Connecting from Visual Studio for Mac to Team Foundation Server/Azure DevOps with Team Foundation Version Control (TFVC)."
author: jmatthiesen
ms.author: jomatthi
ms.date: 06/25/2019
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
---

# Connecting to Team Foundation Version Control

> [!NOTE]
> For the best version control experience on macOS, we recommend using Git instead of Team Foundation Version Control (TFVC). 
Git is supported in Visual Studio for Mac and is the default option for repositories hosted in Team Foundation Server (TFS)/Azure DevOps. To learn more about using Git with TFS/Azure DevOps, see the [Setting up a Git Repository](/visualstudio/mac/set-up-git-repository) article.
> 
> If you previously used the preview release of the TFVC extension for Visual Studio for Mac, it is no longer supported in Visual Studio 2019 for Mac.

Azure Repos provides two models of version control: [Git](/azure/devops/repos/git/?view=azure-devops), a distributed version control system, and [Team Foundation Version Control](/azure/devops/repos/tfvc/index?view=azure-devops) (TFVC), a centralized version control system.

Visual Studio for Mac provides full support for Git repositories, but requires some workarounds to work with TFVC. If you're using TFVC for version control today, here are some solutions you can use to access your source code hosted in TFVC:

* [Use Visual Studio Code and the Azure Repos extension, for a graphical UI](#use-visual-studio-code-and-the-azure-repos-extension)
* [Connect to your repo using the Team Explorer Everywhere Command Line Client (TEE-CLC)](#connecting-using-the-team-explorer-everywhere-command-line-client)

The rest of this article walks you through the options listed above.

## Requirements

* Visual Studio Community, Professional, or Enterprise for Mac version 7.8 and later.
* Azure DevOps Services, Team Foundation Server 2013 and later, or Azure DevOps Server 2018 and later.
* A project in Azure DevOps Services or Team Foundation Server/Azure DevOps Server, configured to use Team Foundation Version Control.

## Use Visual Studio Code and the Azure Repos extension

If you like to work with a graphical interface to manage your files in version control, then the Azure Repos extension for Visual Studio Code provides a supported solution from Microsoft. To get started, download [Visual Studio Code](https://code.visualstudio.com) and then learn how to [configure the Azure Repos extension](https://marketplace.visualstudio.com/items?itemName=ms-vsts.team).

## Connecting using the Team Explorer Everywhere Command Line Client

If you're comfortable using the macOS Terminal, then the Team Explorer Everywhere Command Line Client (TEE-CLC) provides a supported way to connect to your source in TFVC.

You can follow the steps below to set up your connection to TFVC and commit changes.

### Setting up the TEE-CLC

There are two ways to get setup with the TEE-CLC.

* Use Homebrew to install the client, or
* Download and manually install the client

The easiest solution is **using HomeBrew**, which is a package manager for macOS. To install using this method:

1. Launch the macOS Terminal application.
1. Install Homebrew using the Terminal and the instructions on the [Homebrew home page](https://brew.sh/).
1. Once Homebrew is installed, run the following command from your Terminal: `brew install tee-clc`

To **setup the TEE-CLC manually**:

1. [Download the latest version of the tee-clc](https://github.com/Microsoft/team-explorer-everywhere/releases) from the releases page of the Team Explorer Everywhere GitHub repo (e.g. tee-clc-14.134.0.zip at the time of this writing).
1. Extract the content of the .zip to a folder on disk.
1. Open the macOS Terminal app and use the `cd` command to switch to the folder you used in the previous step.
1. From within the folder, run the command `./tf` to test that the command line client can run, you may be prompted to install Java or other dependencies.

Once the TEE-CLC is installed, you can run the command `tf eula` to view and accept the license agreement for the client.

Finally, to authenticate with your TFS/Azure DevOps environment, you'll need to create a personal access token on the server. Learn more about [authenticating with personal access tokens](https://docs.microsoft.com/azure/devops/integrate/get-started/authentication/pats?view=azure-devops). When creating a personal access token to use with TFVC, be sure to provide Full Access when configuring the token.

### Using the TEE-CLC to connect to your repo

To connect to your source code, you first need to create a workspace using the `tf workspace` command. For example, the following commands connect to an Organization in Azure DevOps Services called "MyOrganization": 

```bash
export TF_AUTO_SAVE_CREDENTIALS=1
tf workspace -new MyWorkspace -collection:https://dev.azure.com/MyOrganization
```

The `TF_AUTO_SAVE_CREDENTIALS` environment setting is used to save your credentials so you aren't prompted to enter them multiple times. When prompted for a user name, use the personal access token you created in the previous section and use a blank password.

To create a mapping of your source files to a local folder, you'll use the `tf workfold` command. The following example will map a folder named "WebApp.Services" from the "MyRepository" TFVC project and set it up to be copied into the local ~/Projects/ folder (i.e. a "Projects" folder in the current users's home folder).

```bash
tf workfold -map $/MyRepository/WebApp.Services -workspace:MyWorkspace ~/Projects/
```

Finally, you use the following command to get the source files from the server and copy them locally:

```bash
tf get
```

### Committing changes using the TEE-CLC

After you've made changes to your files in Visual Studio for Mac, you can switch back to the Terminal to check in your edits. The `tf add` command is used to add files to the list of pending changes to be checked-in and the `tf checkin` command performs the actual check-in to the server. The `checkin` command includes parameters to add a comment or associate a related work item. In the following code snippet, all files in a `WebApp.Services` folder are added, recursively, to the checkin. Then, the code is checked in with a comment and associated with a work item with the ID "42".

```bash
cd WebApp.Services
tf add * /recursive
tf checkin -comment:"Replaced 'Northwand' typos with the correct word Northwind" -associate:42
```

To learn more about the commands mentioned here, or others, you can use the following command from the Terminal:

`tf help`

### See also

- [Develop and share your code in TFVC using Visual Studio (on Windows)](/azure/devops/repos/tfvc/share-your-code-in-tfvc-vs)
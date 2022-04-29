---
title: Get the tools
description: A list of tools you need to write Visual Studio extensions and how to install them.
ms.date: 12/01/2021
ms.topic: conceptual
author: madskristensen
ms.author: madsk
manager: pchapman
ms.prod: visual-studio-windows
ms.technology: vs-ide-sdk
ms.custom: cookbook
---
# Get the tools needed to write Visual Studio extensions

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-not-mac.md)]

To write extensions you have to install the extensibility workload. That's technically all you need, but this set of documentation makes use of the community driven extension called *Extensibility Essentials*. Each version of Visual Studio has its own version: [Extensibility Essentials 2019](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.ExtensibilityEssentials2019) or [Extensibility Essentials 2022](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.ExtensibilityEssentials2022).

The following video introduces the tools you'll need.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWPhtT]

## Install extensibility workload

To open the **Visual Studio Installer**, choose **Tools**, and then choose **Get Tools and Features...**. Then install the **Visual Studio extension development** workload.

:::image type="content" source="../media/visual-studio-installer.png" alt-text="VS Installer showing the extensibility workload.":::

## Install Extensibility Essentials
To install the **Extensibility Essentials**, choose **Extensions**, choose **Manage Extensions** and then search for *extensibility*.

* For Visual Studio 2019 install [Extensibility Essentials 2019](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.ExtensibilityEssentials2019).
* For Visual Studio 2022 install [Extensibility Essentials 2022](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.ExtensibilityEssentials2022).

:::image type="content" source="../media/install-extensibility-essentials.png" alt-text="Install Extensibility Essentials from the Extension Manager dialog.":::

That's it, you are now ready to start developing [your first extension](first-extension.md).

---
title: "Create custom views of .NET objects | Microsoft Docs"
description: Visual Studio debugger displays data in its variable windows. Learn to customize how data types—including custom types—are displayed. 
ms.date: "08/08/2023"
ms.topic: "conceptual"
f1_keywords:
  - "vs.debug.data.elements"
dev_langs:
  - "CSharp"
  - "VB"
  - "FSharp"
  - "C++"
helpviewer_keywords:
  - "data types, custom"
  - "custom data types"
  - "managed code, custom data types"
  - "autoexp.dat file"
  - "mcee_cs.dat file"
  - "debugger, expanding data types"
  - "mcee_mc.dat file"
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: "mikejo5000"
ms.author: "mikejo"
manager: jmartens
ms.technology: vs-ide-debug
ms.workload:
  - "dotnet"
---
# Create custom views of .NET objects (C#, Visual Basic, F#, C++/CLI)

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
You can customize the way Visual Studio displays data types in debugger variable windows.

## Attributes

In C#, Visual Basic, F#, and C++ (C++/CLI code only), you can add expansions for custom data using <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, and <xref:System.Diagnostics.DebuggerBrowsableAttribute>.

In .NET Framework 2.0 code, Visual Basic does not support the DebuggerBrowsable attribute. This limitation is removed in more recent versions of .NET.

## Visualizers

You can write a visualizer to display any managed data type. For more information, see [Custom visualizers](create-custom-visualizers-of-data.md).

> [!NOTE]
> For C++ code, you can add custom data type expansions using the Natvis framework, as described in [Create custom views of C++ objects in the debugger](create-custom-views-of-native-objects.md).

## See also

- [Tell the debugger what to show using the DebuggerDisplay Attribute](../debugger/using-the-debuggerdisplay-attribute.md)
- [Tell the debugger what type to show using DebuggerTypeProxy Attribute](../debugger/using-debuggertypeproxy-attribute.md)
- [Watch and QuickWatch Windows](../debugger/watch-and-quickwatch-windows.md)
- [Enhancing Debugging with the Debugger Display Attributes](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)

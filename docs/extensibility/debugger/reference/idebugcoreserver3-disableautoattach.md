---
description: "Disables automatic attaching for all debug engines associated with this server."
title: IDebugCoreServer3::DisableAutoAttach
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugCoreServer3::DisableAutoAttach
helpviewer_keywords:
- IDebugCoreServer3::DisableAutoAttach
author: maiak
ms.author: maiak
manager: jmartens
ms.subservice: vs-ide-debug
dev_langs:
- CPP
- CSharp
---
# IDebugCoreServer3::DisableAutoAttach

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
Disables automatic attaching for all debug engines associated with this server.

## Syntax

### [C#](#tab/csharp)
```csharp
int DisableAutoAttach();
```
### [C++](#tab/cpp)
```cpp
HRESULT DisableAutoAttach(
   void
);
```
---

## Return Value
 If successful, returns `S_OK`; otherwise, returns error code.

## See also
- [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)

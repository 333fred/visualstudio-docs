---
description: "Retrieves a flag that specifies whether the user-defined data type is nested."
title: "IDiaSymbol::get_nested"
ms.date: "11/04/2016"
ms.topic: "reference"
dev_langs:
  - "C++"
helpviewer_keywords:
  - "IDiaSymbol::get_nested method"
author: "mikejo5000"
ms.author: "mikejo"
manager: jmartens
ms.technology: vs-ide-debug
---
# IDiaSymbol::get_nested

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
Retrieves a flag that specifies whether the user-defined data type is nested.

## Syntax

```C++
HRESULT get_nested ( 
   BOOL* pRetVal
);
```

#### Parameters
 `pRetVal`

[out] Returns `TRUE` if the user-defined data type is nested; otherwise, returns `FALSE`.

## Return Value
 If successful, returns `S_OK`; otherwise, returns `S_FALSE` or an error code.

> [!NOTE]
> A return value of `S_FALSE` means that the property is not available for the symbol.

## See also
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)

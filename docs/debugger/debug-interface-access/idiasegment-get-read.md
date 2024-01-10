---
description: "Retrieves a flag that indicates whether the segment can be read."
title: "IDiaSegment::get_read"
ms.date: "11/04/2016"
ms.topic: "reference"
dev_langs:
  - "C++"
helpviewer_keywords:
  - "IDiaSegment::get_read method"
author: "mikejo5000"
ms.author: "mikejo"
manager: jmartens
ms.subservice: vs-ide-debug
---
# IDiaSegment::get_read

 [!INCLUDE [Visual Studio](~/includes/applies-to-version/vs-windows-only.md)]
Retrieves a flag that indicates whether the segment can be read.

## Syntax

```C++
HRESULT get_read ( 
   BOOL* pRetVal
);
```

#### Parameters
 `pRetVal`

[out] Returns `TRUE` if the segment can be read; otherwise, returns `FALSE`.

## Return Value
 If successful, returns `S_OK`. Returns `S_FALSE` if this property is not supported. Otherwise, returns an error code.

## See also
- [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)

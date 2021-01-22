---
description: '了解详细信息：延迟加载异常 (C/c + +) '
title: DLL 延迟加载异常代码
ms.date: 01/19/2021
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.openlocfilehash: 214d8514baba7b180b8d838af8a6b6c0543cc1ce
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667190"
---
# <a name="dll-delay-load-exception-codes"></a>DLL 延迟加载异常代码

发生故障时，可以引发两个结构化异常代码：

- 对于 `LoadLibrary` 失败

- 对于 `GetProcAddress` 失败

下面是异常信息宏：

```C
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

引发的异常代码为标准 `VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND)` 值和 `VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)` 值。 此异常在字段中传递一个指针，该指针指向 `DelayLoadInfo` `LPDWORD` 可以在结构中检索的值中的结构 `GetExceptionInformation` [`EXCEPTION_RECORD`](/windows/win32/api/winnt/ns-winnt-exception_record) `ExceptionInformation[0]` 。

此外，如果在字段中设置了不正确的位 `grAttrs` ，则 `ERROR_INVALID_PARAMETER` 会引发异常。 此例外是出于所有意图和目的，都是致命的。

有关详细信息，请参阅 [结构和常量定义](structure-and-constant-definitions.md)。

## <a name="see-also"></a>另请参阅

[错误处理和通知](error-handling-and-notification.md)

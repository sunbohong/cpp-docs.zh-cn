---
description: 了解详细信息： _local_unwind2
title: _local_unwind2
ms.date: 1/14/2021
api_name:
- _local_unwind2
api_location:
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _local_unwind2
- local_unwind2
helpviewer_keywords:
- _local_unwind2 function
- local_unwind2 function
ms.assetid: 44f1fa82-e01e-490f-a6e6-18fc6811c28c
ms.openlocfilehash: cb137547c44eb6d6516086a06109a9339247699c
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243055"
---
# <a name="_local_unwind2"></a>_local_unwind2

内部 CRT 函数。 运行在指示的范围表中列出的所有终止处理程序。

## <a name="syntax"></a>语法

```cpp
void _local_unwind2(
   PEXCEPTION_REGISTRATION xr,
   int stop
);
```

#### <a name="parameters"></a>参数

*xr*<br/>
[in] 与一个范围表相关联的注册记录。

*stop*<br/>
[in] 指示应停止 `_local_unwind2` 的位置的词法级别。

## <a name="remarks"></a>注解

此方法仅可由运行时环境使用。 请不要在代码中调用该方法。

当此方法执行终止处理程序时，它将从当前词汇级别开始，并按自己的方式运行到更高的词汇级别，直到它达到由 `stop` 指示的级别。 它不会在由 `stop` 指示的级别上执行终止处理程序。

## <a name="see-also"></a>另请参阅

[字母函数引用](../c-runtime-library/reference/crt-alphabetical-function-reference.md)

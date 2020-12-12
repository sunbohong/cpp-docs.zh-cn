---
description: 了解详细信息： _setjmp3
title: _setjmp3
ms.date: 11/04/2016
api_name:
- _setjmp3
api_location:
- msvcrt.dll
- msvcr90.dll
- msvcr110.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr120.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp3
- _setjmp3
helpviewer_keywords:
- _setjmp3 function
- setjmp3 function
ms.assetid: 6129c2f3-8bac-4fdb-a827-44e1eebba500
ms.openlocfilehash: 07a84601a6f57eca3e7dc71638a964428579b1c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277058"
---
# <a name="_setjmp3"></a>_setjmp3

内部 CRT 函数。 `setjmp` 函数的新实现。

## <a name="syntax"></a>语法

```
int _setjmp3(
   OUT jmp_buf env,
   int count,
   (optional parameters)
);
```

#### <a name="parameters"></a>parameters

*env*<br/>
[out] 用于存储状态信息的缓冲区地址。

*计数*<br/>
[in] 存储在 `optional parameters` 中的信息的附加 `DWORD` 数。

*可选参数*<br/>
[in] 由 `setjmp` 内部函数向下推送的其他数据。 第一个 `DWORD` 是一个用于展开多余数据并返回到永久性注册状态的函数指针。 第二个 `DWORD` 是要还原的尝试级别。 之后的所有数据都将保存在 `jmp_buf` 的通用数据数组中。

## <a name="return-value"></a>返回值

始终返回 0。

## <a name="remarks"></a>备注

请不要在 C++ 程序中使用此函数。 它是一个不支持 C++ 的内部函数。 有关如何使用 `setjmp` 的详细信息，请参阅[使用 setjmp/longjmp](../cpp/using-setjmp-longjmp.md)。

## <a name="requirements"></a>要求

## <a name="see-also"></a>另请参阅

[字母函数引用](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[setjmp](../c-runtime-library/reference/setjmp.md)

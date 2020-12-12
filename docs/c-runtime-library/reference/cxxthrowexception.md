---
description: 了解详细信息： _CxxThrowException
title: _CxxThrowException
ms.date: 11/04/2016
api_name:
- _CxxThrowException
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CxxThrowException
- _CxxThrowException
helpviewer_keywords:
- _CxxThrowException function
- CxxThrowException function
ms.assetid: 0b90bef5-b7d2-46e0-88e2-59e531e01a4d
ms.openlocfilehash: df4b1b30ba70ebf34bdb3cb4ae1c51a210f95a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327029"
---
# <a name="_cxxthrowexception"></a>_CxxThrowException

生成异常记录并调用运行时环境以开始处理异常。

## <a name="syntax"></a>语法

```C
extern "C" void __stdcall _CxxThrowException(
   void* pExceptionObject
   _ThrowInfo* pThrowInfo
);
```

### <a name="parameters"></a>parameters

*pExceptionObject*<br/>
生成异常的对象。

*pThrowInfo*<br/>
处理异常所需的信息。

## <a name="remarks"></a>备注

此方法包含在编译器用来处理异常的仅编译器文件中。 不要直接从代码调用方法。

## <a name="requirements"></a>要求

**源：** Throw.cpp

## <a name="see-also"></a>请参阅

[字母函数引用](crt-alphabetical-function-reference.md)<br/>

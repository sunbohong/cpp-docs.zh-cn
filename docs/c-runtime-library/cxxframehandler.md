---
description: 了解详细信息： __CxxFrameHandler
title: __CxxFrameHandler
ms.date: 1/14/2021
api_name:
- __CxxFrameHandler
api_location:
- msvcr110.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __CxxFrameHandler
helpviewer_keywords:
- __CxxFrameHandler
ms.assetid: b79ac97f-425a-42ae-9b91-8beaef935333
ms.openlocfilehash: 0bf82b3a247505d052f1d64edc63bb9cd76a1dcb
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243185"
---
# <a name="__cxxframehandler"></a>__CxxFrameHandler

内部 CRT 函数。 由 CRT 用于处理结构化异常帧。

## <a name="syntax"></a>语法

```cpp
EXCEPTION_DISPOSITION __CxxFrameHandler(
      EHExceptionRecord  *pExcept,
      EHRegistrationNode *pRN,
      void               *pContext,
      DispatcherContext  *pDC
   )
```

#### <a name="parameters"></a>参数

*pExcept*<br/>
传递给可能的语句的异常记录 **`catch`** 。

*.Prn*<br/>
有关用于处理异常的堆栈帧的动态信息。 有关详细信息，请参阅 ehdata.h。

*pContext*<br/>
上下文。 （不可用于 Intel 处理器上。）

*pDC*<br/>
有关函数入口和堆栈帧的其他信息。

## <a name="return-value"></a>返回值

由 [try-except 语句](../cpp/try-except-statement.md)使用的 filter expression 值之一。

## <a name="remarks"></a>备注

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|__CxxFrameHandler|excpt.h，ehdata.h|

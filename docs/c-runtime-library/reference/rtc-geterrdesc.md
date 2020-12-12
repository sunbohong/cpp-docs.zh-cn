---
description: 了解详细信息： _RTC_GetErrDesc
title: _RTC_GetErrDesc
ms.date: 11/04/2016
api_name:
- _RTC_GetErrDesc
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
- RTC_GetErrDesc
- _RTC_GetErrDesc
helpviewer_keywords:
- run-time errors
- _RTC_GetErrDesc function
- RTC_GetErrDesc function
ms.assetid: 7994ec2b-5488-4fd4-806d-a166c9a9f927
ms.openlocfilehash: 5e9beccec5e13d6c2c00e3edaefec695a8e16737
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168717"
---
# <a name="_rtc_geterrdesc"></a>_RTC_GetErrDesc

返回运行时错误检查 (RTC) 类型的简要描述。

## <a name="syntax"></a>语法

```C
const char * _RTC_GetErrDesc(
   _RTC_ErrorNumber errnum
);
```

### <a name="parameters"></a>parameters

*errnum*<br/>
一个数字，介于 0 和 **_RTC_NumErrors** 返回的值减 1 所得的值之间。

## <a name="return-value"></a>返回值

一个字符串，其中包含由运行时错误检查系统检测到的一个错误类型的简短描述。 如果错误小于零或大于等于 [_RTC_NumErrors](rtc-numerrors.md)返回的值，则 **_RTC_GetErrDesc** 返回 **NULL**。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_RTC_GetErrDesc**|\<rtcapi.h>|

有关详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

[C 运行时库](../../c-runtime-library/crt-library-features.md)的所有版本。

## <a name="see-also"></a>请参阅

[_RTC_NumErrors](rtc-numerrors.md)<br/>
[运行时错误检查](../../c-runtime-library/run-time-error-checking.md)<br/>

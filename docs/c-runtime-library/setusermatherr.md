---
description: 了解详细信息： __setusermatherr
title: __setusermatherr
ms.date: 11/04/2016
api_name:
- __setusermatherr
api_location:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __setusermatherr
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
ms.openlocfilehash: 11b470f3c39a22b212187936dc4bad36c3cefd1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277071"
---
# <a name="__setusermatherr"></a>__setusermatherr

指定用户提供的例程（而不是 [_matherr](../c-runtime-library/reference/matherr.md) 例程）处理数学错误。

## <a name="syntax"></a>语法

```cpp
void __setusermatherr(
   _HANDLE_MATH_ERROR pf
   )
```

#### <a name="parameters"></a>parameters

*pf*<br/>
指向用户提供的 `_matherr` 的实现的指针。

将 *pf* 参数的类型声明为 `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`。

## <a name="remarks"></a>备注

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|__setusermatherr|matherr.c|

---
description: 了解详细信息： __set_app_type
title: __set_app_type
ms.date: 11/04/2016
api_name:
- __set_app_type
- _set_app_type
api_location:
- msvcr90.dll
- msvcr100.dll
- msvcr110.dll
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __set_app_type
helpviewer_keywords:
- __set_app_type
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
ms.openlocfilehash: 19aafebc4f7fd848804e21193332fb693af56010
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97246744"
---
# <a name="__set_app_type"></a>__set_app_type

设置当前应用程序类型。

## <a name="syntax"></a>语法

```cpp
void __set_app_type (
   int at
   )
```

#### <a name="parameters"></a>parameters

*at*<br/>
表示应用程序类型的值。 可能的值为：

|值|描述|
|-----------|-----------------|
|_UNKNOWN_APP|未知应用程序类型。|
|_CONSOLE_APP|控制台（命令行）应用程序。|
|_GUI_APP|GUI (Windows) 应用程序。|

## <a name="remarks"></a>备注

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|__set_app_type|internal.h|

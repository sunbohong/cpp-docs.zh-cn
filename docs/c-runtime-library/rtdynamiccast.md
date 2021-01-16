---
description: 了解详细信息： __RTDynamicCast
title: __RTDynamicCast
ms.date: 1/14/2021
api_name:
- __RTDynamicCast
api_location:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: cefd5248e0409b72f97c959d08aa30b1c0167e26
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243107"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

[dynamic_cast](../cpp/dynamic-cast-operator.md) 运算符的运行时实现。

## <a name="syntax"></a>语法

```cpp
PVOID __RTDynamicCast (
   PVOID inptr,
   LONG VfDelta,
   PVOID SrcType,
   PVOID TargetType,
   BOOL isReference
   ) throw(...)
```

#### <a name="parameters"></a>参数

*inptr*<br/>
指向多态对象的指针。

*VfDelta*<br/>
对象中的虚函数指针的偏移量。

*SrcType*<br/>
由 `inptr` 参数指向的对象的静态类型。

*TargetType*<br/>
转换的预期结果。

*isReference*<br/>
**`true`** 如果输入是引用，则为; **`false`** 如果输入是指针，则为。

## <a name="return-value"></a>返回值

如果成功，则为指向相应子对象的指针;否则 **为 NULL**。

## <a name="exceptions"></a>例外

如果 `bad_cast()` 的输入为引用并且转换失败，则为 `dynamic_cast<>`。

## <a name="remarks"></a>注解

将 `inptr` 转换为 `TargetType` 类型的对象。 如果 `TargetType` 是指针，则 `inptr` 类型必须为指针，或者如果 `TargetType` 是引用，则为左值。 `TargetType` 必须是针对以前定义的类类型的指针或引用，或者是指向 void 的指针。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|

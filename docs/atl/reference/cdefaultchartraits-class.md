---
description: 了解详细信息： CDefaultCharTraits 类
title: CDefaultCharTraits 类
ms.date: 11/04/2016
f1_keywords:
- CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits
- ATLCOLL/ATL::CDefaultCharTraits::CharToLower
- ATLCOLL/ATL::CDefaultCharTraits::CharToUpper
helpviewer_keywords:
- CDefaultCharTraits class
ms.assetid: f94a3934-597f-401d-8513-ed6924ae069a
ms.openlocfilehash: 6d98c6b6ffb527fef1e5b2320b46eda61ec3f670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141955"
---
# <a name="cdefaultchartraits-class"></a>CDefaultCharTraits 类

此类提供两个用于在大写和小写之间转换字符的静态函数。

## <a name="syntax"></a>语法

```
template <typename T>
class CDefaultCharTraits
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDefaultCharTraits::CharToLower](#chartolower)| (Static) 调用此函数将字符转换为大写。|
|[CDefaultCharTraits::CharToUpper](#chartoupper)| (Static) 调用此函数将字符转换为小写。|

## <a name="remarks"></a>备注

此类提供类 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)使用的函数。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cdefaultchartraitschartolower"></a><a name="chartolower"></a> CDefaultCharTraits::CharToLower

调用此函数可将字符转换为小写。

```
static wchar_t CharToLower(wchar_t x);
static char CharToLower(char x);
```

### <a name="parameters"></a>parameters

*x*<br/>
要转换为小写的字符。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#132](../../atl/codesnippet/cpp/cdefaultchartraits-class_1.cpp)]

## <a name="cdefaultchartraitschartoupper"></a><a name="chartoupper"></a> CDefaultCharTraits::CharToUpper

调用此函数可将字符转换为大写。

```
static wchar_t CharToUpper(wchar_t x);
static char CharToUpper(char x);
```

### <a name="parameters"></a>parameters

*x*<br/>
要转换为大写的字符。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

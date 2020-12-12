---
description: 了解详细信息： CSimpleMapEqualHelper 类
title: CSimpleMapEqualHelper 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
ms.openlocfilehash: 2b8ff742bf24b6c6c4354cef652e3fc697ffb1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140603"
---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper 类

此类是 [CSimpleMap](../../atl/reference/csimplemap-class.md) 类的帮助器。

## <a name="syntax"></a>语法

```
template <class TKey, class TVal>
class CSimpleMapEqualHelper
```

#### <a name="parameters"></a>parameters

*TKey*<br/>
Key 元素。

*TVal*<br/>
值元素。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)| (静态) 测试两个键是否相等。|
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)| (静态) 测试两个值是否相等。|

## <a name="remarks"></a>备注

此特征类是对类的补充 `CSimpleMap` 。 它提供了一些方法，用于比较两个 `CSimpleMap` 对象元素 (具体说来，键和值组件) 相等。 默认情况下，使用 **operator = = ( # B1** 来比较键和值，但如果映射包含缺少自己的相等运算符的复杂数据类型，则可以重写此类以提供额外的所需功能。

## <a name="requirements"></a>要求

**标头：** atlsimpcoll

## <a name="csimplemapequalhelperisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelper::IsEqualKey

测试两个键是否相等。

```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```

### <a name="parameters"></a>parameters

*k1*<br/>
第一个键。

*k2*<br/>
第二个键。

### <a name="return-value"></a>返回值

如果键相等，则返回 true，否则返回 false。

## <a name="csimplemapequalhelperisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelper::IsEqualValue

测试两个值是否相等。

```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```

### <a name="parameters"></a>parameters

*v1*<br/>
第一个值。

*v2*<br/>
第二个值。

### <a name="return-value"></a>返回值

如果值相等，则返回 true，否则返回 false。

## <a name="see-also"></a>请参阅

[CSimpleMapEqualHelperFalse 类](../../atl/reference/csimplemapequalhelperfalse-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

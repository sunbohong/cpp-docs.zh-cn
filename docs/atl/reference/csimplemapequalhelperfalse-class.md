---
description: 了解详细信息： CSimpleMapEqualHelperFalse 类
title: CSimpleMapEqualHelperFalse 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
ms.openlocfilehash: 5bad8232dc1a96fc743a3526acdb86b839601d9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140577"
---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse 类

此类是 [CSimpleMap](../../atl/reference/csimplemap-class.md) 类的帮助器。

## <a name="syntax"></a>语法

```
template <class TKey, class TVal>
class CSimpleMapEqualHelperFalse
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)| (静态) 测试两个键是否相等。|
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)| (Static) 返回 false。|

## <a name="remarks"></a>备注

此特征类是对类的补充 `CSimpleMap` 。 它提供了一种方法，用于比较对象中包含的两个元素 `CSimpleMap` ，尤其是两个值元素或两个关键元素。

值比较将始终返回 false，此外， `ATLASSERT` 如果曾引用参数，则将使用参数 false 调用。 在未充分定义相等性测试的情况下，此类允许包含键/值对的映射对大多数方法正确运行，但对于依赖于比较（如 [CSimpleMap：： FindVal](../../atl/reference/csimplemap-class.md#findval)）的方法，这些方法会以定义完善的方式进行。

## <a name="requirements"></a>要求

**标头：** atlsimpcoll

## <a name="csimplemapequalhelperfalseisequalkey"></a><a name="isequalkey"></a> CSimpleMapEqualHelperFalse::IsEqualKey

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

### <a name="remarks"></a>备注

此方法调用 [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)。

## <a name="csimplemapequalhelperfalseisequalvalue"></a><a name="isequalvalue"></a> CSimpleMapEqualHelperFalse::IsEqualValue

返回 false。

```
static bool IsEqualValue(const TVal&, const TVal&);
```

### <a name="return-value"></a>返回值

返回 false。

### <a name="remarks"></a>备注

此方法始终返回 false，并将 `ATLASSERT` 使用参数 false （如果曾引用它）调用。 的目的 `CSimpleMapEqualHelperFalse::IsEqualValue` 是在没有充分定义相等性测试的情况时使用比较来强制使用比较来失败。

## <a name="see-also"></a>请参阅

[CSimpleMapEqualHelper 类](../../atl/reference/csimplemapequalhelper-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

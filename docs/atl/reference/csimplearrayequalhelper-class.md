---
description: 了解详细信息： CSimpleArrayEqualHelper 类
title: CSimpleArrayEqualHelper 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e1a5fd3eea5fd6ef7563febc662c5a7a1bc639c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140759"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper 类

此类是 [CSimpleArray](../../atl/reference/csimplearray-class.md) 类的帮助器。

## <a name="syntax"></a>语法

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生类。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleArrayEqualHelper：： IsEqual](#isequal)| (静态) 测试两个 `CSimpleArray` 对象元素是否相等。|

## <a name="remarks"></a>备注

此特征类是对类的补充 `CSimpleArray` 。 它提供了一种方法，用于比较存储在对象中的两个元素 `CSimpleArray` 。 默认情况下，使用 **operator = ( # B1** 比较元素，但如果数组包含缺少其自己的相等运算符的复杂数据类型，将需要重写此类。

## <a name="requirements"></a>要求

**标头：** atlsimpcoll

## <a name="csimplearrayequalhelperisequal"></a><a name="isequal"></a> CSimpleArrayEqualHelper：： IsEqual

测试两个 `CSimpleArray` 对象元素是否相等。

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>parameters

*t1*<br/>
一个 T 类型的对象。

<bpt id="p1">*</bpt>t2<ept id="p1">*</ept><br/>
一个 T 类型的对象。

### <a name="return-value"></a>返回值

如果元素相等，则返回 true，否则返回 false。

## <a name="see-also"></a>请参阅

[CSimpleArray 类](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse 类](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

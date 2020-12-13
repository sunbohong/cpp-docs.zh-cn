---
description: 了解详细信息： CElementTraits 类
title: CElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CElementTraits
- atlcoll/ATL::CElementTraits
helpviewer_keywords:
- CElementTraits class
ms.assetid: 496528e5-7f80-4b45-be0c-6f646feb43c5
ms.openlocfilehash: 1bcb6c9da2bca733efe68b634eebd7f379ba0d10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141799"
---
# <a name="celementtraits-class"></a>CElementTraits 类

集合类使用此类为移动、复制、比较和哈希操作提供方法和函数。

## <a name="syntax"></a>语法

```
template<typename T>
class CElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="remarks"></a>备注

此类提供了用于移动、复制、比较和哈希集合类对象中存储的元素的默认静态函数和方法。 `CElementTraits` 由集合类 [CAtlArray](../../atl/reference/catlarray-class.md)、 [CAtlList](../../atl/reference/catllist-class.md)、 [CRBMap](../../atl/reference/crbmap-class.md)、 [CRBMultiMap](../../atl/reference/crbmultimap-class.md)和 [CRBTree](../../atl/reference/crbtree-class.md)指定为这些操作的默认提供程序。

默认实现适用于简单数据类型，但如果集合类用于存储更复杂的对象，则必须由用户提供的实现重写这些函数和方法。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

---
description: 了解详细信息： CDefaultElementTraits 类
title: CDefaultElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CDefaultElementTraits
- atlcoll/ATL::CDefaultElementTraits
helpviewer_keywords:
- CDefaultElementTraits class
ms.assetid: ac5ee610-7957-4b7c-92b6-38ff72e4118e
ms.openlocfilehash: f4dd1bae67ef626ef793ecee946d88879a07f194
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141890"
---
# <a name="cdefaultelementtraits-class"></a>CDefaultElementTraits 类

此类提供集合类的默认方法和函数。

## <a name="syntax"></a>语法

```
template <typename T>
class CDefaultElementTraits : public CElementTraitsBase<T>,
    public CDefaultHashTraits<T>,
    public CDefaultCompareTraits<T>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="remarks"></a>备注

此类提供了用于移动、复制、比较和哈希集合类对象中存储的元素的默认静态函数和方法。 此类从 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)、 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)和 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)派生其函数和方法，并由 [CElementTraits](../../atl/reference/celementtraits-class.md)、 [CPrimitiveElementTraits](../../atl/reference/cprimitiveelementtraits-class.md)和 [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md)使用。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

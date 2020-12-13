---
description: 了解详细信息： CDefaultHashTraits 类
title: CDefaultHashTraits 类
ms.date: 11/04/2016
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
ms.openlocfilehash: 85cc881466be03931d435d91a48548456d74305b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141877"
---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits 类

此类提供用于计算哈希值的静态函数。

## <a name="syntax"></a>语法

```
template<typename T>
class CDefaultHashTraits
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDefaultHashTraits：： Hash](#hash)| (Static) 调用此函数以计算给定元素的哈希值。|

## <a name="remarks"></a>备注

此类包含一个返回给定元素的哈希值的静态函数。 此类由 [CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)使用。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cdefaulthashtraitshash"></a><a name="hash"></a> CDefaultHashTraits：： Hash

调用此函数可为给定元素计算哈希值。

```
static ULONG Hash(const T& element) throw();
```

### <a name="parameters"></a>parameters

*element*<br/>
元素。

### <a name="return-value"></a>返回值

返回哈希值。

### <a name="remarks"></a>备注

默认哈希算法非常简单：返回值为元素号。 如果需要更复杂的算法，请重写此函数。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

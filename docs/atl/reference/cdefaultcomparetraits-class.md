---
description: 了解详细信息： CDefaultCompareTraits 类
title: CDefaultCompareTraits 类
ms.date: 11/04/2016
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
ms.openlocfilehash: dcb366cdcd99a6eed2b641be290ccc4913a81476
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141903"
---
# <a name="cdefaultcomparetraits-class"></a>CDefaultCompareTraits 类

此类提供默认元素比较函数。

## <a name="syntax"></a>语法

```
template<typename T>
class CDefaultCompareTraits
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDefaultCompareTraits::CompareElements](#compareelements)| (Static) 调用此函数以比较两个元素是否相等。|
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)| (Static) 调用此函数以确定更大和较小的元素。|

## <a name="remarks"></a>备注

此类包含两个用于比较集合类对象中存储的元素的静态函数。 此类由 [CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)使用。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cdefaultcomparetraitscompareelements"></a><a name="compareelements"></a> CDefaultCompareTraits::CompareElements

调用此函数可比较两个元素是否相等。

```
static bool CompareElements(const T& element1, const T& element2);
```

### <a name="parameters"></a>parameters

*element1*<br/>
第一个元素。

*element2*<br/>
第二个元素。

### <a name="return-value"></a>返回值

如果元素相等，则返回 true，否则返回 false。

### <a name="remarks"></a>备注

此函数的默认实现是 () 运算符的相等性 **==** 。 对于简单数据类型以外的对象，可能需要覆盖此函数。

## <a name="cdefaultcomparetraitscompareelementsordered"></a><a name="compareelementsordered"></a> CDefaultCompareTraits::CompareElementsOrdered

调用此函数可确定大于或等于的元素。

```
static int CompareElementsOrdered(const T& element1, const T& element2);
```

### <a name="parameters"></a>parameters

*element1*<br/>
第一个元素。

*element2*<br/>
第二个元素。

### <a name="return-value"></a>返回值

返回基于下表的整数：

|条件|返回值|
|---------------|------------------|
|*element1*  < *element2*|<0|
|*element1*  == *element2*|0|
|*element1*  > *element2*|>0|

### <a name="remarks"></a>备注

此函数的默认实现使用 **==** 、 **\<**, and **>** 运算符。 对于简单数据类型以外的对象，可能需要覆盖此函数。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

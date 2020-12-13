---
description: 了解详细信息： CElementTraitsBase 类
title: CElementTraitsBase 类
ms.date: 11/04/2016
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
helpviewer_keywords:
- CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
ms.openlocfilehash: a200517e378cc3c3ca854ff60e9a49ac8e43d215
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141773"
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase 类

此类提供集合类的默认复制和移动方法。

## <a name="syntax"></a>语法

```
template<typename T>
class CElementTraitsBase
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CElementTraitsBase::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CElementTraitsBase::CopyElements](#copyelements)|调用此方法可复制集合类对象中存储的元素。|
|[CElementTraitsBase::RelocateElements](#relocateelements)|调用此方法可重新定位集合类对象中存储的元素。|

## <a name="remarks"></a>备注

此基类定义用于复制和重定位集合类中的元素的方法。 它由 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)、 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md)和 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md)类使用。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="celementtraitsbasecopyelements"></a><a name="copyelements"></a> CElementTraitsBase::CopyElements

调用此方法可复制集合类对象中存储的元素。

```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>parameters

*pDest*<br/>
指向将接收复制的数据的第一个元素的指针。

*.Psrc*<br/>
指向要复制的第一个元素的指针。

*nElements*<br/>
要复制的元素数。

### <a name="remarks"></a>备注

源和目标元素不应重叠。

## <a name="celementtraitsbaseinargtype"></a><a name="inargtype"></a> CElementTraitsBase::INARGTYPE

要用于将元素添加到集合中的数据类型。

```
typedef const T& INARGTYPE;
```

## <a name="celementtraitsbaseoutargtype"></a><a name="outargtype"></a> CElementTraitsBase::OUTARGTYPE

用于检索集合中的元素的数据类型。

```
typedef T& OUTARGTYPE;
```

## <a name="celementtraitsbaserelocateelements"></a><a name="relocateelements"></a> CElementTraitsBase::RelocateElements

调用此方法可重新定位集合类对象中存储的元素。

```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```

### <a name="parameters"></a>parameters

*pDest*<br/>
指向将接收重定位数据的第一个元素的指针。

*.Psrc*<br/>
指向要重新定位的第一个元素的指针。

*nElements*<br/>
要重新定位的元素的数目。

### <a name="remarks"></a>备注

此方法调用 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)，这对大多数数据类型来说已经足够了。 如果要移动的对象包含指向其自身成员的指针，则需要重写此方法。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

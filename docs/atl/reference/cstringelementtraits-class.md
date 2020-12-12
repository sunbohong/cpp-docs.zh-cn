---
description: 了解详细信息： CStringElementTraits 类
title: CStringElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits
- CSTRINGT/ATL::CStringElementTraits::INARGTYPE
- CSTRINGT/ATL::CStringElementTraits::OUTARGTYPE
- CSTRINGT/ATL::CStringElementTraits::CompareElements
- CSTRINGT/ATL::CStringElementTraits::CompareElementsOrdered
- CSTRINGT/ATL::CStringElementTraits::CopyElements
- CSTRINGT/ATL::CStringElementTraits::Hash
- CSTRINGT/ATL::CStringElementTraits::RelocateElements
helpviewer_keywords:
- CStringElementTraits class
ms.assetid: 74d7134b-099d-4455-bf91-3e68ccbf95bc
ms.openlocfilehash: 1e3f6a73e71530250d9dd88408165471028a18e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140486"
---
# <a name="cstringelementtraits-class"></a>CStringElementTraits 类

此类提供由存储对象的集合类使用的静态函数 `CString` 。

## <a name="syntax"></a>语法

```
template <typename T>
class CStringElementTraits
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CStringElementTraits::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CStringElementTraits::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CStringElementTraits::CompareElements](#compareelements)| (Static) 调用此函数以比较两个字符串元素是否相等。|
|[CStringElementTraits::CompareElementsOrdered](#compareelementsordered)| (Static) 调用此函数以比较两个字符串元素。|
|[CStringElementTraits::CopyElements](#copyelements)| (Static) 调用此函数复制 `CString` 集合类对象中存储的元素。|
|[CStringElementTraits：： Hash](#hash)| (Static) 调用此函数以计算给定字符串元素的哈希值。|
|[CStringElementTraits::RelocateElements](#relocateelements)| (Static) 调用此函数以重新定位 `CString` 集合类对象中存储的元素。|

## <a name="remarks"></a>备注

此类提供静态函数用于复制、移动和比较字符串，以及用于创建哈希值。 当使用集合类存储基于字符串的数据时，这些函数很有用。 当需要不区分大小写的比较时，请使用 [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md) 。 当字符串对象作为引用处理时，请使用 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="requirements"></a>要求

**标头：** cstringt

## <a name="cstringelementtraitscompareelements"></a><a name="compareelements"></a> CStringElementTraits::CompareElements

调用此静态函数以比较两个字符串元素是否相等。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>parameters

*str1*<br/>
第一个字符串元素。

*str2*<br/>
第二个字符串元素。

### <a name="return-value"></a>返回值

如果元素相等，则返回 true，否则返回 false。

## <a name="cstringelementtraitscompareelementsordered"></a><a name="compareelementsordered"></a> CStringElementTraits::CompareElementsOrdered

调用此静态函数以比较两个字符串元素。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2);
```

### <a name="parameters"></a>parameters

*str1*<br/>
第一个字符串元素。

*str2*<br/>
第二个字符串元素。

### <a name="return-value"></a>返回值

如果字符串相同，则为零; 如果 *str1* 小于 *str2*，则 < 0; 如果 *str1* 大于 *str2*>，则为0。 [CStringT：： Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)方法用于执行比较。

## <a name="cstringelementtraitscopyelements"></a><a name="copyelements"></a> CStringElementTraits::CopyElements

调用此静态函数复制 `CString` 集合类对象中存储的元素。

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

## <a name="cstringelementtraitshash"></a><a name="hash"></a> CStringElementTraits：： Hash

调用此静态函数以计算给定字符串元素的哈希值。

```
static ULONG Hash(INARGTYPE str);
```

### <a name="parameters"></a>parameters

*str*<br/>
String 元素。

### <a name="return-value"></a>返回值

返回使用字符串内容计算所得的哈希值。

## <a name="cstringelementtraitsinargtype"></a><a name="inargtype"></a> CStringElementTraits::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsoutargtype"></a><a name="outargtype"></a> CStringElementTraits::OUTARGTYPE

用于检索集合类对象中的元素的数据类型。

```
typedef T& OUTARGTYPE;
```

## <a name="cstringelementtraitsrelocateelements"></a><a name="relocateelements"></a> CStringElementTraits::RelocateElements

调用此静态函数以重新定位 `CString` 集合类对象中存储的元素。

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

此静态函数调用 [memmove](../../c-runtime-library/reference/memmove-wmemmove.md)，这对大多数数据类型都足够了。 如果要移动的对象包含指向其自身成员的指针，则需要重写此静态函数。

## <a name="see-also"></a>请参阅

[CElementTraitsBase 类](../../atl/reference/celementtraitsbase-class.md)<br/>
[CStringElementTraitsI 类](../../atl/reference/cstringelementtraitsi-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

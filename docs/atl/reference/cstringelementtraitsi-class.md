---
description: 了解详细信息： CStringElementTraitsI 类
title: CStringElementTraitsI 类
ms.date: 11/04/2016
f1_keywords:
- CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI
- ATLCOLL/ATL::CStringElementTraitsI::INARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::OUTARGTYPE
- ATLCOLL/ATL::CStringElementTraitsI::CompareElements
- ATLCOLL/ATL::CStringElementTraitsI::CompareElementsOrdered
- ATLCOLL/ATL::CStringElementTraitsI::Hash
helpviewer_keywords:
- CStringElementTraitsI class
ms.assetid: c23f92b1-91e5-400f-96ed-258b02622b7a
ms.openlocfilehash: 0a626677f4a62805933b2effb4811394626374a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140396"
---
# <a name="cstringelementtraitsi-class"></a>CStringElementTraitsI 类

此类提供与集合类对象中存储的字符串相关的静态函数。 它类似于 [CStringElementTraits](../../atl/reference/cstringelementtraits-class.md)，但执行不区分大小写的比较。

## <a name="syntax"></a>语法

```
template <typename T, class CharTraits = CDefaultCharTraits<T ::XCHAR>>
class CStringElementTraitsI : public CElementTraitsBase<T>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合中的数据的类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CStringElementTraitsI::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CStringElementTraitsI::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CStringElementTraitsI::CompareElements](#compareelements)|调用此静态函数以比较两个字符串元素是否相等，同时忽略大小写差异。|
|[CStringElementTraitsI::CompareElementsOrdered](#compareelementsordered)|调用此静态函数以比较两个字符串元素，并忽略大小写差异。|
|[CStringElementTraitsI：： Hash](#hash)|调用此静态函数以计算给定字符串元素的哈希值。|

## <a name="remarks"></a>备注

此类提供用于比较字符串和创建哈希值的静态函数。 当使用集合类存储基于字符串的数据时，这些函数很有用。 当字符串对象将作为引用处理时，请使用 [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md) 。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

`CStringElementTraitsI`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cstringelementtraitsicompareelements"></a><a name="compareelements"></a> CStringElementTraitsI::CompareElements

调用此静态函数以比较两个字符串元素是否相等，同时忽略大小写差异。

```
static bool CompareElements(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>parameters

*str1*<br/>
第一个字符串元素。

*str2*<br/>
第二个字符串元素。

### <a name="return-value"></a>返回值

如果元素相等，则返回 true，否则返回 false。

### <a name="remarks"></a>备注

比较不区分大小写。

## <a name="cstringelementtraitsicompareelementsordered"></a><a name="compareelementsordered"></a> CStringElementTraitsI::CompareElementsOrdered

调用此静态函数以比较两个字符串元素，并忽略大小写差异。

```
static int CompareElementsOrdered(INARGTYPE str1, INARGTYPE str2) throw();
```

### <a name="parameters"></a>parameters

*str1*<br/>
第一个字符串元素。

*str2*<br/>
第二个字符串元素。

### <a name="return-value"></a>返回值

如果字符串相同，则为零; 如果 *str1* 小于 *str2*，则 < 0; 如果 *str1* 大于 *str2*>，则为0。 [CStringT：： Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare)方法用于执行比较。

### <a name="remarks"></a>备注

比较不区分大小写。

## <a name="cstringelementtraitsihash"></a><a name="hash"></a> CStringElementTraitsI：： Hash

调用此静态函数以计算给定字符串元素的哈希值。

```
static ULONG Hash(INARGTYPE str) throw();
```

### <a name="parameters"></a>parameters

*str*<br/>
String 元素。

### <a name="return-value"></a>返回值

返回使用字符串内容计算所得的哈希值。

## <a name="cstringelementtraitsiinargtype"></a><a name="inargtype"></a> CStringElementTraitsI::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef T::PCXSTR INARGTYPE;
```

## <a name="cstringelementtraitsioutargtype"></a><a name="outargtype"></a> CStringElementTraitsI::OUTARGTYPE

用于检索集合类对象中的元素的数据类型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>请参阅

[CElementTraitsBase 类](../../atl/reference/celementtraitsbase-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[CStringElementTraits 类](../../atl/reference/cstringelementtraits-class.md)

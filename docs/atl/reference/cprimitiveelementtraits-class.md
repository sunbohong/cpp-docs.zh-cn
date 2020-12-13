---
description: 了解详细信息： CPrimitiveElementTraits 类
title: CPrimitiveElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits
- ATLCOLL/ATL::CPrimitiveElementTraits::INARGTYPE
- ATLCOLL/ATL::CPrimitiveElementTraits::OUTARGTYPE
helpviewer_keywords:
- CPrimitiveElementTraits class
ms.assetid: 21c1cea8-2c5a-486c-b65c-85490f3ed4e6
ms.openlocfilehash: a9a47d9e6268ee6cc858d85e9236b00c270e8841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141071"
---
# <a name="cprimitiveelementtraits-class"></a>CPrimitiveElementTraits 类

此类提供由基元数据类型组成的集合类的默认方法和函数。

## <a name="syntax"></a>语法

```
template <typename T>
class CPrimitiveElementTraits : public CDefaultElementTraits<T>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合类对象中的数据的类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CPrimitiveElementTraits::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CPrimitiveElementTraits::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

## <a name="remarks"></a>备注

此类提供了用于移动、复制、比较和哈希集合类对象中存储的基元数据类型元素的默认静态函数和方法。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CPrimitiveElementTraits`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cprimitiveelementtraitsinargtype"></a><a name="inargtype"></a> CPrimitiveElementTraits::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef T INARGTYPE;
```

## <a name="cprimitiveelementtraitsoutargtype"></a><a name="outargtype"></a> CPrimitiveElementTraits::OUTARGTYPE

用于检索集合类对象中的元素的数据类型。

```
typedef T& OUTARGTYPE;
```

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

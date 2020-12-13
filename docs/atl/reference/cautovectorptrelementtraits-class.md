---
description: 了解详细信息： CAutoVectorPtrElementTraits 类
title: CAutoVectorPtrElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoVectorPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoVectorPtrElementTraits class
ms.assetid: 16b81a56-55fb-46ca-b376-66a1884231a6
ms.openlocfilehash: 571b85c1b11968289d372f9c349ffcdb754dc381
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147090"
---
# <a name="cautovectorptrelementtraits-class"></a>CAutoVectorPtrElementTraits 类

使用向量 new 和 delete 运算符创建智能指针集合时，此类提供的方法、静态函数和 typedef 非常有用。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <typename T>
class CAutoVectorPtrElementTraits :
   public CDefaultElementTraits<ATL::CAutoVectorPtr<T>>
```

#### <a name="parameters"></a>parameters

*T*<br/>
指针类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CAutoVectorPtrElementTraits::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CAutoVectorPtrElementTraits::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

## <a name="remarks"></a>备注

此类为协助提供了用于创建包含智能指针的集合类对象的方法、静态函数和 typedef。 与 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)不同，此类使用向量 new 和 delete 运算符。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoVectorPtrElementTraits`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cautovectorptrelementtraitsinargtype"></a><a name="inargtype"></a> CAutoVectorPtrElementTraits::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef CAutoVectorPtr<T>& INARGTYPE;
```

## <a name="cautovectorptrelementtraitsoutargtype"></a><a name="outargtype"></a> CAutoVectorPtrElementTraits::OUTARGTYPE

用于检索集合类对象中的元素的数据类型。

```
typedef T*& OUTARGTYPE;
```

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CAutoVectorPtr 类](../../atl/reference/cautovectorptr-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

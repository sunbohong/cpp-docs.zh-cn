---
description: 了解详细信息： CAutoPtrElementTraits 类
title: CAutoPtrElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits
- ATLCOLL/ATL::CAutoPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CAutoPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CAutoPtrElementTraits class
ms.assetid: 777c1b14-6ab7-491f-b9a5-be149e71d4a2
ms.openlocfilehash: 2478f8251f0094aaa5cabf1c0dcc873c9c526cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147129"
---
# <a name="cautoptrelementtraits-class"></a>CAutoPtrElementTraits 类

此类提供在创建智能指针集合时有用的方法、静态函数和 typedef。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<typename T>
class CAutoPtrElementTraits
    : public CDefaultElementTraits<ATL::CAutoPtr<T>>
```

#### <a name="parameters"></a>parameters

*T*<br/>
指针类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CAutoPtrElementTraits::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CAutoPtrElementTraits::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

## <a name="remarks"></a>备注

此类为协助提供了用于创建包含智能指针的集合类对象的方法、静态函数和 typedef。 类 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 和 [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) 派生自 `CAutoPtrElementTraits` 。 如果生成需要 vector new 和 delete 运算符的智能指针集合，请改用 [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CAutoPtrElementTraits`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cautoptrelementtraitsinargtype"></a><a name="inargtype"></a> CAutoPtrElementTraits::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef CAutoPtr<T>& INARGTYPE;
```

## <a name="cautoptrelementtraitsoutargtype"></a><a name="outargtype"></a> CAutoPtrElementTraits::OUTARGTYPE

用于检索集合类对象中的元素的数据类型。

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

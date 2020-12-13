---
description: 了解详细信息： CHeapPtrElementTraits 类
title: CHeapPtrElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
ms.openlocfilehash: 7ca3d194a284f06e6b5baa0530cb49bc93d8510a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141604"
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits 类

此类提供方法、静态函数和 typedef 在创建堆指针的集合时非常有用。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<typename T, class Allocator = ATL::CCRTAllocator>
class CHeapPtrElementTraits :
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在集合类中的对象类型。

*分配器*<br/>
要使用的内存分配类。 默认值为 [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|用于检索集合类对象中的元素的数据类型。|

## <a name="remarks"></a>备注

此类为协助提供了用于创建包含堆指针的集合类对象的方法、静态函数和 typedef。 类 `CHeapPtrList` 派生自 `CHeapPtrElementTraits` 。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CHeapPtrElementTraits`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cheapptrelementtraitsinargtype"></a><a name="inargtype"></a> CHeapPtrElementTraits::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```

## <a name="cheapptrelementtraitsoutargtype"></a><a name="outargtype"></a> CHeapPtrElementTraits::OUTARGTYPE

用于检索集合类对象中的元素的数据类型。

```
typedef T *& OUTARGTYPE;
```

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[CComHeapPtr 类](../../atl/reference/ccomheapptr-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

---
description: 了解详细信息： CComQIPtrElementTraits 类
title: CComQIPtrElementTraits 类
ms.date: 11/04/2016
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
ms.openlocfilehash: 9aa96c5b926263d6ed58125a28f5d0a12d8107d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142332"
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits 类

此类提供方法、静态函数和 typedef 在创建 COM 接口指针的集合时非常有用。

## <a name="syntax"></a>语法

```
template<typename I, const IID* piid=& __uuidof(I)>
class CComQIPtrElementTraits :
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```

#### <a name="parameters"></a>parameters

*I*<br/>
一个 COM 接口，指定要存储的指针的类型。

*piid*<br/>
指向 *I* 的 IID 的指针。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|用于将元素添加到集合类对象的数据类型。|

## <a name="remarks"></a>备注

此类派生方法，并在创建 [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM 接口指针对象的集合类时提供 typedef。 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md)和[CInterfaceList](../../atl/reference/cinterfacelist-class.md)类使用此类。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)

[CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)

[CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)

[CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)

`CComQIPtrElementTraits`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="ccomqiptrelementtraitsinargtype"></a><a name="inargtype"></a> CComQIPtrElementTraits::INARGTYPE

用于将元素添加到集合类对象的数据类型。

```
typedef I* INARGTYPE;
```

## <a name="see-also"></a>请参阅

[CDefaultElementTraits 类](../../atl/reference/cdefaultelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

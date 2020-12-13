---
description: 了解详细信息： CInterfaceList 类
title: CInterfaceList 类
ms.date: 11/04/2016
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
ms.openlocfilehash: 2612ba4700466bb877f84978c55bfd018f1dd286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141526"
---
# <a name="cinterfacelist-class"></a>CInterfaceList 类

此类提供的方法在构造 COM 接口指针的列表时很有用。

## <a name="syntax"></a>语法

```
template<class I, const IID* piid =& __uuidof(I)>
class CInterfaceList
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```

#### <a name="parameters"></a>parameters

*I*<br/>
一个 COM 接口，指定要存储的指针的类型。

*piid*<br/>
指向 *I* 的 IID 的指针。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CInterfaceList::CInterfaceList](#cinterfacelist)|接口列表的构造函数。|

## <a name="remarks"></a>备注

此类提供构造函数和用于创建 COM 接口指针列表的派生方法。 需要数组时，请使用 [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) 。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CAtlList](../../atl/reference/catllist-class.md)

`CInterfaceList`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cinterfacelistcinterfacelist"></a><a name="cinterfacelist"></a> CInterfaceList::CInterfaceList

接口列表的构造函数。

```
CInterfaceList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>parameters

*nBlockSize*<br/>
块大小，默认值为10。

### <a name="remarks"></a>备注

块大小是在需要新元素时分配的内存量的度量值。 较大的块大小可减少对内存分配例程的调用，但会占用更多资源。

## <a name="see-also"></a>请参阅

[CAtlList 类](../../atl/reference/catllist-class.md)<br/>
[CComQIPtr 类](../../atl/reference/ccomqiptr-class.md)<br/>
[CComQIPtrElementTraits 类](../../atl/reference/ccomqiptrelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

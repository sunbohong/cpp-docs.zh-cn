---
description: 了解详细信息： CAutoPtrList 类
title: CAutoPtrList 类
ms.date: 11/04/2016
f1_keywords:
- CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList
- ATLCOLL/ATL::CAutoPtrList::CAutoPtrList
helpviewer_keywords:
- CAutoPtrList class
ms.assetid: 11de4aca-28b0-4ff2-a74a-cb602312ffbd
ms.openlocfilehash: 51544d464904d0ebfd31b82152088a0dfa638969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152511"
---
# <a name="cautoptrlist-class"></a>CAutoPtrList 类

此类提供在构造智能指针列表时有用的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<typename E>
class CAutoPtrList :
   public CAtlList<ATL::CAutoPtr<E>, CAutoPtrElementTraits<E>>
```

#### <a name="parameters"></a>parameters

*E*<br/>
指针类型。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAutoPtrList::CAutoPtrList](#cautoptrlist)|构造函数。|

## <a name="remarks"></a>备注

此类提供构造函数并从 [CAtlList](../../atl/reference/catllist-class.md) 和 [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) 派生方法，以帮助创建存储智能指针的列表对象。 类 [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) 为数组对象提供类似的函数。

有关详细信息，请参阅 [ATL Collection 类](../../atl/atl-collection-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CAtlList](../../atl/reference/catllist-class.md)

`CAutoPtrList`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cautoptrlistcautoptrlist"></a><a name="cautoptrlist"></a> CAutoPtrList::CAutoPtrList

构造函数。

```
CAutoPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>parameters

*nBlockSize*<br/>
块大小，默认值为10。

### <a name="remarks"></a>备注

块大小是在需要新元素时分配的内存量的度量值。 较大的块大小可减少对内存分配例程的调用，但会占用更多资源。

## <a name="see-also"></a>请参阅

[CAtlList 类](../../atl/reference/catllist-class.md)<br/>
[CAutoPtrElementTraits 类](../../atl/reference/cautoptrelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

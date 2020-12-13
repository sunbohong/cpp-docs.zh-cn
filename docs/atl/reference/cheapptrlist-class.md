---
description: 了解详细信息： CHeapPtrList 类
title: CHeapPtrList 类
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
ms.openlocfilehash: 7e3a97280f7abcd4b7efebf6726ac062215912d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141591"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList 类

此类提供在构造堆指针列表时有用的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<typename E, class Allocator = ATL::CCRTAllocator>
class CHeapPtrList
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```

#### <a name="parameters"></a>parameters

*E*<br/>
要存储在集合类中的对象类型。

*分配器*<br/>
要使用的内存分配类。 默认值为 [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|构造函数。|

## <a name="remarks"></a>备注

此类提供构造函数并从 [CAtlList](../../atl/reference/catllist-class.md) 和 [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) 派生方法，以帮助创建存储堆指针的集合类对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CAtlList](../../atl/reference/catllist-class.md)

`CHeapPtrList`

## <a name="requirements"></a>要求

**标头：** atlcoll

## <a name="cheapptrlistcheapptrlist"></a><a name="cheapptrlist"></a> CHeapPtrList::CHeapPtrList

构造函数。

```
CHeapPtrList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>parameters

*nBlockSize*<br/>
块大小。

### <a name="remarks"></a>备注

块大小是在需要新元素时分配的内存量的度量值。 较大的块大小可减少对内存分配例程的调用，但会占用更多资源。

## <a name="see-also"></a>请参阅

[CAtlList 类](../../atl/reference/catllist-class.md)<br/>
[CHeapPtr 类](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrElementTraits 类](../../atl/reference/cheapptrelementtraits-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

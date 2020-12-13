---
description: 了解详细信息： CCRTAllocator 类
title: CCRTAllocator 类
ms.date: 11/04/2016
f1_keywords:
- CCRTAllocator
- ATLCORE/ATL::CCRTAllocator
- ATLCORE/ATL::CCRTAllocator::Allocate
- ATLCORE/ATL::CCRTAllocator::Free
- ATLCORE/ATL::CCRTAllocator::Reallocate
helpviewer_keywords:
- CCRTAllocator class
ms.assetid: 3e1b8cb0-859a-41ab-8e93-6f0b5ceca49d
ms.openlocfilehash: 378a1c27a6c2dde9fbcb24eb9b51b64c3af7e8aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142059"
---
# <a name="ccrtallocator-class"></a>CCRTAllocator 类

此类提供使用 CRT 内存例程管理内存的方法。

## <a name="syntax"></a>语法

```
class ATL::CCRTAllocator
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CCRTAllocator：： Allocate](#allocate)| (静态) 调用此方法来分配内存。|
|[CCRTAllocator：： Free](#free)| (静态) 调用此方法以释放内存。|
|[CCRTAllocator：：重新分配](#reallocate)| (静态) 调用此方法以重新分配内存。|

## <a name="remarks"></a>备注

此类由 [CHeapPtr](../../atl/reference/cheapptr-class.md) 用来提供 CRT 内存分配例程。 对应类 [CComAllocator](../../atl/reference/ccomallocator-class.md)使用 COM 例程提供相同的方法。

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="ccrtallocatorallocate"></a><a name="allocate"></a> CCRTAllocator：： Allocate

调用此静态函数以分配内存。

```
static __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*nBytes*<br/>
要分配的字节数。

### <a name="return-value"></a>返回值

返回指向已分配空间的 void 指针；如果可用内存不足，则返回 NULL。

### <a name="remarks"></a>备注

分配内存。 有关更多详细信息，请参阅 [malloc](../../c-runtime-library/reference/malloc.md) 。

## <a name="ccrtallocatorfree"></a><a name="free"></a> CCRTAllocator：： Free

调用此静态函数以释放内存。

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向已分配内存的指针。

### <a name="remarks"></a>备注

释放已分配的内存。 请参阅 [免费](../../c-runtime-library/reference/free.md) 了解更多详细信息。

## <a name="ccrtallocatorreallocate"></a><a name="reallocate"></a> CCRTAllocator：：重新分配

调用此静态函数以重新分配内存。

```
static __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向已分配内存的指针。

*nBytes*<br/>
要重新分配的字节数。

### <a name="return-value"></a>返回值

如果没有足够的内存，请返回指向已分配空间的 void 指针，或返回 NULL。

### <a name="remarks"></a>备注

调整已分配内存的大小。 有关更多详细信息，请参阅 [realloc](../../c-runtime-library/reference/realloc.md) 。

## <a name="see-also"></a>请参阅

[CHeapPtr 类](../../atl/reference/cheapptr-class.md)<br/>
[CComAllocator 类](../../atl/reference/ccomallocator-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

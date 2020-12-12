---
description: 了解详细信息： CComHeap 类
title: CComHeap 类
ms.date: 11/04/2016
f1_keywords:
- CComHeap
- ATLCOMMEM/ATL::CComHeap
- ATLCOMMEM/ATL::CComHeap::Allocate
- ATLCOMMEM/ATL::CComHeap::Free
- ATLCOMMEM/ATL::CComHeap::GetSize
- ATLCOMMEM/ATL::CComHeap::Reallocate
helpviewer_keywords:
- CComHeap class
ms.assetid: c74183ce-98ae-46fb-b186-93ea4cf0222b
ms.openlocfilehash: 2ced98194bea8e186cee17504ca9e3abf7c212c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152030"
---
# <a name="ccomheap-class"></a>CComHeap 类

此类使用 COM 内存分配函数实现 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) 。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CComHeap : public IAtlMemMgr
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComHeap：： Allocate](#allocate)|调用此方法来分配内存块。|
|[CComHeap：： Free](#free)|调用此方法可释放此内存管理器分配的内存块。|
|[CComHeap：： GetSize](#getsize)|调用此方法可获取此内存管理器分配的内存块的分配大小。|
|[CComHeap：：重新分配](#reallocate)|调用此方法以重新分配由该内存管理器分配的内存。|

## <a name="remarks"></a>备注

`CComHeap` 使用 COM 分配函数实现内存分配函数，包括 [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)、 [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)、 [IMalloc：： GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)和 [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)。 可分配的最大内存量等于 INT_MAX (2147483647) 字节。

## <a name="example"></a>示例

请参阅 [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)的示例。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IAtlMemMgr`

`CComHeap`

## <a name="requirements"></a>要求

**标头：** ATLComMem

## <a name="ccomheapallocate"></a><a name="allocate"></a> CComHeap：： Allocate

调用此方法来分配内存块。

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*nBytes*<br/>
新内存块中请求的字节数。

### <a name="return-value"></a>返回值

将指针返回到新分配内存块的起始位置。

### <a name="remarks"></a>备注

调用 [CComHeap：： Free](#free) 或 [CComHeap：：重新分配](#reallocate) 以释放此方法分配的内存。

使用 [CoTaskMemAlloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc)实现。

## <a name="ccomheapfree"></a><a name="free"></a> CComHeap：： Free

调用此方法可释放此内存管理器分配的内存块。

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向此内存管理器以前分配的内存的指针。 NULL 是有效的值并且不执行任何操作。

### <a name="remarks"></a>备注

使用 [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree)实现。

## <a name="ccomheapgetsize"></a><a name="getsize"></a> CComHeap：： GetSize

调用此方法可获取此内存管理器分配的内存块的分配大小。

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向此内存管理器以前分配的内存的指针。

### <a name="return-value"></a>返回值

返回分配的内存块的大小（以字节为单位）。

### <a name="remarks"></a>备注

使用 [IMalloc：： GetSize](/windows/win32/api/objidlbase/nf-objidlbase-imalloc-getsize)实现。

## <a name="ccomheapreallocate"></a><a name="reallocate"></a> CComHeap：：重新分配

调用此方法以重新分配由该内存管理器分配的内存。

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向此内存管理器以前分配的内存的指针。

*nBytes*<br/>
新内存块中请求的字节数。

### <a name="return-value"></a>返回值

将指针返回到新分配内存块的起始位置。

### <a name="remarks"></a>备注

调用 [CComHeap：： free](#free) 可释放由此方法分配的内存。

使用 [CoTaskMemRealloc](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc)实现。

## <a name="see-also"></a>请参阅

[DynamicConsumer 示例](../../overview/visual-cpp-samples.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[CWin32Heap 类](../../atl/reference/cwin32heap-class.md)<br/>
[CLocalHeap 类](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap 类](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap 类](../../atl/reference/ccrtheap-class.md)<br/>
[IAtlMemMgr 类](../../atl/reference/iatlmemmgr-class.md)

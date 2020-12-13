---
description: 了解详细信息： CHeapPtr 类
title: CHeapPtr 类
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: dc795c199562fa423a160b053c96983651d0812d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141643"
---
# <a name="cheapptr-class"></a>CHeapPtr 类

用于管理堆指针的智能指针类。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在堆上的对象类型。

*分配器*<br/>
要使用的内存分配类。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CHeapPtr：： Allocate](#allocate)|调用此方法可在堆上分配内存来存储对象。|
|[CHeapPtr：：重新分配](#reallocate)|调用此方法可重新分配堆上的内存。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CHeapPtr：： operator =](#operator_eq)|赋值运算符。|

## <a name="remarks"></a>备注

`CHeapPtr` 派生自 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) ，默认情况下使用 [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) 中 (CRT 例程来分配和释放内存。 类 [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) 可用于构造堆指针列表。 另请参阅 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md)，它使用 COM 内存分配例程。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="cheapptrallocate"></a><a name="allocate"></a> CHeapPtr：： Allocate

调用此方法可在堆上分配内存来存储对象。

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>parameters

*nElements*<br/>
用于计算要分配的内存量的元素数。 默认值为 1。

### <a name="return-value"></a>返回值

如果已成功分配内存，则返回 true，否则返回 false。

### <a name="remarks"></a>备注

分配器例程用于在堆上保留足够的内存来存储在构造函数中定义的类型的 *nElement* 对象。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a> CHeapPtr::CHeapPtr

构造函数。

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
现有堆指针或 `CHeapPtr` 。

### <a name="remarks"></a>备注

可以选择使用现有指针或对象创建堆指针 `CHeapPtr` 。 如果是这样，则新的 `CHeapPtr` 对象将负责管理新的指针和资源。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a> CHeapPtr：： operator =

赋值运算符。

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
一个现有的 `CHeapPtr` 对象。

### <a name="return-value"></a>返回值

返回对已更新的的引用 `CHeapPtr` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a> CHeapPtr：：重新分配

调用此方法可重新分配堆上的内存。

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>parameters

*nElements*<br/>
用于计算要分配的内存量的新元素数。

### <a name="return-value"></a>返回值

如果已成功分配内存，则返回 true，否则返回 false。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>请参阅

[CHeapPtrBase 类](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator 类](../../atl/reference/ccrtallocator-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

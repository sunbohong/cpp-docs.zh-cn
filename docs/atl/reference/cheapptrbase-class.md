---
description: 了解详细信息： CHeapPtrBase 类
title: CHeapPtrBase 类
ms.date: 11/04/2016
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
ms.openlocfilehash: 6186f68066f4c159c16c458f9f00725478aa98a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141630"
---
# <a name="cheapptrbase-class"></a>CHeapPtrBase 类

此类构成了几个智能堆指针类的基础。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <class T, class Allocator = CCRTAllocator>
class CHeapPtrBase
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在堆上的对象类型。

*分配器*<br/>
要使用的内存分配类。 默认情况下，CRT 例程用于分配和释放内存。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHeapPtrBase：： ~ CHeapPtrBase](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|调用此方法来分配内存。|
|[CHeapPtrBase：： Attach](#attach)|调用此方法以获取现有指针的所有权。|
|[CHeapPtrBase：:D etach](#detach)|调用此方法可释放指针的所有权。|
|[CHeapPtrBase：： Free](#free)|调用此方法以删除指向的对象 `CHeapPtrBase` 。|
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|调用此方法可重新分配内存。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CHeapPtrBase：： operator T *](#operator_t_star)|转换运算符。|
|[CHeapPtrBase：： operator &](#operator_amp)|& 运算符。|
|[CHeapPtrBase：： operator->](#operator_ptr)|指向成员的指针运算符。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CHeapPtrBase：： m_pData](#m_pdata)|指针数据成员变量。|

## <a name="remarks"></a>备注

此类构成了几个智能堆指针类的基础。 派生类（例如 [CHeapPtr](../../atl/reference/cheapptr-class.md) 和 [CComHeapPtr](../../atl/reference/ccomheapptr-class.md)）添加其自己的构造函数和运算符。 有关实现示例，请参阅这些类。

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a> CHeapPtrBase::AllocateBytes

调用此方法来分配内存。

```
bool AllocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*nBytes*<br/>
要分配的内存字节数。

### <a name="return-value"></a>返回值

如果已成功分配内存，则返回 true，否则返回 false。

### <a name="remarks"></a>备注

在调试版本中，如果 [CHeapPtrBase：： m_pData](#m_pdata) 成员变量当前指向现有值，则将发生断言失败;也就是说，它不等于 NULL。

## <a name="cheapptrbaseattach"></a><a name="attach"></a> CHeapPtrBase：： Attach

调用此方法以获取现有指针的所有权。

```cpp
void Attach(T* pData) throw();
```

### <a name="parameters"></a>parameters

*pData*<br/>
`CHeapPtrBase`对象将取得此指针的所有权。

### <a name="remarks"></a>备注

当 `CHeapPtrBase` 对象取得指针的所有权时，它会在超出范围时自动删除指针和任何分配的数据。

在调试版本中，如果 [CHeapPtrBase：： m_pData](#m_pdata) 成员变量当前指向现有值，则将发生断言失败;也就是说，它不等于 NULL。

## <a name="cheapptrbasecheapptrbase"></a><a name="dtor"></a> CHeapPtrBase：： ~ CHeapPtrBase

析构函数。

```
~CHeapPtrBase() throw();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

## <a name="cheapptrbasedetach"></a><a name="detach"></a> CHeapPtrBase：:D etach

调用此方法可释放指针的所有权。

```
T* Detach() throw();
```

### <a name="return-value"></a>返回值

返回指针的副本。

### <a name="remarks"></a>备注

释放指针的所有权，将 [CHeapPtrBase：： m_pData](#m_pdata) 成员变量设置为 NULL，并返回指针的副本。

## <a name="cheapptrbasefree"></a><a name="free"></a> CHeapPtrBase：： Free

调用此方法以删除指向的对象 `CHeapPtrBase` 。

```cpp
void Free() throw();
```

### <a name="remarks"></a>备注

将释放由指向的对象 `CHeapPtrBase` ，并将 [CHeapPtrBase：： m_pData](#m_pdata) 成员变量设置为 NULL。

## <a name="cheapptrbasem_pdata"></a><a name="m_pdata"></a> CHeapPtrBase：： m_pData

指针数据成员变量。

```
T* m_pData;
```

### <a name="remarks"></a>备注

此成员变量保存指针信息。

## <a name="cheapptrbaseoperator-amp"></a><a name="operator_amp"></a> CHeapPtrBase：： operator &amp;

& 运算符。

```
T** operator&() throw();
```

### <a name="return-value"></a>返回值

返回对象所指向的对象的地址 `CHeapPtrBase` 。

## <a name="cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a> CHeapPtrBase：： operator-&gt;

指向成员的指针运算符。

```
T* operator->() const throw();
```

### <a name="return-value"></a>返回值

返回 [CHeapPtrBase：： m_pData](#m_pdata) 成员变量的值。

### <a name="remarks"></a>备注

使用此运算符可调用对象所指向的类中的方法 `CHeapPtrBase` 。 在调试版本中，如果指向 NULL，将发生断言失败 `CHeapPtrBase` 。

## <a name="cheapptrbaseoperator-t"></a><a name="operator_t_star"></a> CHeapPtrBase：： operator T *

转换运算符。

```
operator T*() const throw();
```

### <a name="remarks"></a>备注

返回 [CHeapPtrBase：： m_pData](#m_pdata)。

## <a name="cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a> CHeapPtrBase::ReallocateBytes

调用此方法可重新分配内存。

```
bool ReallocateBytes(size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*nBytes*<br/>
要分配的新内存量（以字节为单位）。

### <a name="return-value"></a>返回值

如果已成功分配内存，则返回 true，否则返回 false。

## <a name="see-also"></a>请参阅

[CHeapPtr 类](../../atl/reference/cheapptr-class.md)<br/>
[CComHeapPtr 类](../../atl/reference/ccomheapptr-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

---
description: 了解详细信息： CComHeapPtr 类
title: CComHeapPtr 类
ms.date: 11/04/2016
f1_keywords:
- CComHeapPtr
- ATLBASE/ATL::CComHeapPtr
- ATLBASE/ATL::CComHeapPtr::CComHeapPtr
helpviewer_keywords:
- CComHeapPtr class
ms.assetid: bd08b53d-da2b-43ab-a79c-e7c8dbbc5994
ms.openlocfilehash: 18865923e86a2392260ab1e6dedde2f37b9b4ea3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146622"
---
# <a name="ccomheapptr-class"></a>CComHeapPtr 类

用于管理堆指针的智能指针类。

## <a name="syntax"></a>语法

```
template<typename T>
class CComHeapPtr : public CHeapPtr<T, CComAllocator>
```

#### <a name="parameters"></a>parameters

*T*<br/>
要存储在堆上的对象类型。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComHeapPtr::CComHeapPtr](#ccomheapptr)|构造函数。|

## <a name="remarks"></a>备注

`CComHeapPtr` 派生自 `CHeapPtr` ，但使用 [CCOMALLOCATOR](../../atl/reference/ccomallocator-class.md) 通过 COM 例程分配内存。 请参阅 [CHeapPtr](../../atl/reference/cheapptr-class.md) 和 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) ，了解可用的方法。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

[CHeapPtr](../../atl/reference/cheapptr-class.md)

`CComHeapPtr`

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="ccomheapptrccomheapptr"></a><a name="ccomheapptr"></a> CComHeapPtr::CComHeapPtr

构造函数。

```
CComHeapPtr() throw();
explicit CComHeapPtr(T* pData) throw();
```

### <a name="parameters"></a>parameters

*pData*<br/>
一个现有的 `CComHeapPtr` 对象。

### <a name="remarks"></a>备注

可以选择使用现有对象创建堆指针 `CComHeapPtr` 。 如果是这样，则新的 `CComHeapPtr` 对象将负责管理新的指针和资源。

## <a name="see-also"></a>请参阅

[CHeapPtr 类](../../atl/reference/cheapptr-class.md)<br/>
[CHeapPtrBase 类](../../atl/reference/cheapptrbase-class.md)<br/>
[CComAllocator 类](../../atl/reference/ccomallocator-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

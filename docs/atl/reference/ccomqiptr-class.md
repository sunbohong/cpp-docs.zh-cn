---
description: 了解详细信息： CComQIPtr 类
title: CComQIPtr 类
ms.date: 11/04/2016
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
ms.openlocfilehash: e5af938cd7b2bbae3b091eac5323d3455ce1cf02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142319"
---
# <a name="ccomqiptr-class"></a>CComQIPtr 类

用于管理 COM 接口指针的智能指针类。

## <a name="syntax"></a>语法

```
template<class T, const IID* piid= &__uuidof(T)>
class CComQIPtr: public CComPtr<T>
```

#### <a name="parameters"></a>parameters

*T*<br/>
一个 COM 接口，指定要存储的指针的类型。

*piid*<br/>
指向 *T* 的 IID 的指针。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComQIPtr：： CComQIPtr](#ccomqiptr)|构造函数。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CComQIPtr：： operator =](#operator_eq)|分配指向成员指针的指针。|

## <a name="remarks"></a>备注

ATL 使用 `CComQIPtr` 和 [CCOMPTR](../../atl/reference/ccomptr-class.md) 管理 COM 接口指针，它们都派生自 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)。 这两个类通过调用和执行自动引用计数 `AddRef` `Release` 。 重载运算符处理指针运算。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CComPtrBase](../../atl/reference/ccomptrbase-class.md)

[CComPtr](../../atl/reference/ccomptr-class.md)

`CComQIPtr`

## <a name="requirements"></a>要求

**标头：** atlcomcli。h

## <a name="ccomqiptrccomqiptr"></a><a name="ccomqiptr"></a> CComQIPtr：： CComQIPtr

构造函数。

```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```

### <a name="parameters"></a>parameters

*lp*<br/>
用于初始化接口指针。

*T*<br/>
COM 接口。

*piid*<br/>
指向 *T* 的 IID 的指针。

## <a name="ccomqiptroperator-"></a><a name="operator_eq"></a> CComQIPtr：： operator =

赋值运算符。

```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```

### <a name="parameters"></a>parameters

*lp*<br/>
用于初始化接口指针。

*T*<br/>
COM 接口。

*piid*<br/>
指向 *T* 的 IID 的指针。

### <a name="return-value"></a>返回值

返回一个指向已更新的 `CComQIPtr` 对象的指针。

## <a name="see-also"></a>请参阅

[CComPtr：： CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)<br/>
[CComQIPtr：： CComQIPtr](#ccomqiptr)<br/>
[CComPtrBase 类](../../atl/reference/ccomptrbase-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[CComQIPtrElementTraits 类](../../atl/reference/ccomqiptrelementtraits-class.md)

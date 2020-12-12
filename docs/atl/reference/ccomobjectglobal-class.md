---
description: 了解详细信息： CComObjectGlobal 类
title: CComObjectGlobal 类
ms.date: 11/04/2016
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
ms.openlocfilehash: 0f79acb0fdbb43f9456e08f26875d45eec9904c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151978"
---
# <a name="ccomobjectglobal-class"></a>CComObjectGlobal 类

此类管理包含对象的模块的引用计数 `Base` 。

## <a name="syntax"></a>语法

```
template<class Base>
class CComObjectGlobal : public Base
```

#### <a name="parameters"></a>parameters

*基座*<br/>
从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 或 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)派生的类，以及要在对象上支持的任何其他接口。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|构造函数。|
|[CComObjectGlobal：： ~ CComObjectGlobal](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComObjectGlobal：： AddRef](#addref)|实现全局 `AddRef` 。|
|[CComObjectGlobal：： QueryInterface](#queryinterface)|实现全局 `QueryInterface` 。|
|[CComObjectGlobal：： Release](#release)|实现全局 `Release` 。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComObjectGlobal：： m_hResFinalConstruct](#m_hresfinalconstruct)|包含在构造对象期间返回的 HRESULT `CComObjectGlobal` 。|

## <a name="remarks"></a>备注

`CComObjectGlobal` 管理包含您的对象的模块上的引用计数 `Base` 。 `CComObjectGlobal` 只要模块未释放，就可以确保不会删除您的对象。 只有在整个模块的引用计数变为零时，才会删除您的对象。

例如，使用 `CComObjectGlobal` ，类工厂可以保存其所有客户端共享的公共全局对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

`Base`

`CComObjectGlobal`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomobjectglobaladdref"></a><a name="addref"></a> CComObjectGlobal：： AddRef

将对象的引用计数递增1。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>返回值

可能对诊断和测试有用的值。

### <a name="remarks"></a>备注

默认情况下， `AddRef` 调用 `_Module::Lock` ，其中 `_Module` 是 [CComModule](../../atl/reference/ccommodule-class.md) 的全局实例或从其派生的类。

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="ccomobjectglobal"></a> CComObjectGlobal::CComObjectGlobal

构造函数。 调用 `FinalConstruct` ，然后将 [m_hResFinalConstruct](#m_hresfinalconstruct) 设置为 `HRESULT` 返回的 `FinalConstruct` 。

```
CComObjectGlobal(void* = NULL));
```

### <a name="remarks"></a>备注

如果尚未从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)派生基类，则必须提供自己的 `FinalConstruct` 方法。 析构函数调用 `FinalRelease`。

## <a name="ccomobjectglobalccomobjectglobal"></a><a name="dtor"></a> CComObjectGlobal：： ~ CComObjectGlobal

析构函数。

```
CComObjectGlobal();
```

### <a name="remarks"></a>备注

释放所有已分配的资源，并调用 [FinalRelease](ccomobjectrootex-class.md#finalrelease)。

## <a name="ccomobjectglobalm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectGlobal：： m_hResFinalConstruct

包含在 `FinalConstruct` 对象构造过程中调用的 HRESULT `CComObjectGlobal` 。

```
HRESULT m_hResFinalConstruct;
```

## <a name="ccomobjectglobalqueryinterface"></a><a name="queryinterface"></a> CComObjectGlobal：： QueryInterface

检索指向所请求的接口指针的指针。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>parameters

*iid*<br/>
中所请求的接口的 GUID。

*ppvObject*<br/>
弄指向由 iid 标识的接口指针的指针; 如果找不到接口，则为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

`QueryInterface` 仅处理 COM 映射表中的接口。

## <a name="ccomobjectglobalrelease"></a><a name="release"></a> CComObjectGlobal：： Release

将对象的引用计数递减1。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>返回值

在调试版本中，将 `Release` 返回一个值，该值可用于诊断和测试。 在非调试版本中， `Release` 始终返回0。

### <a name="remarks"></a>备注

默认情况下， `Release` 调用 `_Module::Unlock` ，其中 `_Module` 是 [CComModule](../../atl/reference/ccommodule-class.md) 的全局实例或从其派生的类。

## <a name="see-also"></a>请参阅

[CComObjectStack 类](../../atl/reference/ccomobjectstack-class.md)<br/>
[CComAggObject 类](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 类](../../atl/reference/ccomobject-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

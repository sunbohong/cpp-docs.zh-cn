---
description: 了解详细信息： CComObjectStack 类
title: CComObjectStack 类
ms.date: 11/04/2016
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
ms.openlocfilehash: 5713601a765ad9ff1c32992d1f9c517dd86affca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142410"
---
# <a name="ccomobjectstack-class"></a>CComObjectStack 类

此类创建一个临时 COM 对象，并为其提供框架实现 `IUnknown` 。

## <a name="syntax"></a>语法

```
template <class  Base>
class CComObjectStack : public Base
```

#### <a name="parameters"></a>parameters

*基座*<br/>
从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 或 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)派生的类，以及要在对象上支持的任何其他接口。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|构造函数。|
|[CComObjectStack：： ~ CComObjectStack](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComObjectStack：： AddRef](#addref)|返回零。 在调试模式中，调用 `_ASSERTE` 。|
|[CComObjectStack：： QueryInterface](#queryinterface)|返回 E_NOINTERFACE。 在调试模式中，调用 `_ASSERTE` 。|
|[CComObjectStack：： Release](#release)|返回零。 在调试模式中，调用 `_ASSERTE` 。 ~|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComObjectStack：： m_hResFinalConstruct](#m_hresfinalconstruct)|包含在构造对象期间返回的 HRESULT `CComObjectStack` 。|

## <a name="remarks"></a>备注

`CComObjectStack` 用于创建临时 COM 对象，并为对象提供主干实现 `IUnknown` 。 通常情况下，该对象用作一个函数 (中的局部变量，并将其推送到堆栈) 上。 由于对象在函数完成时被销毁，因此不会执行引用计数来提高效率。

下面的示例演示如何创建一个在函数内使用的 COM 对象：

[!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]

临时对象 `Tempobj` 被推送到堆栈上，并在函数完成时自动消失。

## <a name="inheritance-hierarchy"></a>继承层次结构

`Base`

`CComObjectStack`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomobjectstackaddref"></a><a name="addref"></a> CComObjectStack：： AddRef

返回零。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>返回值

返回零。

### <a name="remarks"></a>备注

在调试模式中，调用 `_ASSERTE` 。

## <a name="ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a> CComObjectStack::CComObjectStack

构造函数。

```
CComObjectStack(void* = NULL);
```

### <a name="remarks"></a>备注

调用 `FinalConstruct` ，然后将 [m_hResFinalConstruct](#m_hresfinalconstruct) 设置为返回的 HRESULT `FinalConstruct` 。 如果尚未从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md)派生基类，则必须提供自己的 `FinalConstruct` 方法。 析构函数调用 `FinalRelease`。

## <a name="ccomobjectstackccomobjectstack"></a><a name="dtor"></a> CComObjectStack：： ~ CComObjectStack

析构函数。

```
CComObjectStack();
```

### <a name="remarks"></a>备注

释放所有已分配的资源，并调用 [FinalRelease](ccomobjectrootex-class.md#finalrelease)。

## <a name="ccomobjectstackm_hresfinalconstruct"></a><a name="m_hresfinalconstruct"></a> CComObjectStack：： m_hResFinalConstruct

包含在 `FinalConstruct` 对象构造过程中通过调用返回的 HRESULT `CComObjectStack` 。

```
HRESULT    m_hResFinalConstruct;
```

## <a name="ccomobjectstackqueryinterface"></a><a name="queryinterface"></a> CComObjectStack：： QueryInterface

返回 E_NOINTERFACE。

```
HRESULT    QueryInterface(REFIID, void**);
```

### <a name="return-value"></a>返回值

返回 E_NOINTERFACE。

### <a name="remarks"></a>备注

在调试模式中，调用 `_ASSERTE` 。

## <a name="ccomobjectstackrelease"></a><a name="release"></a> CComObjectStack：： Release

返回零。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>返回值

返回零。

### <a name="remarks"></a>备注

在调试模式中，调用 `_ASSERTE` 。

## <a name="see-also"></a>请参阅

[CComAggObject 类](../../atl/reference/ccomaggobject-class.md)<br/>
[CComObject 类](../../atl/reference/ccomobject-class.md)<br/>
[CComObjectGlobal 类](../../atl/reference/ccomobjectglobal-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

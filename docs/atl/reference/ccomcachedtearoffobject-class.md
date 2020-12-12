---
description: 了解详细信息： CComCachedTearOffObject 类
title: CComCachedTearOffObject 类
ms.date: 11/04/2016
f1_keywords:
- CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::CComCachedTearOffObject
- ATLCOM/ATL::CComCachedTearOffObject::AddRef
- ATLCOM/ATL::CComCachedTearOffObject::FinalConstruct
- ATLCOM/ATL::CComCachedTearOffObject::FinalRelease
- ATLCOM/ATL::CComCachedTearOffObject::QueryInterface
- ATLCOM/ATL::CComCachedTearOffObject::Release
- ATLCOM/ATL::CComCachedTearOffObject::m_contained
helpviewer_keywords:
- cache, ATL cached tear-off objects
- CComCachedTearOffObject class
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
ms.openlocfilehash: 321e92b6bdf59834cd6c74b417a1788beefbdcb8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146908"
---
# <a name="ccomcachedtearoffobject-class"></a>CComCachedTearOffObject 类

此类为拆卸接口实现 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 。

## <a name="syntax"></a>语法

```
template
<class contained>
class CComCachedTearOffObject : public
    IUnknown,
public CComObjectRootEx<contained
::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>parameters

*独立*<br/>
从派生的类， `CComTearOffObjectBase` 以及要使其支持您的脱离对象的接口。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComCachedTearOffObject::CComCachedTearOffObject](#ccomcachedtearoffobject)|构造函数。|
|[CComCachedTearOffObject：： ~ CComCachedTearOffObject](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComCachedTearOffObject：： AddRef](#addref)|递增对象的引用计数 `CComCachedTearOffObject` 。|
|[CComCachedTearOffObject：： FinalConstruct](#finalconstruct)|调用 `m_contained::FinalConstruct` (脱离类的) 方法。|
|[CComCachedTearOffObject::FinalRelease](#finalrelease)|调用 `m_contained::FinalRelease` (脱离类的) 方法。|
|[CComCachedTearOffObject：： QueryInterface](#queryinterface)|返回指向对象的的指针 `IUnknown` `CComCachedTearOffObject` ，或返回类)  (您的脱离类上所请求的接口的指针 `contained` 。|
|[CComCachedTearOffObject：： Release](#release)|递减对象的引用计数 `CComCachedTearOffObject` ，并在引用计数为0时将其销毁。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComCachedTearOffObject：： m_contained](#m_contained)|`CComContainedObject`派生自你的撕类 (类) 的对象 `contained` 。|

## <a name="remarks"></a>备注

`CComCachedTearOffObject` 为脱离接口实现 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 。 此类与的不同之处在于，它 `CComTearOffObject` `CComCachedTearOffObject` 具有其自己的 `IUnknown` 独立于所有者对象的 `IUnknown` (所有者是要为其创建撕) 的对象。 `CComCachedTearOffObject` 在其引用计数为零时，维护其自己的引用计数 `IUnknown` ，并删除自身。 但是，如果查询其任何脱离接口，所有者对象的引用计数 `IUnknown` 将递增。

如果 `CComCachedTearOffObject` 实现了分离的对象已经实例化，并再次查询了脱离接口，则重用相同的 `CComCachedTearOffObject` 对象。 与此相反，如果通过所有者对象再次查询由实现的脱离接口，则会 `CComTearOffObject` 实例化另一个 `CComTearOffObject` 。

所有者类必须在为 `FinalRelease` 缓存的中实现并调用 `Release` `IUnknown` `CComCachedTearOffObject` ，这将减少其引用计数。 这将导致 `CComCachedTearOffObject` `FinalRelease` 调用，并删除删除。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComCachedTearOffObject`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomcachedtearoffobjectaddref"></a><a name="addref"></a> CComCachedTearOffObject：： AddRef

将对象的引用计数递增 `CComCachedTearOffObject` 1。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>返回值

可能对诊断和测试有用的值。

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="ccomcachedtearoffobject"></a> CComCachedTearOffObject::CComCachedTearOffObject

构造函数。

```
CComCachedTearOffObject(void* pv);
```

### <a name="parameters"></a>parameters

*函数*<br/>
中指向的 `IUnknown` 的指针 `CComCachedTearOffObject` 。

### <a name="remarks"></a>备注

初始化 `CComContainedObject` 成员， [m_contained](#m_contained)。

## <a name="ccomcachedtearoffobjectccomcachedtearoffobject"></a><a name="dtor"></a> CComCachedTearOffObject：： ~ CComCachedTearOffObject

析构函数。

```
~CComCachedTearOffObject();
```

### <a name="remarks"></a>备注

释放所有已分配的资源，并调用 [FinalRelease](#finalrelease)。

## <a name="ccomcachedtearoffobjectfinalconstruct"></a><a name="finalconstruct"></a> CComCachedTearOffObject：： FinalConstruct

`m_contained::FinalConstruct`要创建 `m_contained`> 的调用，该 `CComContainedObject` <  `contained` 对象用于访问由你的撕开类实现的接口。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ccomcachedtearoffobjectfinalrelease"></a><a name="finalrelease"></a> CComCachedTearOffObject::FinalRelease

调用 `m_contained::FinalRelease` `m_contained` （ `CComContainedObject` <  `contained`> 对象）。

```cpp
void FinalRelease();
```

## <a name="ccomcachedtearoffobjectm_contained"></a><a name="m_contained"></a> CComCachedTearOffObject：： m_contained

一个派生自你的 [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 类的对象。

```
CcomContainedObject <contained> m_contained;
```

### <a name="parameters"></a>parameters

*独立*<br/>
中从派生的类， `CComTearOffObjectBase` 以及要使其支持您的脱离对象的接口。

### <a name="remarks"></a>备注

方法 `m_contained` 继承用于通过缓存的撕出对象的、和来访问你的脱离类中的脱离接口 `QueryInterface` `FinalConstruct` `FinalRelease` 。

## <a name="ccomcachedtearoffobjectqueryinterface"></a><a name="queryinterface"></a> CComCachedTearOffObject：： QueryInterface

检索指向所请求的接口的指针。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```

### <a name="parameters"></a>parameters

*iid*<br/>
中所请求的接口的 GUID。

*ppvObject*<br/>
弄指向由 *iid* 标识的接口指针的指针; 如果找不到接口，则为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

如果请求的接口为 `IUnknown` ，则返回一个指向 `CComCachedTearOffObject` 自身的指针 `IUnknown` 并递增引用计数。 否则，使用从继承的 [InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) 方法在您的脱离类上查询接口 `CComObjectRootEx` 。

## <a name="ccomcachedtearoffobjectrelease"></a><a name="release"></a> CComCachedTearOffObject：： Release

将引用计数递减1，如果引用计数为0，则删除 `CComCachedTearOffObject` 对象。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>返回值

在非调试版本中，始终返回0。 在调试版本中，将返回一个值，该值对于诊断或测试可能很有用。

## <a name="see-also"></a>请参阅

[CComTearOffObject 类](../../atl/reference/ccomtearoffobject-class.md)<br/>
[CComObjectRootEx 类](../../atl/reference/ccomobjectrootex-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

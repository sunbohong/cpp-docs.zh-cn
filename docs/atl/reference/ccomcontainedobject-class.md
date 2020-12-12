---
description: 了解详细信息： CComContainedObject 类
title: CComContainedObject 类
ms.date: 11/04/2016
f1_keywords:
- CComContainedObject
- ATLCOM/ATL::CComContainedObject
- ATLCOM/ATL::CComContainedObject::CComContainedObject
- ATLCOM/ATL::CComContainedObject::AddRef
- ATLCOM/ATL::CComContainedObject::GetControllingUnknown
- ATLCOM/ATL::CComContainedObject::QueryInterface
- ATLCOM/ATL::CComContainedObject::Release
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComContainedObject class
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
ms.openlocfilehash: 9c0993d5ce71a557b71939f60a7019d3c062bac3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152199"
---
# <a name="ccomcontainedobject-class"></a>CComContainedObject 类

此类通过[](/windows/win32/api/unknwn/nn-unknwn-iunknown)委托给所有者对象的来实现 IUnknown `IUnknown` 。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<class Base>
class CComContainedObject : public Base
```

#### <a name="parameters"></a>parameters

*基座*<br/>
从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 或 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)派生的类。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComContainedObject::CComContainedObject](#ccomcontainedobject)|构造函数。 初始化指向所有者对象的成员指针 `IUnknown` 。|
|[CComContainedObject：： ~ CComContainedObject](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComContainedObject：： AddRef](#addref)|递增所有者对象的引用计数。|
|[CComContainedObject::GetControllingUnknown](#getcontrollingunknown)|检索所有者对象的 `IUnknown` 。|
|[CComContainedObject：： QueryInterface](#queryinterface)|检索指向所有者对象上所请求的接口的指针。|
|[CComContainedObject：： Release](#release)|递减所有者对象的引用计数。|

## <a name="remarks"></a>备注

ATL `CComContainedObject` 在类 [CComAggObject](../../atl/reference/ccomaggobject-class.md)、 [CComPolyObject](../../atl/reference/ccompolyobject-class.md)和 [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md)中使用。 `CComContainedObject`通过[](/windows/win32/api/unknwn/nn-unknwn-iunknown)委托给所有者对象的来实现 IUnknown `IUnknown` 。  (所有者是聚合的外部对象或正在为其创建脱离接口的对象。 ) `CComContainedObject` 调用 `CComObjectRootEx` 的 `OuterQueryInterface` 、 `OuterAddRef` 和 `OuterRelease` ，它们都通过继承 `Base` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`Base`

`CComContainedObject`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomcontainedobjectaddref"></a><a name="addref"></a> CComContainedObject：： AddRef

递增所有者对象的引用计数。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>返回值

可能对诊断或测试有用的值。

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="ccomcontainedobject"></a> CComContainedObject::CComContainedObject

构造函数。

```
CComContainedObject(void* pv);
```

### <a name="parameters"></a>parameters

*函数*<br/>
中所有者对象的 `IUnknown` 。

### <a name="remarks"></a>备注

设置 `m_pOuterUnknown` 成员指针 (通过 `Base` 类继承) 到 *pv*。

## <a name="ccomcontainedobjectccomcontainedobject"></a><a name="dtor"></a> CComContainedObject：： ~ CComContainedObject

析构函数。

```
~CComContainedObject();
```

### <a name="remarks"></a>备注

释放所有已分配的资源。

## <a name="ccomcontainedobjectgetcontrollingunknown"></a><a name="getcontrollingunknown"></a> CComContainedObject::GetControllingUnknown

返回 `m_pOuterUnknown` (通过包含所有者对象的 *基类*) 继承的成员指针 `IUnknown` 。

```
IUnknown* GetControllingUnknown();
```

### <a name="return-value"></a>返回值

所有者对象的 `IUnknown` 。

### <a name="remarks"></a>备注

如果 `Base` 已声明 [DECLARE_GET_CONTROLLING_UNKNOWN](aggregation-and-class-factory-macros.md#declare_get_controlling_unknown) 宏，则此方法可能是虚拟的。

## <a name="ccomcontainedobjectqueryinterface"></a><a name="queryinterface"></a> CComContainedObject：： QueryInterface

检索指向所有者对象上所请求的接口的指针。

```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```

### <a name="parameters"></a>parameters

*iid*<br/>
中所请求的接口的标识符。

*ppvObject*<br/>
弄指向由 *iid* 标识的接口指针的指针。 如果对象不支持此接口，则将 *ppvObject* 设置为 NULL。

*pp*<br/>
弄指向由类型标识的接口指针的指针 `Q` 。 如果对象不支持此接口，则 *pp* 设置为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ccomcontainedobjectrelease"></a><a name="release"></a> CComContainedObject：： Release

递减所有者对象的引用计数。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>返回值

在调试版本中，将 `Release` 返回一个值，该值对于诊断或测试可能很有用。 在非调试版本中， `Release` 始终返回0。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

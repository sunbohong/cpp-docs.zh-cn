---
description: 了解详细信息： CComAggObject 类
title: CComAggObject 类
ms.date: 11/04/2016
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
ms.openlocfilehash: 84af79678221ae74a151a4821039ff1d7a743cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152355"
---
# <a name="ccomaggobject-class"></a>CComAggObject 类

此类为聚合的对象实现 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 接口。 按照定义，聚合对象包含在外部对象中。 `CComAggObject`类类似于[CComObject 类](../../atl/reference/ccomobject-class.md)，只不过它公开了可直接由外部客户端访问的接口。

## <a name="syntax"></a>语法

```
template<class contained>
class CComAggObject : public IUnknown,
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```

#### <a name="parameters"></a>parameters

*独立*<br/>
从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 或 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)派生的类，以及要在对象上支持的任何其他接口。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CComAggObject：： CComAggObject](#ccomaggobject)|构造函数。|
|[CComAggObject：： ~ CComAggObject](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComAggObject：： AddRef](#addref)|递增聚合对象上的引用计数。|
|[CComAggObject：： CreateInstance](#createinstance)|此静态函数允许创建新的 **CComAggObject<** `contained` **>** 对象，而不会产生 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)开销。|
|[CComAggObject：： FinalConstruct](#finalconstruct)|执行的最终初始化 `m_contained` 。|
|[CComAggObject：： FinalRelease](#finalrelease)|执行的最终析构 `m_contained` 。|
|[CComAggObject：： QueryInterface](#queryinterface)|检索指向所请求的接口的指针。|
|[CComAggObject：： Release](#release)|递减聚合对象上的引用计数。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComAggObject：： m_contained](#m_contained)|将 `IUnknown` 调用委托给外部未知。|

## <a name="remarks"></a>备注

`CComAggObject` 实现聚合对象的 [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) 。 `CComAggObject` 具有其自己的 `IUnknown` 接口，与外部对象的 `IUnknown` 接口分离，维护其自己的引用计数。

有关聚合的详细信息，请参阅 [ATL COM 对象的基础知识](../../atl/fundamentals-of-atl-com-objects.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IUnknown`

`CComAggObject`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomaggobjectaddref"></a><a name="addref"></a> CComAggObject：： AddRef

递增聚合对象上的引用计数。

```
STDMETHOD_(ULONG, AddRef)();
```

### <a name="return-value"></a>返回值

可能对诊断或测试有用的值。

## <a name="ccomaggobjectccomaggobject"></a><a name="ccomaggobject"></a> CComAggObject：： CComAggObject

构造函数。

```
CComAggObject(void* pv);
```

### <a name="parameters"></a>parameters

*函数*<br/>
中外部未知。

### <a name="remarks"></a>备注

初始化 `CComContainedObject` 成员、 [m_contained](#m_contained)，并递增模块锁计数。

析构函数递减模块锁计数。

## <a name="ccomaggobjectccomaggobject"></a><a name="dtor"></a> CComAggObject：： ~ CComAggObject

析构函数。

```
~CComAggObject();
```

### <a name="remarks"></a>备注

释放所有已分配的资源，调用 [FinalRelease](#finalrelease)，并递减模块锁计数。

## <a name="ccomaggobjectcreateinstance"></a><a name="createinstance"></a> CComAggObject：： CreateInstance

此静态函数允许创建新的 **CComAggObject<** `contained` **>** 对象，而不会产生 [CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)开销。

```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```

### <a name="parameters"></a>parameters

*pp*<br/>
弄指向 **\<**<em> 包含 </em>**> * * 指针的 CComAggObject 的指针。 如果 `CreateInstance` 不成功，则 *pp* 设置为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

返回的对象的引用计数为零，因此立即调用 `AddRef` ，然后在完成后使用 `Release` 释放对象指针上的引用。

如果不需要直接访问对象，但仍想要创建一个不带开销的新对象， `CoCreateInstance` 请改用 [CComCoClass：： CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) 。

## <a name="ccomaggobjectfinalconstruct"></a><a name="finalconstruct"></a> CComAggObject：： FinalConstruct

在对象构造的最后阶段调用，此方法对 [m_contained](#m_contained) 成员执行任何最终初始化。

```
HRESULT FinalConstruct();
```

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ccomaggobjectfinalrelease"></a><a name="finalrelease"></a> CComAggObject：： FinalRelease

在对象销毁期间调用，此方法释放 [m_contained](#m_contained) 成员。

```cpp
void FinalRelease();
```

## <a name="ccomaggobjectm_contained"></a><a name="m_contained"></a> CComAggObject：： m_contained

派生自类的 [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) 对象。

```
CComContainedObject<contained> m_contained;
```

### <a name="parameters"></a>parameters

*独立*<br/>
中从 [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) 或 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)派生的类，以及要在对象上支持的任何其他接口。

### <a name="remarks"></a>备注

所有 `IUnknown` 调用 `m_contained` 都委托给外部未知。

## <a name="ccomaggobjectqueryinterface"></a><a name="queryinterface"></a> CComAggObject：： QueryInterface

检索指向所请求的接口的指针。

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

### <a name="remarks"></a>备注

如果请求的接口为 `IUnknown` ，则 `QueryInterface` 返回一个指向聚合对象自身的指针 `IUnknown` ，并递增引用计数。 否则，此方法将通过成员 m_contained 来查询接口 `CComContainedObject` 。 [](#m_contained)

## <a name="ccomaggobjectrelease"></a><a name="release"></a> CComAggObject：： Release

递减聚合对象上的引用计数。

```
STDMETHOD_(ULONG, Release)();
```

### <a name="return-value"></a>返回值

在调试版本中，将 `Release` 返回一个值，该值对于诊断或测试可能很有用。 在非调试版本中， `Release` 始终返回0。

## <a name="see-also"></a>请参阅

[CComObject 类](../../atl/reference/ccomobject-class.md)<br/>
[CComPolyObject 类](../../atl/reference/ccompolyobject-class.md)<br/>
[DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable)<br/>
[DECLARE_ONLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_only_aggregatable)<br/>
[DECLARE_NOT_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_not_aggregatable)<br/>
[类概述](../../atl/atl-class-overview.md)

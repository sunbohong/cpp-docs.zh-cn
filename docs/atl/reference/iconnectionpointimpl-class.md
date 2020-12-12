---
description: 了解详细信息： IConnectionPointImpl 类
title: IConnectionPointImpl 类
ms.date: 11/04/2016
f1_keywords:
- IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl
- ATLCOM/ATL::IConnectionPointImpl::Advise
- ATLCOM/ATL::IConnectionPointImpl::EnumConnections
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionInterface
- ATLCOM/ATL::IConnectionPointImpl::GetConnectionPointContainer
- ATLCOM/ATL::IConnectionPointImpl::Unadvise
- ATLCOM/ATL::IConnectionPointImpl::m_vec
helpviewer_keywords:
- connection points [C++], implementing
- IConnectionPointImpl class
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
ms.openlocfilehash: d87eb0821a3a48d171c196c891b5f5c7aacb9cdf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139576"
---
# <a name="iconnectionpointimpl-class"></a>IConnectionPointImpl 类

此类实现连接点。

## <a name="syntax"></a>语法

```
template<class T, const IID* piid, class CDV = CComDynamicUnkArray>
class ATL_NO_VTABLE IConnectionPointImpl : public _ICPLocator<piid>
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IConnectionPointImpl` 。

*piid*<br/>
一个指针，指向由连接点对象表示的接口的 IID。

*CDV*<br/>
管理连接的类。 默认值为 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)，这允许无限制的连接。 你还可以使用 [CComUnkArray](../../atl/reference/ccomunkarray-class.md)，它指定固定数目的连接。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IConnectionPointImpl：： Advise](#advise)|建立连接点和接收器之间的连接。|
|[IConnectionPointImpl::EnumConnections](#enumconnections)|创建一个枚举器，用于循环访问连接点的连接。|
|[IConnectionPointImpl::GetConnectionInterface](#getconnectioninterface)|检索连接点所表示的接口的 IID。|
|[IConnectionPointImpl::GetConnectionPointContainer](#getconnectionpointcontainer)|检索指向可连接对象的接口指针。|
|[IConnectionPointImpl::Unadvise](#unadvise)|终止先前通过建立的连接 `Advise` 。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[IConnectionPointImpl：： m_vec](#m_vec)|管理连接点的连接。|

## <a name="remarks"></a>备注

`IConnectionPointImpl` 实现一个连接点，它允许对象向客户端公开传出接口。 客户端在名为接收器的对象上实现此接口。

ATL 使用 [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) 实现可连接对象。 可连接对象中的每个连接点都代表一个由 *piid* 标识的传出接口。 类 *CDV* 管理连接点和接收器之间的连接。 每个连接都是通过 "cookie" 唯一标识的。

有关在 ATL 中使用连接点的详细信息，请参阅文章 [连接点](../../atl/atl-connection-points.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`_ICPLocator`

`IConnectionPointImpl`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="iconnectionpointimpladvise"></a><a name="advise"></a> IConnectionPointImpl：： Advise

建立连接点和接收器之间的连接。

```
STDMETHOD(Advise)(
    IUnknown* pUnkSink,
    DWORD* pdwCookie);
```

### <a name="remarks"></a>备注

使用 [Unadvise](#unadvise) 终止连接调用。

请参阅 Windows SDK 中的 [IConnectionPoint：： Advise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-advise) 。

## <a name="iconnectionpointimplenumconnections"></a><a name="enumconnections"></a> IConnectionPointImpl::EnumConnections

创建一个枚举器，用于循环访问连接点的连接。

```
STDMETHOD(EnumConnections)(IEnumConnections** ppEnum);
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IConnectionPoint：： EnumConnections](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-enumconnections) 。

## <a name="iconnectionpointimplgetconnectioninterface"></a><a name="getconnectioninterface"></a> IConnectionPointImpl::GetConnectionInterface

检索连接点所表示的接口的 IID。

```
STDMETHOD(GetConnectionInterface)(IID* piid2);
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IConnectionPoint：： GetConnectionInterface](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectioninterface) 。

## <a name="iconnectionpointimplgetconnectionpointcontainer"></a><a name="getconnectionpointcontainer"></a> IConnectionPointImpl::GetConnectionPointContainer

检索指向可连接对象的接口指针。

```
STDMETHOD(GetConnectionPointContainer)(IConnectionPointContainer** ppCPC);
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IConnectionPoint：： GetConnectionPointContainer](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-getconnectionpointcontainer) 。

## <a name="iconnectionpointimplm_vec"></a><a name="m_vec"></a> IConnectionPointImpl：： m_vec

管理连接点对象和接收器之间的连接。

```
CDV m_vec;
```

### <a name="remarks"></a>备注

默认情况下， `m_vec` 的类型为 [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)。

## <a name="iconnectionpointimplunadvise"></a><a name="unadvise"></a> IConnectionPointImpl::Unadvise

终止先前通过 [Advise](#advise)建立的连接。

```
STDMETHOD(Unadvise)(DWORD dwCookie);
```

### <a name="remarks"></a>备注

请参阅 Windows SDK 中的 [IConnectionPoint：： Unadvise](/windows/win32/api/ocidl/nf-ocidl-iconnectionpoint-unadvise) 。

## <a name="see-also"></a>请参阅

[IConnectionPoint](/windows/win32/api/ocidl/nn-ocidl-iconnectionpoint)<br/>
[类概述](../../atl/atl-class-overview.md)

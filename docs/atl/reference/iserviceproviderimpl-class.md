---
description: 了解详细信息： IServiceProviderImpl 类
title: IServiceProviderImpl 类
ms.date: 11/04/2016
f1_keywords:
- IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl
- ATLCOM/ATL::IServiceProviderImpl::QueryService
helpviewer_keywords:
- IServiceProviderImpl class
- IServiceProvider interface, ATL implementation
ms.assetid: 251254d3-c4ce-40d7-aee0-3d676d1d72f2
ms.openlocfilehash: 0cd9fab784fe8bffe420123129aa51c80c187890
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139147"
---
# <a name="iserviceproviderimpl-class"></a>IServiceProviderImpl 类

此类提供接口的默认实现 `IServiceProvider` 。

## <a name="syntax"></a>语法

```
template <class T>
class ATL_NO_VTABLE IServiceProviderImpl : public IServiceProvider
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IServiceProviderImpl` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IServiceProviderImpl：： QueryService](#queryservice)|创建或访问指定的服务，并将接口指针返回到服务的指定接口。|

## <a name="remarks"></a>备注

`IServiceProvider`接口定位由其 GUID 指定的服务，并返回服务上请求的接口的接口指针。 类 `IServiceProviderImpl` 提供此接口的默认实现。

`IServiceProviderImpl` 指定一种方法： [QueryService](#queryservice)，它创建或访问指定的服务，并将接口指针返回到服务的指定接口。

`IServiceProviderImpl` 使用服务映射，从 [BEGIN_SERVICE_MAP](service-map-macros.md#begin_service_map) 开始，以 [END_SERVICE_MAP](service-map-macros.md#end_service_map)结束。

服务映射包含两个条目： [SERVICE_ENTRY](service-map-macros.md#service_entry)，它指示对象支持的指定服务 ID (SID) ， [SERVICE_ENTRY_CHAIN](service-map-macros.md#service_entry_chain)并将调用 `QueryService` 链接到另一个对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

`IServiceProvider`

`IServiceProviderImpl`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="iserviceproviderimplqueryservice"></a><a name="queryservice"></a> IServiceProviderImpl：： QueryService

创建或访问指定的服务，并将接口指针返回到服务的指定接口。

```
STDMETHOD(QueryService)(
    REFGUID guidService,
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>parameters

*guidService*<br/>
中指向服务标识符 (SID) 的指针。

*riid*<br/>
中调用方要获取访问权限的接口的标识符。

*ppvObj*<br/>
弄指向所请求接口的间接指针。

### <a name="return-value"></a>返回值

返回的 HRESULT 值为下列值之一：

|返回值|含义|
|------------------|-------------|
|S_OK|已成功创建或检索服务。|
|E_INVALIDARG|一个或多个自变量无效。|
|E_OUTOFMEMORY|内存不足，无法创建服务。|
|E_UNEXPECTED|发生未知错误。|
|E_NOINTERFACE|请求的接口不是此服务的一部分，或者该服务是未知的。|

### <a name="remarks"></a>备注

`QueryService` 返回指向指定服务中所请求的接口的间接指针。 调用方负责在不再需要此指针时释放它。

调用时 `QueryService` ，会将服务标识符 () 并 ( *riid*) 传递接口标识符。 *GuidService* 指定要访问的服务， *riid* 会标识属于该服务的接口。 返回时，会收到指向接口的间接指针。

实现接口的对象还可以实现属于其他服务的接口。 考虑以下情况：

- 其中一些接口可能是可选的。 并非服务说明中定义的所有接口都必须存在于服务的每个实现或每个返回的对象上。

- 不同于对的调用 `QueryInterface` ，传递不同的服务标识符并不一定意味着返回不同的组件对象模型 (COM) 对象。

- 返回的对象可能包含不是该服务定义的一部分的其他接口。

两种不同的服务（如 SID_SMyService 和 SID_SYourService）都可以指定同一接口的使用，即使接口的实现在这两个服务之间可能没有任何共性。 这可行，因为对 `QueryService` (SID_SMyService、IID_IDispatch) 的调用返回的对象不同于 (SID_SYourService IID_IDispatch) `QueryService` 。 指定不同的服务标识符时，不会假定对象标识。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

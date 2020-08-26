---
title: 连接点全局函数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 1a648f49b0f3715fd322b1099dcebbf194f57a10
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833525"
---
# <a name="connection-point-global-functions"></a>连接点全局函数

这些函数提供对连接点和接收器映射的支持。

> [!IMPORTANT]
> 下表中列出的函数不能用于在 Windows 运行时中执行的应用程序。

|函数|说明|
|-|-|
|[AtlAdvise](#atladvise)|在对象的连接点和客户端的接收器间创建连接。|
|[AtlUnadvise](#atlunadvise)|终止通过建立的连接 `AtlAdvise` 。|
|[AtlAdviseSinkMap](#atladvisesinkmap)|事件接收器映射中的建议或 unadvises 条目。|

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="atladvise"></a><a name="atladvise"></a> AtlAdvise

在对象的连接点和客户端的接收器间创建连接。

> [!IMPORTANT]
> 此函数不能用于在 Windows 运行时中执行的应用程序。

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>参数

*pUnkCP*<br/>
中指向客户端要连接到的对象的的指针 `IUnknown` 。

*pUnk*<br/>
中指向客户端的的指针 `IUnknown` 。

*iid*<br/>
中连接点的 GUID。 通常，这与连接点管理的输出接口相同。

*pdw*<br/>
弄一个指针，指向用于唯一标识连接的 cookie。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

接收器实现连接点支持的输出接口。 客户端使用 *pdw* cookie 来删除连接，方法是将连接传递给 [AtlUnadvise](#atlunadvise)。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

## <a name="atlunadvise"></a><a name="atlunadvise"></a> AtlUnadvise

终止通过 [AtlAdvise](#atladvise)建立的连接。

> [!IMPORTANT]
> 此函数不能用于在 Windows 运行时中执行的应用程序。

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>参数

*pUnkCP*<br/>
中指向 `IUnknown` 客户端连接到的对象的的指针。

*iid*<br/>
中连接点的 GUID。 通常，这与连接点管理的输出接口相同。

*dw*<br/>
中用于唯一标识连接的 cookie。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

## <a name="atladvisesinkmap"></a><a name="atladvisesinkmap"></a> AtlAdviseSinkMap

调用此函数可在对象的接收器事件映射中建议或不建议所有条目。

> [!IMPORTANT]
> 此函数不能用于在 Windows 运行时中执行的应用程序。

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>参数

*五*<br/>
中指向包含接收器映射的对象的指针。

*bAdvise*<br/>
中如果建议所有接收项，则为 TRUE;如果所有接收器条目都是 unadvised，则为 FALSE。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>请参阅

[函数](../../atl/reference/atl-functions.md)<br/>
[连接点宏](../../atl/reference/connection-point-macros.md)

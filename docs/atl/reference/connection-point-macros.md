---
title: 连接点宏
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::BEGIN_CONNECTION_POINT_MAP
- atlcom/ATL::END_CONNECTION_POINT_MAP
helpviewer_keywords:
- connection points [C++], macros
ms.assetid: cc3a6dd3-5538-45df-b027-1f34963c31e5
ms.openlocfilehash: 6c716ad85ecb458b4be418a7e8554687dd19f3d8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833512"
---
# <a name="connection-point-macros"></a>连接点宏

这些宏定义连接点映射和条目。

|宏|描述|
|-|-|
|[BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map)|标记连接点映射项的开头。|
|[CONNECTION_POINT_ENTRY](#connection_point_entry)|将连接点输入到映射中。|
|[CONNECTION_POINT_ENTRY_P](#connection_point_entry)|  (Visual Studio 2017) 类似于 CONNECTION_POINT_ENTRY，但采用指向 iid 的指针。|
|[END_CONNECTION_POINT_MAP](#end_connection_point_map)|标记连接点映射项的结尾。|

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="begin_connection_point_map"></a><a name="begin_connection_point_map"></a> BEGIN_CONNECTION_POINT_MAP

标记连接点映射项的开头。

```
BEGIN_CONNECTION_POINT_MAP(x)
```

### <a name="parameters"></a>参数

*x*<br/>
中包含连接点的类的名称。

### <a name="remarks"></a>注解

启动连接点映射与 BEGIN_CONNECTION_POINT_MAP 宏，为每个连接点添加包含 [CONNECTION_POINT_ENTRY](#connection_point_entry) 宏的条目，然后用 [END_CONNECTION_POINT_MAP](#end_connection_point_map) 宏完成映射。

有关 ATL 中的连接点的详细信息，请参阅文章 [连接点](../../atl/atl-connection-points.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#101](../../atl/codesnippet/cpp/connection-point-macros_1.h)]

## <a name="connection_point_entry-and-connection_point_entry_p"></a><a name="connection_point_entry"></a> CONNECTION_POINT_ENTRY 和 CONNECTION_POINT_ENTRY_P

输入指定接口到连接点映射的连接点，以便可以访问该连接点。

```
CONNECTION_POINT_ENTRY(iid)
CONNECTION_POINT_ENTRY_P(piid) // (Visual Studio 2017)
```

### <a name="parameters"></a>参数

*iid*<br/>
中要添加到连接点映射的接口的 GUID。

*piid*<br/>
中指向 adde 接口的 GUID 的指针。

### <a name="remarks"></a>注解

[IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md)使用映射中的连接点条目。 包含连接点映射的类必须继承自 `IConnectionPointContainerImpl` 。

启动连接点映射与 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) 宏，为每个连接点添加包含 CONNECTION_POINT_ENTRY 宏的条目，然后用 [END_CONNECTION_POINT_MAP](#end_connection_point_map) 宏完成映射。

有关 ATL 中的连接点的详细信息，请参阅文章 [连接点](../../atl/atl-connection-points.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#120](../../atl/codesnippet/cpp/connection-point-macros_2.h)]

## <a name="end_connection_point_map"></a><a name="end_connection_point_map"></a> END_CONNECTION_POINT_MAP

标记连接点映射项的结尾。

```
END_CONNECTION_POINT_MAP()
```

### <a name="remarks"></a>注解

启动连接点映射与 [BEGIN_CONNECTION_POINT_MAP](#begin_connection_point_map) 宏，为每个连接点添加包含 [CONNECTION_POINT_ENTRY](#connection_point_entry) 宏的条目，然后用 END_CONNECTION_POINT_MAP 宏完成映射。

有关 ATL 中的连接点的详细信息，请参阅文章 [连接点](../../atl/atl-connection-points.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#128](../../atl/codesnippet/cpp/connection-point-macros_3.h)]

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)<br/>
[连接点全局函数](../../atl/reference/connection-point-global-functions.md)

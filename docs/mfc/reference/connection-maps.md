---
title: 连接映射
ms.date: 11/04/2016
helpviewer_keywords:
- connection maps
ms.assetid: 1f25a9bc-6d09-4614-99cf-dc38e8ddfa73
ms.openlocfilehash: 517017e9e60b86e96daa24f7822538e91c609fb4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841410"
---
# <a name="connection-maps"></a>连接映射

OLE 控件能够向其他应用程序公开接口。 这些接口仅允许从容器到该控件的访问。 如果某个 OLE 控件需要访问其他 OLE 对象的外部接口，则必须建立连接点。 此连接点允许控制外部调度映射（如事件映射或通知函数）的传出访问。

Microsoft 基础类库提供支持连接点的编程模型。 在此模型中，使用 "连接映射" 为 OLE 控件指定接口或连接点。 对于每个连接点，连接映射包含一个宏。 有关连接映射的详细信息，请参阅 [CConnectionPoint](../../mfc/reference/cconnectionpoint-class.md) 类。

通常，控件将仅支持两个连接点：一个用于事件，一个用于属性通知。 这些是由基类实现的 `COleControl` ，控件编写器不需要额外的工作。 您要在类中实现的任何其他连接点必须手动添加。 为了支持连接映射和点，MFC 提供了以下宏：

### <a name="connection-map-declaration-and-demarcation"></a>连接映射声明和分界

|名称|说明|
|-|-|
|[BEGIN_CONNECTION_PART](#begin_connection_part)|声明一个实现附加连接点的嵌入类， (必须在类声明) 中使用。|
|[END_CONNECTION_PART](#end_connection_part)|结束连接点的声明 (必须在类声明) 中使用。|
|[CONNECTION_IID](#connection_iid)|指定控件连接点的接口 ID。|
|[DECLARE_CONNECTION_MAP](#declare_connection_map)|声明连接映射将用于类 (必须在类声明) 中使用。|
|[BEGIN_CONNECTION_MAP](#begin_connection_map)|开始定义连接映射， (必须在类实现) 中使用。|
|[END_CONNECTION_MAP](#end_connection_map)|结束连接映射的定义 (必须在类实现) 中使用。|
|[CONNECTION_PART](#connection_part)|指定控件的连接映射中的连接点。|

以下函数帮助接收器使用连接点建立和断开连接：

### <a name="initializationtermination-of-connection-points"></a>连接点的初始化/终止

|名称|说明|
|-|-|
|[AfxConnectionAdvise](#afxconnectionadvise)|在源和接收器之间建立连接。|
|[AfxConnectionUnadvise](#afxconnectionunadvise)|中断源和接收器之间的连接。|

## <a name="begin_connection_part"></a><a name="begin_connection_part"></a> BEGIN_CONNECTION_PART

使用 BEGIN_CONNECTION_PART 宏来开始定义除事件和属性通知连接点之外的其他连接点。

```
BEGIN_CONNECTION_PART(theClass, localClass)
```

### <a name="parameters"></a>参数

*类*<br/>
指定其连接点为的控件类的名称。

*localClass*<br/>
指定实现连接点的局部类的名称。

### <a name="remarks"></a>注解

在定义类的成员函数的声明 ( .h) 文件中，用 BEGIN_CONNECTION_PART 宏启动连接点，然后添加 CONNECTION_IID 宏以及任何其他要实现的成员函数，并通过 END_CONNECTION_PART 宏完成连接点映射。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="end_connection_part"></a><a name="end_connection_part"></a> END_CONNECTION_PART

结束连接点的声明。

```
END_CONNECTION_PART(localClass)
```

### <a name="parameters"></a>参数

*localClass*<br/>
指定实现连接点的局部类的名称。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="connection_iid"></a><a name="connection_iid"></a> CONNECTION_IID

在 "BEGIN_CONNECTION_PART" 和 "END_CONNECTION_PART" 宏之间使用，定义 OLE 控件支持的连接点的接口 ID。

```
CONNECTION_IID(iid)
```

### <a name="parameters"></a>参数

*iid*<br/>
接口的接口 ID 由连接点调用。

### <a name="remarks"></a>注解

*Iid*参数是一个接口 ID，用于标识连接点在其连接的接收器上调用的接口。 例如：

[!code-cpp[NVC_MFCConnectionPoints#10](../../mfc/codesnippet/cpp/connection-maps_1.h)]

指定调用 `ISinkInterface` 接口的连接点。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="declare_connection_map"></a><a name="declare_connection_map"></a> DECLARE_CONNECTION_MAP

程序中的每个 `COleControl` 派生类可提供一个连接映射来指定控件支持的额外的连接点。

```
DECLARE_CONNECTION_MAP()
```

### <a name="remarks"></a>注解

如果控件支持其他点，请在类声明的末尾使用 DECLARE_CONNECTION_MAP 宏。 然后，在定义类的成员函数的 .cpp 文件中，使用 BEGIN_CONNECTION_MAP 宏，CONNECTION_PART 控件的每个连接点的宏，并使用 END_CONNECTION_MAP 宏来声明连接映射的结尾。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="begin_connection_map"></a><a name="begin_connection_map"></a> BEGIN_CONNECTION_MAP

程序中的每个 `COleControl` 派生类均可提供连接映射来指定控件将支持的连接点。

```
BEGIN_CONNECTION_MAP(theClass, theBase)
```

### <a name="parameters"></a>参数

*类*<br/>
指定连接映射所属的控件类的名称。

*theBase*<br/>
指定 *类*的基类的名称。

### <a name="remarks"></a>注解

在实现 (。CPP) 文件，该文件定义类的成员函数，使用 BEGIN_CONNECTION_MAP 宏启动连接映射，然后使用 [CONNECTION_PART](#connection_part) 宏为每个连接点添加宏条目。 最后，通过 [END_CONNECTION_MAP](#end_connection_map) 宏来完成连接映射。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="end_connection_map"></a><a name="end_connection_map"></a> END_CONNECTION_MAP

结束连接映射的定义。

```
END_CONNECTION_MAP()
```

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="connection_part"></a><a name="connection_part"></a> CONNECTION_PART

将 OLE 控件的连接点映射到特定的接口 ID。

```
CONNECTION_PART(theClass, iid, localClass)
```

### <a name="parameters"></a>参数

*类*<br/>
指定其连接点为的控件类的名称。

*iid*<br/>
接口的接口 ID 由连接点调用。

*localClass*<br/>
指定实现连接点的局部类的名称。

### <a name="remarks"></a>注解

例如：

[!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/cpp/connection-maps_2.cpp)]

使用连接点实现连接映射，该连接点调用 `IID_ISinkInterface` 接口。

### <a name="requirements"></a>要求

  **标头** afxdisp.h&gt

## <a name="afxconnectionadvise"></a><a name="afxconnectionadvise"></a> AfxConnectionAdvise

调用此函数可在源（由 *pUnkSrc*指定）和由 *pUnkSink*指定的接收器之间建立连接。

```
BOOL AFXAPI AfxConnectionAdvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD FAR* pdwCookie);
```

### <a name="parameters"></a>参数

*pUnkSrc*<br/>
指向调用接口的对象的指针。

*pUnkSink*<br/>
指向实现接口的对象的指针。

*iid*<br/>
连接的接口 ID。

*bRefCount*<br/>
TRUE 表示创建连接应导致 *pUnkSink* 的引用计数递增。 FALSE 指示不应递增引用计数。

*pdwCookie*<br/>
一个指针，指向返回连接标识符的 DWORD。 断开连接时，此值应作为 *dwCookie* 参数传递给 `AfxConnectionUnadvise` 。

### <a name="return-value"></a>返回值

如果建立了连接，则为非零值;否则为0。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCConnectionPoints#8](../../mfc/codesnippet/cpp/connection-maps_3.cpp)]

### <a name="requirements"></a>要求

**标头：** afxctl。h

## <a name="afxconnectionunadvise"></a><a name="afxconnectionunadvise"></a> AfxConnectionUnadvise

调用此函数可断开由 *pUnkSrc*指定的源与 *pUnkSink*指定的接收器之间的连接。

```
BOOL AFXAPI AfxConnectionUnadvise(
    LPUNKNOWN pUnkSrc,
    REFIID iid,
    LPUNKNOWN pUnkSink,
    BOOL bRefCount,
    DWORD dwCookie);
```

### <a name="parameters"></a>参数

*pUnkSrc*<br/>
指向调用接口的对象的指针。

*pUnkSink*<br/>
指向实现接口的对象的指针。

*iid*<br/>
连接点接口的接口 ID。

*bRefCount*<br/>
如果为 TRUE，则表示断开连接连接应导致减少 *pUnkSink* 的引用计数。 FALSE 指示不应减少引用计数。

*dwCookie*<br/>
返回的连接标识符 `AfxConnectionAdvise` 。

### <a name="return-value"></a>返回值

如果断开连接，则为非零值;否则为0。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCConnectionPoints#9](../../mfc/codesnippet/cpp/connection-maps_4.cpp)]

### <a name="requirements"></a>要求

**标头：** afxctl。h

## <a name="see-also"></a>另请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)

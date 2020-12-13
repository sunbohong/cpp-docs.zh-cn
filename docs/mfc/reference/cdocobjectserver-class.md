---
description: 了解详细信息： CDocObjectServer 类
title: CDocObjectServer 类
ms.date: 09/12/2018
f1_keywords:
- CDocObjectServer
- AFXDOCOB/CDocObjectServer
- AFXDOCOB/CDocObjectServer::CDocObjectServer
- AFXDOCOB/CDocObjectServer::ActivateDocObject
- AFXDOCOB/CDocObjectServer::OnActivateView
- AFXDOCOB/CDocObjectServer::OnApplyViewState
- AFXDOCOB/CDocObjectServer::OnSaveViewState
helpviewer_keywords:
- CDocObjectServer [MFC], CDocObjectServer
- CDocObjectServer [MFC], ActivateDocObject
- CDocObjectServer [MFC], OnActivateView
- CDocObjectServer [MFC], OnApplyViewState
- CDocObjectServer [MFC], OnSaveViewState
ms.assetid: 18cd0dff-0616-4472-b8d9-66c081bc383a
ms.openlocfilehash: 5a87363fef66a4819fc8efd504da96398cf3c89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184941"
---
# <a name="cdocobjectserver-class"></a>CDocObjectServer 类

实现将常规 `COleDocument` 服务器接入完整 DocObject 服务器所需的其他 OLE 接口： `IOleDocument`、 `IOleDocumentView`、 `IOleCommandTarget`和 `IPrint`。

## <a name="syntax"></a>语法

```
class CDocObjectServer : public CCmdTarget
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDocObjectServer：： CDocObjectServer](#cdocobjectserver)|构造 `CDocObjectServer` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDocObjectServer：： ActivateDocObject](#activatedocobject)|激活文档对象服务器，但不显示它。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CDocObjectServer：： OnActivateView](#onactivateview)|显示 DocObject 视图。|
|[CDocObjectServer：： OnApplyViewState](#onapplyviewstate)|还原 DocObject 视图的状态。|
|[CDocObjectServer：： OnSaveViewState](#onsaveviewstate)|保存 DocObject 视图的状态。|

## <a name="remarks"></a>备注

`CDocObjectServer` 派生自 `CCmdTarget` ，并与结合使用 `COleServerDoc` 来公开接口。

DocObject 服务器文档可以包含 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md) 对象，这些对象表示用于 DocObject 项的服务器接口。

若要自定义 DocObject 服务器，请从派生您自己的类， `CDocObjectServer` 并重写其视图设置函数、 [OnActivateView](#onactivateview)、 [OnApplyViewState](#onapplyviewstate)和 [OnSaveViewState](#onsaveviewstate)。 你将需要提供类的新实例，以响应框架调用。

有关 DocObjects 的详细信息，请参阅 *MFC 参考* 中的 [CDocObjectServerItem](../../mfc/reference/cdocobjectserveritem-class.md)和 [COleCmdUI](../../mfc/reference/colecmdui-class.md) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocObjectServer`

## <a name="requirements"></a>要求

**标头：** afxdocob

## <a name="cdocobjectserveractivatedocobject"></a><a name="activatedocobject"></a> CDocObjectServer：： ActivateDocObject

调用此函数可激活 (但不显示文档对象服务器) 。

```cpp
void ActivateDocObject();
```

### <a name="remarks"></a>备注

`ActivateDocObject` 调用 `IOleDocumentSite` 的 `ActivateMe` 方法，但不显示视图，因为它会等待有关如何设置和显示视图的特定说明（在调用 [CDocObjectServer：： OnActivateView](#onactivateview)中提供）。

一起 `ActivateDocObject` `OnActivateView` 激活并显示 DocObject 视图。 DocObject 激活不同于其他类型的 OLE 就地激活。 DocObject activation 会绕过显示就地影线边框和对象修饰 (例如调整大小图) 、忽略对象范围函数，以及在视图矩形内绘制滚动条，而不是像在正常就地激活) 中绘制 (它们。

## <a name="cdocobjectservercdocobjectserver"></a><a name="cdocobjectserver"></a> CDocObjectServer：： CDocObjectServer

构造并初始化一个 `CDocObjectServer` 对象。

```
explicit CDocObjectServer(
    COleServerDoc* pOwner,
    LPOLEDOCUMENTSITE pDocSite = NULL);
```

### <a name="parameters"></a>parameters

*pOwner*<br/>
指向客户端站点文档的指针，该文档是 DocObject 服务器的客户端。

*pDocSite*<br/>
指向 `IOleDocumentSite` 容器实现的接口的指针。

### <a name="remarks"></a>备注

当 DocObject 处于活动状态时，客户端站点 OLE 界面 ( `IOleDocumentSite`) 将允许 DocObject 服务器与其 (容器) 的客户端通信。 激活 DocObject 服务器后，它会首先检查容器是否实现了 `IOleDocumentSite` 接口。 如果是这样，则会调用 [COleServerDoc：： GetDocObjectServer](../../mfc/reference/coleserverdoc-class.md#getdocobjectserver) 来查看容器是否支持 DocObjects。 默认情况下， `GetDocObjectServer` 返回 NULL。 必须重写 `COleServerDoc::GetDocObjectServer` 以构造新的 `CDocObjectServer` 对象或自己的派生对象，并将指向 `COleServerDoc` 容器及其接口的指针 `IOleDocumentSite` 作为构造函数的参数。

## <a name="cdocobjectserveronactivateview"></a><a name="onactivateview"></a> CDocObjectServer：： OnActivateView

调用此函数以显示 DocObject 视图。

```
virtual HRESULT OnActivateView();
```

### <a name="return-value"></a>返回值

返回一个错误或警告值。 默认情况下，如果成功，则返回 NOERROR;否则，E_FAIL。

### <a name="remarks"></a>备注

此函数创建一个就地框架窗口，在视图中绘制滚动条，设置服务器与其容器共享的菜单，添加框架控件，设置活动对象，最后显示就地框架窗口并设置焦点。

## <a name="cdocobjectserveronapplyviewstate"></a><a name="onapplyviewstate"></a> CDocObjectServer：： OnApplyViewState

重写此函数以还原 DocObject 视图的状态。

```
virtual void OnApplyViewState(CArchive& ar);
```

### <a name="parameters"></a>parameters

*ar*<br/>
`CArchive`要从中序列化视图状态的对象。

### <a name="remarks"></a>备注

当视图在其实例化后第一次显示时，将调用此函数。 `OnApplyViewState` 指示视图根据 `CArchive` 以前使用 [OnSaveViewState](#onsaveviewstate)保存的对象中的数据重新初始化自身。 视图必须验证对象中的数据， `CArchive` 因为容器不会尝试以任何方式解释视图状态数据。

你可以使用 `OnSaveViewState` 来存储特定于视图状态的持久性信息。 如果你重写 `OnSaveViewState` 来存储信息，你将希望重写 `OnApplyViewState` 以读取该信息并在新激活时将其应用到你的视图。

## <a name="cdocobjectserveronsaveviewstate"></a><a name="onsaveviewstate"></a> CDocObjectServer：： OnSaveViewState

重写此函数以保存有关 DocObject 视图的其他状态信息。

```
virtual void OnSaveViewState(CArchive& ar);
```

### <a name="parameters"></a>parameters

*ar*<br/>
`CArchive`视图状态序列化到的对象。

### <a name="remarks"></a>备注

你的状态可能包括视图类型、缩放系数、插入和选择点等属性。 容器通常会在停用视图之前调用此函数。 稍后可以通过 [OnApplyViewState](#onapplyviewstate)还原已保存状态。

你可以使用 `OnSaveViewState` 来存储特定于视图状态的持久性信息。 如果你重写 `OnSaveViewState` 来存储信息，你将希望重写 `OnApplyViewState` 以读取该信息并在新激活时将其应用到你的视图。

## <a name="see-also"></a>请参阅

[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDocObjectServerItem 类](../../mfc/reference/cdocobjectserveritem-class.md)

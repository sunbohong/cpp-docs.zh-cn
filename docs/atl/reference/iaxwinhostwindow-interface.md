---
description: 了解详细信息： IAxWinHostWindow 接口
title: IAxWinHostWindow 接口
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindow
- ATLIFACE/ATL::IAxWinHostWindow
- ATLIFACE/ATL::AttachControl
- ATLIFACE/ATL::CreateControl
- ATLIFACE/ATL::CreateControlEx
- ATLIFACE/ATL::QueryControl
- ATLIFACE/ATL::SetExternalDispatch
- ATLIFACE/ATL::SetExternalUIHandler
helpviewer_keywords:
- IAxWinHostWindow interface
ms.assetid: 9821c035-cd52-4c46-b58a-9278064f09b4
ms.openlocfilehash: 86cccd2b9ae19d5020cd1cf7ff2f0aff8759060e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139706"
---
# <a name="iaxwinhostwindow-interface"></a>IAxWinHostWindow 接口

此接口提供用于操作控件及其宿主对象的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
interface IAxWinHostWindow : IUnknown
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|描述|
|-|-|
|[AttachControl](#attachcontrol)|将现有控件附加到宿主对象。|
|[CreateControl](#createcontrol)|创建一个控件，并将其附加到宿主对象。|
|[CreateControlEx](#createcontrolex)|创建一个控件，将其附加到宿主对象，并根据需要设置一个事件处理程序。|
|[QueryControl](#querycontrol)|返回一个指向所承载控件的接口指针。|
|[SetExternalDispatch](#setexternaldispatch)|设置外部 `IDispatch` 接口。|
|[SetExternalUIHandler](#setexternaluihandler)|设置外部 `IDocHostUIHandlerDispatch` 接口。|

## <a name="remarks"></a>备注

此接口由 ATL 的 ActiveX 控件宿主对象公开。 调用此接口上的方法，创建控件并/或者将其附加到宿主对象，以从托管控件获取接口，或设置外部调度接口或 UI 处理程序，以便在承载 Web 浏览器时使用。

## <a name="requirements"></a>要求

此接口的定义以 IDL 或 c + + 形式提供，如下所示。

|定义类型|文件|
|---------------------|----------|
|.IDL|ATLIFace .idl|
|C++|ATLIFace 也包含在 Atlbase.h 中 () |

## <a name="iaxwinhostwindowattachcontrol"></a><a name="attachcontrol"></a> IAxWinHostWindow::AttachControl

使用 *hWnd* 标识的窗口将现有 (和之前初始化的) 控件附加到宿主对象。

```
STDMETHOD(AttachControl)(IUnknown* pUnkControl, HWND hWnd);
```

### <a name="parameters"></a>parameters

*pUnkControl*<br/>
中指向要 `IUnknown` 附加到宿主对象的控件接口的指针。

*hWnd*<br/>
中用于承载的窗口的句柄。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinhostwindowcreatecontrol"></a><a name="createcontrol"></a> IAxWinHostWindow：： CreateControl

创建一个控件，对其进行初始化，并将其托管在由 *hWnd* 标识的窗口中。

```
STDMETHOD(CreateControl)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream);
```

### <a name="parameters"></a>parameters

*lpTricsData*<br/>
中标识要创建的控件的字符串。 可以是 CLSID (必须包括 MSHTML) 、ProgID、URL 或原始 HTML (，并以 **MSHTML：) 为** 前缀。

*hWnd*<br/>
中用于承载的窗口的句柄。

*pStream*<br/>
中包含控件的初始化数据的流的接口指针。 可以为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

此窗口将由公开此接口的主机对象进行细分，以便可以将消息反射到该控件，其他容器功能将起作用。

调用此方法等效于调用 [IAxWinHostWindow：： CreateControlEx](#createcontrolex)。

若要创建许可的 ActiveX 控件，请参阅 [IAxWinHostWindowLic：： CreateControlLic](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)。

## <a name="iaxwinhostwindowcreatecontrolex"></a><a name="createcontrolex"></a> IAxWinHostWindow::CreateControlEx

创建 ActiveX 控件，对其进行初始化，并在指定窗口中承载它，类似于 [IAxWinHostWindow：： CreateControl](#createcontrol)。

```
STDMETHOD(CreateControlEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise);
```

### <a name="parameters"></a>parameters

*lpTricsData*<br/>
中标识要创建的控件的字符串。 可以是 CLSID (必须包括以 **MSHTML：**) 为前缀的大括号) 、PROGID、URL 或原始 HTML (。

*hWnd*<br/>
中用于承载的窗口的句柄。

*pStream*<br/>
中包含控件的初始化数据的流的接口指针。 可以为 NULL。

*ppUnk*<br/>
弄将接收创建的控件接口的指针的地址 `IUnknown` 。 可以为 NULL。

*riidAdvise*<br/>
中所包含对象上的传出接口的接口标识符。 可以 IID_NULL。

*punkAdvise*<br/>
中一个指针，指向要 `IUnknown` 连接到指定的所包含对象上的连接点的接收器对象的接口 `iidSink` 。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

与 `CreateControl` 方法不同， `CreateControlEx` 还允许您接收指向新创建的控件的接口指针，并设置一个事件接收器来接收由控件触发的事件。

若要创建许可的 ActiveX 控件，请参阅 [IAxWinHostWindowLic：： CreateControlLicEx](../../atl/reference/iaxwinhostwindowlic-interface.md#createcontrollicex)。

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a> IAxWinHostWindow::QueryControl

返回由托管控件提供的指定接口指针。

```
STDMETHOD(QueryControl)(
    REFIID riid,
    void** ppvObject);
```

### <a name="parameters"></a>parameters

*riid*<br/>
中正在请求的控件的接口 ID。

*ppvObject*<br/>
弄将接收所创建控件的指定接口的指针的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinhostwindowsetexternaldispatch"></a><a name="setexternaldispatch"></a> IAxWinHostWindow::SetExternalDispatch

设置外部调度接口，可通过 [IDocHostUIHandlerDispatch：： GetExternal](../../atl/reference/idochostuihandlerdispatch-interface.md) 方法用于包含的控件。

```
STDMETHOD(SetExternalDispatch)(IDispatch* pDisp);
```

### <a name="parameters"></a>parameters

*pDisp*<br/>
中指向接口的指针 `IDispatch` 。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinhostwindowsetexternaluihandler"></a><a name="setexternaluihandler"></a> IAxWinHostWindow::SetExternalUIHandler

调用此函数可设置对象的外部 [IDocHostUIHandlerDispatch](../../atl/reference/idochostuihandlerdispatch-interface.md) 接口 `CAxWindow` 。

```
STDMETHOD(SetExternalUIHandler)(IDocHostUIHandlerDispatch* pDisp);
```

### <a name="parameters"></a>parameters

*pDisp*<br/>
中指向接口的指针 `IDocHostUIHandlerDispatch` 。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

此函数由控件 (（如 Web 浏览器控件) ，用于查询接口的宿主站点 `IDocHostUIHandlerDispatch` 。

## <a name="see-also"></a>请参阅

[IAxWinAmbientDispatch 接口](../../atl/reference/iaxwinambientdispatch-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)

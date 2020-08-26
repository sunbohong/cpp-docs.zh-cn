---
title: IAxWinAmbientDispatch 接口
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatch
- ATLIFACE/ATL::IAxWinAmbientDispatch
- ATLIFACE/ATL::get_AllowContextMenu
- ATLIFACE/ATL::get_AllowShowUI
- ATLIFACE/ATL::get_AllowWindowlessActivation
- ATLIFACE/ATL::get_BackColor
- ATLIFACE/ATL::get_DisplayAsDefault
- ATLIFACE/ATL::get_DocHostDoubleClickFlags
- ATLIFACE/ATL::get_DocHostFlags
- ATLIFACE/ATL::get_Font
- ATLIFACE/ATL::get_ForeColor
- ATLIFACE/ATL::get_LocaleID
- ATLIFACE/ATL::get_MessageReflect
- ATLIFACE/ATL::get_OptionKeyPath
- ATLIFACE/ATL::get_ShowGrabHandles
- ATLIFACE/ATL::get_ShowHatching
- ATLIFACE/ATL::get_UserMode
- ATLIFACE/ATL::put_AllowContextMenu
- ATLIFACE/ATL::put_AllowShowUI
- ATLIFACE/ATL::put_AllowWindowlessActivation
- ATLIFACE/ATL::put_BackColor
- ATLIFACE/ATL::put_DisplayAsDefault
- ATLIFACE/ATL::put_DocHostDoubleClickFlags
- ATLIFACE/ATL::put_DocHostFlags
- ATLIFACE/ATL::put_Font
- ATLIFACE/ATL::put_ForeColor
- ATLIFACE/ATL::put_LocaleID
- ATLIFACE/ATL::put_MessageReflect
- ATLIFACE/ATL::put_OptionKeyPath
- ATLIFACE/ATL::put_UserMode
helpviewer_keywords:
- IAxWinAmbientDispatch interface
ms.assetid: 55ba6f7b-7a3c-4792-ae47-c8a84b683ca9
ms.openlocfilehash: a53481a57676b5b4a253a3501d3536e5115907a7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833408"
---
# <a name="iaxwinambientdispatch-interface"></a>IAxWinAmbientDispatch 接口

此接口提供用于指定承载的控件或容器的特性的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
interface IAxWinAmbientDispatch : IDispatch
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|说明|
|-|-|
|[get_AllowContextMenu](#get_allowcontextmenu)|`AllowContextMenu`属性指定是否允许寄宿控件显示其自己的上下文菜单。|
|[get_AllowShowUI](#get_allowshowui)|`AllowShowUI`属性指定是否允许托管控件显示其自己的用户界面。|
|[get_AllowWindowlessActivation](#get_allowwindowlessactivation)|`AllowWindowlessActivation`属性指定容器是否允许无窗口激活。|
|[get_BackColor](#get_backcolor)|`BackColor`属性指定容器的环境背景色。|
|[get_DisplayAsDefault](#get_displayasdefault)|`DisplayAsDefault` 是一个环境属性，它允许控件确定其是否为默认控件。|
|[get_DocHostDoubleClickFlags](#get_dochostdoubleclickflags)|`DocHostDoubleClickFlags`属性指定应在响应双击时进行的操作。|
|[get_DocHostFlags](#get_dochostflags)|`DocHostFlags`属性指定宿主对象的用户界面功能。|
|[get_Font](#get_font)|`Font`属性指定容器的环境字体。|
|[get_ForeColor](#get_forecolor)|`ForeColor`属性指定容器的环境前景色。|
|[get_LocaleID](#get_localeid)|`LocaleID`属性指定容器的环境区域设置 ID。|
|[get_MessageReflect](#get_messagereflect)|`MessageReflect`环境属性指定容器是否将消息反射到承载的控件。|
|[get_OptionKeyPath](#get_optionkeypath)|`OptionKeyPath`属性指定用户设置的注册表项路径。|
|[get_ShowGrabHandles](#get_showgrabhandles)|`ShowGrabHandles`环境属性允许控件发现它是否应该用抓取手柄来绘制自身。|
|[get_ShowHatching](#get_showhatching)|`ShowHatching`环境属性允许控件查明是否应绘制其自身的阴影。|
|[get_UserMode](#get_usermode)|`UserMode`属性指定容器的环境用户模式。|
|[put_AllowContextMenu](#put_allowcontextmenu)|`AllowContextMenu`属性指定是否允许寄宿控件显示其自己的上下文菜单。|
|[put_AllowShowUI](#put_allowshowui)|`AllowShowUI`属性指定是否允许托管控件显示其自己的用户界面。|
|[put_AllowWindowlessActivation](#put_allowwindowlessactivation)|`AllowWindowlessActivation`属性指定容器是否允许无窗口激活。|
|[put_BackColor](#put_backcolor)|`BackColor`属性指定容器的环境背景色。|
|[put_DisplayAsDefault](#put_displayasdefault)|`DisplayAsDefault` 是一个环境属性，它允许控件确定其是否为默认控件。|
|[put_DocHostDoubleClickFlags](#put_dochostdoubleclickflags)|`DocHostDoubleClickFlags`属性指定应在响应双击时进行的操作。|
|[put_DocHostFlags](#put_dochostflags)|`DocHostFlags`属性指定宿主对象的用户界面功能。|
|[put_Font](#put_font)|`Font`属性指定容器的环境字体。|
|[put_ForeColor](#put_forecolor)|`ForeColor`属性指定容器的环境前景色。|
|[put_LocaleID](#put_localeid)|`LocaleID`属性指定容器的环境区域设置 ID。|
|[put_MessageReflect](#put_messagereflect)|`MessageReflect`环境属性指定容器是否将消息反射到承载的控件。|
|[put_OptionKeyPath](#put_optionkeypath)|`OptionKeyPath`属性指定用户设置的注册表项路径。|
|[put_UserMode](#put_usermode)|`UserMode`属性指定容器的环境用户模式。|

## <a name="remarks"></a>注解

此接口由 ATL 的 ActiveX 控件宿主对象公开。 调用此接口上的方法，以设置承载控件可用的环境属性，或指定容器的行为的其他方面。 若要补充提供的属性 `IAxWinAmbientDispatch` ，请使用 [IAxWinAmbientDispatchEx](../../atl/reference/iaxwinambientdispatchex-interface.md)。

<xref:System.Windows.Forms.AxHost> 将尝试 `IAxWinAmbientDispatch` 从包含代码的类型库中加载和类型信息 `IAxWinAmbientDispatchEx` 。

如果要链接到 ATL90.dll， **AXHost** 将从 DLL 中的 typelib 加载类型信息。

有关更多详细信息，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/hosting-activex-controls-using-atl-axhost.md) 。

## <a name="requirements"></a>要求

此接口的定义以多种形式提供，如下表所示。

|定义类型|文件|
|---------------------|----------|
|.IDL|atliface .idl|
|类型库|ATL.dll|
|C++|atliface 也包含在 Atlbase.h 中 () |

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a> IAxWinAmbientDispatch：： get_AllowContextMenu

`AllowContextMenu`属性指定是否允许寄宿控件显示其自己的上下文菜单。

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>参数

*pbAllowContextMenu*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a> IAxWinAmbientDispatch：： get_AllowShowUI

`AllowShowUI`属性指定是否允许托管控件显示其自己的用户界面。

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>参数

*pbAllowShowUI*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a> IAxWinAmbientDispatch：： get_AllowWindowlessActivation

`AllowWindowlessActivation`属性指定容器是否允许无窗口激活。

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>参数

*pbAllowWindowless*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a> IAxWinAmbientDispatch：： get_BackColor

`BackColor`属性指定容器的环境背景色。

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>参数

*pclrBackground*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 COLOR_BTNFACE 或 COLOR_WINDOW 作为此属性的默认值 (具体取决于宿主窗口的父窗口是对话框还是不) 。

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a> IAxWinAmbientDispatch：： get_DisplayAsDefault

`DisplayAsDefault` 是一个环境属性，它允许控件确定其是否为默认控件。

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>参数

*pbDisplayAsDefault*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a> IAxWinAmbientDispatch：： get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`属性指定应在响应双击时进行的操作。

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>参数

*pdwDocHostDoubleClickFlags*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 DOCHOSTUIDBLCLK_DEFAULT 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a> IAxWinAmbientDispatch：： get_DocHostFlags

`DocHostFlags`属性指定宿主对象的用户界面功能。

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>参数

*pdwDocHostFlags*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 DOCHOSTUIFLAG_NO3DBORDER 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a> IAxWinAmbientDispatch：： get_Font

`Font`属性指定容器的环境字体。

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>参数

*pFont*<br/>
弄 `IFontDisp` 用于接收此属性的当前值的接口指针的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用默认的 GUI 字体或系统字体作为此属性的默认值。

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a> IAxWinAmbientDispatch：： get_ForeColor

`ForeColor`属性指定容器的环境前景色。

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>参数

*pclrForeground*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用系统窗口文本颜色作为此属性的默认值。

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a> IAxWinAmbientDispatch：： get_LocaleID

`LocaleID`属性指定容器的环境区域设置 ID。

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>参数

*plcidLocaleID*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用用户的默认区域设置作为此属性的默认值。

使用此方法，你可以发现环境 LocalID，即你的控件所使用的程序的 LocaleID。 知道 LocaleID 后，可以调用代码来加载资源文件或附属 DLL 中特定于区域设置的标题、错误消息文本等。

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a> IAxWinAmbientDispatch：： get_MessageReflect

`MessageReflect`环境属性指定容器是否将消息反射到承载的控件。

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>参数

*pbMessageReflect*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a> IAxWinAmbientDispatch：： get_OptionKeyPath

`OptionKeyPath`属性指定用户设置的注册表项路径。

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>参数

*pbstrOptionKeyPath*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a> IAxWinAmbientDispatch：： get_ShowGrabHandles

`ShowGrabHandles`环境属性允许控件发现它是否应该用抓取手柄来绘制自身。

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>参数

*pbShowGrabHandles*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现始终返回 VARIANT_FALSE 作为此属性的值。

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a> IAxWinAmbientDispatch：： get_ShowHatching

`ShowHatching`环境属性允许控件查明是否应绘制其自身的阴影。

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>参数

*pbShowHatching*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现始终返回 VARIANT_FALSE 作为此属性的值。

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a> IAxWinAmbientDispatch：： get_UserMode

`UserMode`属性指定容器的环境用户模式。

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>参数

*pbUserMode*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a> IAxWinAmbientDispatch：:p ut_AllowContextMenu

`AllowContextMenu`属性指定是否允许寄宿控件显示其自己的上下文菜单。

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>参数

*bAllowContextMenu*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a> IAxWinAmbientDispatch：:p ut_AllowShowUI

`AllowShowUI`属性指定是否允许托管控件显示其自己的用户界面。

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>参数

*bAllowShowUI*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a> IAxWinAmbientDispatch：:p ut_AllowWindowlessActivation

`AllowWindowlessActivation`属性指定容器是否允许无窗口激活。

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>参数

*bAllowWindowless*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a> IAxWinAmbientDispatch：:p ut_BackColor

`BackColor`属性指定容器的环境背景色。

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>参数

*clrBackground*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 COLOR_BTNFACE 或 COLOR_WINDOW 作为此属性的默认值 (具体取决于宿主窗口的父窗口是对话框还是不) 。

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a> IAxWinAmbientDispatch：:p ut_DisplayAsDefault

`DisplayAsDefault` 是一个环境属性，它允许控件确定其是否为默认控件。

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>参数

*bDisplayAsDefault*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a> IAxWinAmbientDispatch：:p ut_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`属性指定应在响应双击时进行的操作。

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>参数

*dwDocHostDoubleClickFlags*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 DOCHOSTUIDBLCLK_DEFAULT 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a> IAxWinAmbientDispatch：:p ut_DocHostFlags

`DocHostFlags`属性指定宿主对象的用户界面功能。

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>参数

*dwDocHostFlags*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 DOCHOSTUIFLAG_NO3DBORDER 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a> IAxWinAmbientDispatch：:p ut_Font

`Font`属性指定容器的环境字体。

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>参数

*pFont*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用默认的 GUI 字体或系统字体作为此属性的默认值。

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a> IAxWinAmbientDispatch：:p ut_ForeColor

`ForeColor`属性指定容器的环境前景色。

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>参数

*clrForeground*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用系统窗口文本颜色作为此属性的默认值。

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a> IAxWinAmbientDispatch：:p ut_LocaleID

`LocaleID`属性指定容器的环境区域设置 ID。

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>参数

*lcidLocaleID*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用用户的默认区域设置作为此属性的默认值。

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a> IAxWinAmbientDispatch：:p ut_MessageReflect

`MessageReflect`环境属性指定容器是否将消息反射到承载的控件。

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>参数

*bMessageReflect*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a> IAxWinAmbientDispatch：:p ut_OptionKeyPath

`OptionKeyPath`属性指定用户设置的注册表项路径。

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>参数

*bstrOptionKeyPath*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a> IAxWinAmbientDispatch：:p ut_UserMode

`UserMode`属性指定容器的环境用户模式。

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>参数

*bUserMode*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>注解

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="see-also"></a>另请参阅

[IAxWinAmbientDispatchEx 接口](../../atl/reference/iaxwinambientdispatchex-interface.md)<br/>
[IAxWinHostWindow 接口](../../atl/reference/iaxwinhostwindow-interface.md)<br/>
[CAxWindow::QueryHost](../../atl/reference/caxwindow-class.md#queryhost)<br/>
[AtlAxGetHost](composite-control-global-functions.md#atlaxgethost)

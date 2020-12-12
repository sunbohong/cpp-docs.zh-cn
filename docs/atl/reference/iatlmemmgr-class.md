---
description: 了解详细信息： IAtlMemMgr 类
title: IAtlMemMgr 类
ms.date: 11/04/2016
f1_keywords:
- IAtlMemMgr
- ATLMEM/ATL::IAtlMemMgr
- ATLMEM/ATL::Allocate
- ATLMEM/ATL::Free
- ATLMEM/ATL::GetSize
- ATLMEM/ATL::Reallocate
helpviewer_keywords:
- IAtlMemMgr class
- memory, managing
- memory, memory manager
ms.assetid: 18b2c569-25fe-4464-bdb6-3b1abef7154a
ms.openlocfilehash: 31f25c5fdb6a4e443bf011aac29620be8a4f13f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139745"
---
# <a name="iatlmemmgr-class"></a>IAtlMemMgr 类

此类表示内存管理器的接口。

## <a name="syntax"></a>语法

```
__interface __declspec(uuid("654F7EF5-CFDF-4df9-A450-6C6A13C622C0")) IAtlMemMgr
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|描述|
|-|-|
|[分配](#allocate)|调用此方法来分配内存块。|
|[免费](#free)|调用此方法可释放内存块。|
|[GetSize](#getsize)|调用此方法可检索已分配内存块的大小。|
|[给](#reallocate)|调用此方法可重新分配内存块。|

## <a name="remarks"></a>备注

此接口由 [CComHeap](../../atl/reference/ccomheap-class.md)、 [CCRTHeap](../../atl/reference/ccrtheap-class.md)、 [CLocalHeap](../../atl/reference/clocalheap-class.md)、 [CGlobalHeap](../../atl/reference/cglobalheap-class.md)或 [CWin32Heap](../../atl/reference/cwin32heap-class.md)实现。

> [!NOTE]
> 本地和全局堆函数比其他内存管理函数慢，并且不提供任何多个功能。 因此，新应用程序应使用 [堆函数](/windows/win32/Memory/heap-functions)。 这些都在 [CWin32Heap](../../atl/reference/cwin32heap-class.md) 类中提供。

## <a name="example"></a>示例

[!code-cpp[NVC_ATL_Utilities#94](../../atl/codesnippet/cpp/iatlmemmgr-class_1.cpp)]

## <a name="requirements"></a>要求

**标头：** atlmem

## <a name="iatlmemmgrallocate"></a><a name="allocate"></a> IAtlMemMgr：： Allocate

调用此方法来分配内存块。

```cpp
void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*nBytes*<br/>
新内存块中请求的字节数。

### <a name="return-value"></a>返回值

将指针返回到新分配内存块的起始位置。

### <a name="remarks"></a>备注

调用 [IAtlMemMgr：： Free](#free) 或 [IAtlMemMgr：：重新分配](#reallocate) 以释放此方法分配的内存。

### <a name="example"></a>示例

有关示例，请参阅 [IAtlMemMgr 概述](../../atl/reference/iatlmemmgr-class.md)。

## <a name="iatlmemmgrfree"></a><a name="free"></a> IAtlMemMgr：： Free

调用此方法可释放内存块。

```cpp
void Free(void* p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向此内存管理器以前分配的内存的指针。

### <a name="remarks"></a>备注

使用此方法可释放通过 [IAtlMemMgr：： Allocate](#allocate) 或 [IAtlMemMgr：：](#reallocate)Allocate 获取的内存。

### <a name="example"></a>示例

有关示例，请参阅 [IAtlMemMgr 概述](../../atl/reference/iatlmemmgr-class.md)。

## <a name="iatlmemmgrgetsize"></a><a name="getsize"></a> IAtlMemMgr：： GetSize

调用此方法可检索已分配内存块的大小。

```
size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向此内存管理器以前分配的内存的指针。

### <a name="return-value"></a>返回值

返回内存块的大小（以字节为单位）。

### <a name="example"></a>示例

有关示例，请参阅 [IAtlMemMgr 概述](../../atl/reference/iatlmemmgr-class.md)。

## <a name="iatlmemmgrreallocate"></a><a name="reallocate"></a> IAtlMemMgr：：重新分配

调用此方法以重新分配由该内存管理器分配的内存。

```cpp
void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>parameters

*h-p*<br/>
指向此内存管理器以前分配的内存的指针。

*nBytes*<br/>
新内存块中请求的字节数。

### <a name="return-value"></a>返回值

将指针返回到新分配内存块的起始位置。

### <a name="remarks"></a>备注

调用 [IAtlMemMgr：： Free](#free) 或 [IAtlMemMgr：：重新分配](#reallocate) 以释放此方法分配的内存。

从概念上讲，此方法将释放现有内存并分配新的内存块。 事实上，可以扩展或重复使用现有内存。

### <a name="example"></a>示例

有关示例，请参阅 [IAtlMemMgr 概述](../../atl/reference/iatlmemmgr-class.md)。

## <a name="iaxwinambientdispatchget_allowcontextmenu"></a><a name="get_allowcontextmenu"></a> IAxWinAmbientDispatch：： get_AllowContextMenu

`AllowContextMenu`属性指定是否允许寄宿控件显示其自己的上下文菜单。

```
STDMETHOD(get_AllowContextMenu)(VARIANT_BOOL* pbAllowContextMenu);
```

### <a name="parameters"></a>parameters

*pbAllowContextMenu*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_allowshowui"></a><a name="get_allowshowui"></a> IAxWinAmbientDispatch：： get_AllowShowUI

`AllowShowUI`属性指定是否允许托管控件显示其自己的用户界面。

```
STDMETHOD(get_AllowShowUI)(VARIANT_BOOL* pbAllowShowUI);
```

### <a name="parameters"></a>parameters

*pbAllowShowUI*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_allowwindowlessactivation"></a><a name="get_allowwindowlessactivation"></a> IAxWinAmbientDispatch：： get_AllowWindowlessActivation

`AllowWindowlessActivation`属性指定容器是否允许无窗口激活。

```
STDMETHOD(get_AllowWindowlessActivation)(VARIANT_BOOL* pbAllowWindowless);
```

### <a name="parameters"></a>parameters

*pbAllowWindowless*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_backcolor"></a><a name="get_backcolor"></a> IAxWinAmbientDispatch：： get_BackColor

`BackColor`属性指定容器的环境背景色。

```
STDMETHOD(get_BackColor)(OLE_COLOR* pclrBackground);
```

### <a name="parameters"></a>parameters

*pclrBackground*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 COLOR_BTNFACE 或 COLOR_WINDOW 作为此属性的默认值 (具体取决于宿主窗口的父窗口是对话框还是不) 。

## <a name="iaxwinambientdispatchget_displayasdefault"></a><a name="get_displayasdefault"></a> IAxWinAmbientDispatch：： get_DisplayAsDefault

`DisplayAsDefault` 是一个环境属性，它允许控件确定其是否为默认控件。

```
STDMETHOD(get_DisplayAsDefault)(VARIANT_BOOL* pbDisplayAsDefault);
```

### <a name="parameters"></a>parameters

*pbDisplayAsDefault*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_dochostdoubleclickflags"></a><a name="get_dochostdoubleclickflags"></a> IAxWinAmbientDispatch：： get_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`属性指定应在响应双击时进行的操作。

```
STDMETHOD(get_DocHostDoubleClickFlags)(DWORD* pdwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>parameters

*pdwDocHostDoubleClickFlags*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 DOCHOSTUIDBLCLK_DEFAULT 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_dochostflags"></a><a name="get_dochostflags"></a> IAxWinAmbientDispatch：： get_DocHostFlags

`DocHostFlags`属性指定宿主对象的用户界面功能。

```
STDMETHOD(get_DocHostFlags)(DWORD* pdwDocHostFlags);
```

### <a name="parameters"></a>parameters

*pdwDocHostFlags*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 DOCHOSTUIFLAG_NO3DBORDER 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_font"></a><a name="get_font"></a> IAxWinAmbientDispatch：： get_Font

`Font`属性指定容器的环境字体。

```
STDMETHOD(get_Font)(IFontDisp** pFont);
```

### <a name="parameters"></a>parameters

*pFont*<br/>
弄 `IFontDisp` 用于接收此属性的当前值的接口指针的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用默认的 GUI 字体或系统字体作为此属性的默认值。

## <a name="iaxwinambientdispatchget_forecolor"></a><a name="get_forecolor"></a> IAxWinAmbientDispatch：： get_ForeColor

`ForeColor`属性指定容器的环境前景色。

```
STDMETHOD(get_ForeColor)(OLE_COLOR* pclrForeground);
```

### <a name="parameters"></a>parameters

*pclrForeground*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用系统窗口文本颜色作为此属性的默认值。

## <a name="iaxwinambientdispatchget_localeid"></a><a name="get_localeid"></a> IAxWinAmbientDispatch：： get_LocaleID

`LocaleID`属性指定容器的环境区域设置 ID。

```
STDMETHOD(get_LocaleID)(LCID* plcidLocaleID);
```

### <a name="parameters"></a>parameters

*plcidLocaleID*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用用户的默认区域设置作为此属性的默认值。

使用此方法，你可以发现环境 LocalID，即你的控件所使用的程序的 LocaleID。 知道 LocaleID 后，可以调用代码来加载资源文件或附属 DLL 中特定于区域设置的标题、错误消息文本等。

## <a name="iaxwinambientdispatchget_messagereflect"></a><a name="get_messagereflect"></a> IAxWinAmbientDispatch：： get_MessageReflect

`MessageReflect`环境属性指定容器是否将消息反射到承载的控件。

```
STDMETHOD(get_MessageReflect)(VARIANT_BOOL* pbMessageReflect);
```

### <a name="parameters"></a>parameters

*pbMessageReflect*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchget_optionkeypath"></a><a name="get_optionkeypath"></a> IAxWinAmbientDispatch：： get_OptionKeyPath

`OptionKeyPath`属性指定用户设置的注册表项路径。

```
STDMETHOD(get_OptionKeyPath)(BSTR* pbstrOptionKeyPath);
```

### <a name="parameters"></a>parameters

*pbstrOptionKeyPath*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinambientdispatchget_showgrabhandles"></a><a name="get_showgrabhandles"></a> IAxWinAmbientDispatch：： get_ShowGrabHandles

`ShowGrabHandles`环境属性允许控件发现它是否应该用抓取手柄来绘制自身。

```
STDMETHOD(get_ShowGrabHandles)(VARIANT_BOOL* pbShowGrabHandles);
```

### <a name="parameters"></a>parameters

*pbShowGrabHandles*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现始终返回 VARIANT_FALSE 作为此属性的值。

## <a name="iaxwinambientdispatchget_showhatching"></a><a name="get_showhatching"></a> IAxWinAmbientDispatch：： get_ShowHatching

`ShowHatching`环境属性允许控件查明是否应绘制其自身的阴影。

```
STDMETHOD(get_ShowHatching)(VARIANT_BOOL* pbShowHatching);
```

### <a name="parameters"></a>parameters

*pbShowHatching*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现始终返回 VARIANT_FALSE 作为此属性的值。

## <a name="iaxwinambientdispatchget_usermode"></a><a name="get_usermode"></a> IAxWinAmbientDispatch：： get_UserMode

`UserMode`属性指定容器的环境用户模式。

```
STDMETHOD(get_UserMode)(VARIANT_BOOL* pbUserMode);
```

### <a name="parameters"></a>parameters

*pbUserMode*<br/>
弄用于接收此属性的当前值的变量的地址。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_allowcontextmenu"></a><a name="put_allowcontextmenu"></a> IAxWinAmbientDispatch：:p ut_AllowContextMenu

`AllowContextMenu`属性指定是否允许寄宿控件显示其自己的上下文菜单。

```
STDMETHOD(put_AllowContextMenu)(VARIANT_BOOL bAllowContextMenu);
```

### <a name="parameters"></a>parameters

*bAllowContextMenu*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_allowshowui"></a><a name="put_allowshowui"></a> IAxWinAmbientDispatch：:p ut_AllowShowUI

`AllowShowUI`属性指定是否允许托管控件显示其自己的用户界面。

```
STDMETHOD(put_AllowShowUI)(VARIANT_BOOL bAllowShowUI);
```

### <a name="parameters"></a>parameters

*bAllowShowUI*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_allowwindowlessactivation"></a><a name="put_allowwindowlessactivation"></a> IAxWinAmbientDispatch：:p ut_AllowWindowlessActivation

`AllowWindowlessActivation`属性指定容器是否允许无窗口激活。

```
STDMETHOD(put_AllowWindowlessActivation)(VARIANT_BOOL bAllowWindowless);
```

### <a name="parameters"></a>parameters

*bAllowWindowless*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_backcolor"></a><a name="put_backcolor"></a> IAxWinAmbientDispatch：:p ut_BackColor

`BackColor`属性指定容器的环境背景色。

```
STDMETHOD(put_BackColor)(OLE_COLOR clrBackground);
```

### <a name="parameters"></a>parameters

*clrBackground*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 COLOR_BTNFACE 或 COLOR_WINDOW 作为此属性的默认值 (具体取决于宿主窗口的父窗口是对话框还是不) 。

## <a name="iaxwinambientdispatchput_displayasdefault"></a><a name="put_displayasdefault"></a> IAxWinAmbientDispatch：:p ut_DisplayAsDefault

`DisplayAsDefault` 是一个环境属性，它允许控件确定其是否为默认控件。

```
STDMETHOD(put_DisplayAsDefault)(VARIANT_BOOL bDisplayAsDefault);
```

### <a name="parameters"></a>parameters

*bDisplayAsDefault*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_FALSE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_dochostdoubleclickflags"></a><a name="put_dochostdoubleclickflags"></a> IAxWinAmbientDispatch：:p ut_DocHostDoubleClickFlags

`DocHostDoubleClickFlags`属性指定应在响应双击时进行的操作。

```
STDMETHOD(put_DocHostDoubleClickFlags)(DWORD dwDocHostDoubleClickFlags);
```

### <a name="parameters"></a>parameters

*dwDocHostDoubleClickFlags*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 DOCHOSTUIDBLCLK_DEFAULT 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_dochostflags"></a><a name="put_dochostflags"></a> IAxWinAmbientDispatch：:p ut_DocHostFlags

`DocHostFlags`属性指定宿主对象的用户界面功能。

```
STDMETHOD(put_DocHostFlags)(DWORD dwDocHostFlags);
```

### <a name="parameters"></a>parameters

*dwDocHostFlags*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 DOCHOSTUIFLAG_NO3DBORDER 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_font"></a><a name="put_font"></a> IAxWinAmbientDispatch：:p ut_Font

`Font`属性指定容器的环境字体。

```
STDMETHOD(put_Font)(IFontDisp* pFont);
```

### <a name="parameters"></a>parameters

*pFont*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用默认的 GUI 字体或系统字体作为此属性的默认值。

## <a name="iaxwinambientdispatchput_forecolor"></a><a name="put_forecolor"></a> IAxWinAmbientDispatch：:p ut_ForeColor

`ForeColor`属性指定容器的环境前景色。

```
STDMETHOD(put_ForeColor)(OLE_COLOR clrForeground);
```

### <a name="parameters"></a>parameters

*clrForeground*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用系统窗口文本颜色作为此属性的默认值。

## <a name="iaxwinambientdispatchput_localeid"></a><a name="put_localeid"></a> IAxWinAmbientDispatch：:p ut_LocaleID

`LocaleID`属性指定容器的环境区域设置 ID。

```
STDMETHOD(put_LocaleID)(LCID lcidLocaleID);
```

### <a name="parameters"></a>parameters

*lcidLocaleID*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用用户的默认区域设置作为此属性的默认值。

## <a name="iaxwinambientdispatchput_messagereflect"></a><a name="put_messagereflect"></a> IAxWinAmbientDispatch：:p ut_MessageReflect

`MessageReflect`环境属性指定容器是否将消息反射到承载的控件。

```
STDMETHOD(put_MessageReflect)(VARIANT_BOOL bMessageReflect);
```

### <a name="parameters"></a>parameters

*bMessageReflect*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchput_optionkeypath"></a><a name="put_optionkeypath"></a> IAxWinAmbientDispatch：:p ut_OptionKeyPath

`OptionKeyPath`属性指定用户设置的注册表项路径。

```
STDMETHOD(put_OptionKeyPath)(BSTR bstrOptionKeyPath);
```

### <a name="parameters"></a>parameters

*bstrOptionKeyPath*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="iaxwinambientdispatchput_usermode"></a><a name="put_usermode"></a> IAxWinAmbientDispatch：:p ut_UserMode

`UserMode`属性指定容器的环境用户模式。

```
STDMETHOD(put_UserMode)(VARIANT_BOOL bUserMode);
```

### <a name="parameters"></a>parameters

*bUserMode*<br/>
中此属性的新值。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

ATL 宿主对象实现使用 VARIANT_TRUE 作为此属性的默认值。

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a> IAxWinAmbientDispatchEx::SetAmbientDispatch

调用此方法以使用用户定义的接口来补充默认环境属性接口。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>parameters

*pDispatch*<br/>
指向新接口的指针。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

当 `SetAmbientDispatch` 使用指向新接口的指针调用时，如果 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)未提供这些属性，则此新接口将用于调用由承载的控件要求的任何属性或方法。

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

若要创建许可的 ActiveX 控件，请参阅 [IAxWinHostWindowLic：： CreateControlLic](#createcontrollicex)。

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

若要创建许可的 ActiveX 控件，请参阅 [IAxWinHostWindowLic：： CreateControlLicEx](#createcontrollicex)。

## <a name="iaxwinhostwindowquerycontrol"></a><a name="querycontrol"></a> IAxWinHostWindow::QueryControl

返回由托管控件提供的指定接口指针。

```
STDMETHOD(QueryControl)(REFIID riid, void** ppvObject);
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

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> IAxWinHostWindowLic::CreateControlLic

创建授权控件，对其进行初始化，并将其托管在由标识的窗口中 `hWnd` 。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>parameters

*bstrLic*<br/>
中包含控件的许可证密钥的 BSTR。

### <a name="remarks"></a>备注

有关剩余参数和返回值的说明，请参阅 [IAxWinHostWindow：： CreateControl](#createcontrol) 。

调用此方法等效于调用 [IAxWinHostWindowLic：： CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>示例

有关使用的示例，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `IAxWinHostWindowLic::CreateControlLic` 。

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> IAxWinHostWindowLic::CreateControlLicEx

创建许可的 ActiveX 控件，对其进行初始化，并将其托管在指定窗口中，类似于 [IAxWinHostWindow：： CreateControl](#createcontrol)。

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>parameters

*bstrLic*<br/>
中包含控件的许可证密钥的 BSTR。

### <a name="remarks"></a>备注

有关剩余参数和返回值的说明，请参阅 [IAxWinHostWindow：： CreateControlEx](#createcontrolex) 。

### <a name="example"></a>示例

有关使用的示例，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `IAxWinHostWindowLic::CreateControlLicEx` 。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

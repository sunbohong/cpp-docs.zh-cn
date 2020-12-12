---
description: 了解详细信息： CWndClassInfo 类
title: CWndClassInfo 类
ms.date: 11/04/2016
f1_keywords:
- CWndClassInfo
- ATLWIN/ATL::CWndClassInfo
- ATLWIN/ATL::Register
- ATLWIN/ATL::m_atom
- ATLWIN/ATL::m_bSystemCursor
- ATLWIN/ATL::m_lpszCursorID
- ATLWIN/ATL::m_lpszOrigName
- ATLWIN/ATL::m_szAutoName
- ATLWIN/ATL::m_wc
- ATLWIN/ATL::pWndProc
helpviewer_keywords:
- CWndClassInfo class
ms.assetid: c36fe7e1-75f1-4cf5-a06f-9f59c43fe6fb
ms.openlocfilehash: 7a857812fa35743fbab0968fb94095bf8fdcabcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140018"
---
# <a name="cwndclassinfo-class"></a>CWndClassInfo 类

此类提供用于注册窗口类的信息的方法。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CWndClassInfo
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|-|-|
|[注册](#register)|注册窗口类。|

### <a name="data-members"></a>数据成员

|名称|描述|
|-|-|
|[m_atom](#m_atom)|唯一标识已注册的窗口类。|
|[m_bSystemCursor](#m_bsystemcursor)|指定光标资源是指系统游标还是引用模块资源中包含的游标。|
|[m_lpszCursorID](#m_lpszcursorid)|指定游标资源的名称。|
|[m_lpszOrigName](#m_lpszorigname)|包含现有窗口类的名称。|
|[m_szAutoName](#m_szautoname)|保存窗口类的 ATL 生成的名称。|
|[m_wc](#m_wc)|在结构中维护窗口类信息 `WNDCLASSEX` 。|
|[pWndProc](#pwndproc)|指向现有窗口类的窗口过程。|

## <a name="remarks"></a>备注

`CWndClassInfo` 管理窗口类的信息。 通常使用 `CWndClassInfo` 三个宏之一，DECLARE_WND_CLASS、DECLARE_WND_CLASS_EX 或 DECLARE_WND_SUPERCLASS，如下表中所述：

|宏|描述|
|-----------|-----------------|
|[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)|`CWndClassInfo` 注册新窗口类的信息。|
|[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)|`CWndClassInfo` 注册新窗口类的信息，包括类参数。|
|[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)|`CWndClassInfo` 注册基于现有类但使用不同窗口过程的窗口类的信息。 此方法称为 superclassing。|

默认情况下， [CWindowImpl](../../atl/reference/cwindowimpl-class.md) 包含 `DECLARE_WND_CLASS` 宏来基于新的窗口类创建窗口。 DECLARE_WND_CLASS 提供控件的默认样式和背景色。 如果要自行指定样式和背景色，请从派生类， `CWindowImpl` 并在类定义中包括 DECLARE_WND_CLASS_EX 宏。

如果要基于现有窗口类创建窗口，请从派生类， `CWindowImpl` 并在类定义中包括 DECLARE_WND_SUPERCLASS 宏。 例如：

[!code-cpp[NVC_ATL_Windowing#43](../../atl/codesnippet/cpp/cwndclassinfo-class_1.h)]

有关窗口类的详细信息，请参阅中的 [窗口类](/windows/win32/winmsg/window-classes) Windows SDK。

有关在 ATL 中使用 windows 的详细信息，请参阅 [Atl 窗口类](../../atl/atl-window-classes.md)一文。

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="cwndclassinfom_atom"></a><a name="m_atom"></a> CWndClassInfo：： m_atom

包含已注册的窗口类的唯一标识符。

```
ATOM m_atom;
```

## <a name="cwndclassinfom_bsystemcursor"></a><a name="m_bsystemcursor"></a> CWndClassInfo：： m_bSystemCursor

如果为 TRUE，则在注册窗口类时将加载系统游标资源。

```
BOOL m_bSystemCursor;
```

### <a name="remarks"></a>备注

否则，将加载模块中包含的游标资源。

`CWndClassInfo``m_bSystemCursor`仅当[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)在[CWindowImpl](../../atl/reference/cwindowimpl-class.md)中 (默认值) 或指定[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)宏时才使用。 在这种情况下， `m_bSystemCursor` 将初始化为 TRUE。 有关详细信息，请参阅 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 概述。

## <a name="cwndclassinfom_lpszcursorid"></a><a name="m_lpszcursorid"></a> CWndClassInfo：： m_lpszCursorID

指定光标资源的名称，或者指定高位字中的资源标识符，并在高位字中指定零。

```
LPCTSTR m_lpszCursorID;
```

### <a name="remarks"></a>备注

当注册窗口类时，由标识的游标的句柄由 `m_lpszCursorID` [m_wc](#m_wc)检索并存储。

`CWndClassInfo``m_lpszCursorID`仅当[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)在[CWindowImpl](../../atl/reference/cwindowimpl-class.md)中 (默认值) 或指定[DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)宏时才使用。 在这种情况下， `m_lpszCursorID` 将初始化为 IDC_ARROW。 有关详细信息，请参阅 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 概述。

## <a name="cwndclassinfom_lpszorigname"></a><a name="m_lpszorigname"></a> CWndClassInfo：： m_lpszOrigName

包含现有窗口类的名称。

```
LPCTSTR m_lpszOrigName;
```

### <a name="remarks"></a>备注

`CWndClassInfo``m_lpszOrigName`仅在类定义中包含[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)宏时使用。 在这种情况下，将 `CWndClassInfo` 基于名为的类注册一个窗口类 `m_lpszOrigName` 。 有关详细信息，请参阅 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 概述。

## <a name="cwndclassinfom_szautoname"></a><a name="m_szautoname"></a> CWndClassInfo：： m_szAutoName

保存窗口类的名称。

```
TCHAR m_szAutoName[13];
```

### <a name="remarks"></a>备注

`CWndClassInfo``m_szAutoName`仅在将 NULL 传递给 `WndClassName` 参数[DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class)、 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex)或[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)时使用。 当注册窗口类时，ATL 将构造一个名称。

## <a name="cwndclassinfom_wc"></a><a name="m_wc"></a> CWndClassInfo：： m_wc

在 [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw) 结构中维护窗口类信息。

```
WNDCLASSEX m_wc;
```

### <a name="remarks"></a>备注

如果已指定 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ([CWindowImpl](../../atl/reference/cwindowimpl-class.md)) 或 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 宏中的默认值，则 `m_wc` 包含有关新窗口类的信息。

如果您已指定 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 宏，则 `m_wc` 包含有关超类的信息：一个基于现有类但使用不同窗口过程的窗口类。 [m_lpszOrigName](#m_lpszorigname) 和 [pWndProc](#pwndproc) 分别保存现有窗口类的名称和窗口过程。

## <a name="cwndclassinfopwndproc"></a><a name="pwndproc"></a> CWndClassInfo：:p WndProc

指向现有窗口类的窗口过程。

```
WNDPROC pWndProc;
```

### <a name="remarks"></a>备注

`CWndClassInfo``pWndProc`仅在类定义中包含[DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass)宏时使用。 在这种情况下，将 `CWndClassInfo` 注册一个基于现有类但使用不同窗口过程的窗口类。 现有窗口类的窗口过程保存在中 `pWndProc` 。 有关详细信息，请参阅 [CWndClassInfo](../../atl/reference/cwndclassinfo-class.md) 概述。

## <a name="cwndclassinforegister"></a><a name="register"></a> CWndClassInfo：： Register

通过 [CWindowImpl：： Create](../../atl/reference/cwindowimpl-class.md#create) 调用，以注册窗口类（如果尚未注册）。

```
ATOM Register(WNDPROC* pProc);
```

### <a name="parameters"></a>parameters

*pProc*<br/>
弄指定现有窗口类的原始窗口过程。

### <a name="return-value"></a>返回值

如果成功，则为唯一标识要注册的窗口类的 atom。 否则为 0。

### <a name="remarks"></a>备注

如果已指定 [DECLARE_WND_CLASS](window-class-macros.md#declare_wnd_class) ([CWindowImpl](../../atl/reference/cwindowimpl-class.md)) 或 [DECLARE_WND_CLASS_EX](window-class-macros.md#declare_wnd_class_ex) 宏中的默认值，则会 `Register` 注册一个新的窗口类。 在这种情况下，不使用 *pProc* 参数。

如果已指定 [DECLARE_WND_SUPERCLASS](window-class-macros.md#declare_wnd_superclass) 宏，则 `Register` 会注册一个超类，这是一个基于现有类但使用不同窗口过程的窗口类。 在 *pProc* 中返回现有窗口类的窗口过程。

## <a name="see-also"></a>请参阅

[CComControl 类](../../atl/reference/ccomcontrol-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)

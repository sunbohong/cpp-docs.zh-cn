---
description: 了解详细信息： CMFCRibbonMiniToolBar 类
title: CMFCRibbonMiniToolBar 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsContextMenuMode
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::IsRibbonMiniToolBar
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::SetCommands
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::Show
- AFXRIBBONMINITOOLBAR/CMFCRibbonMiniToolBar::ShowWithContextMenu
helpviewer_keywords:
- CMFCRibbonMiniToolBar [MFC], IsContextMenuMode
- CMFCRibbonMiniToolBar [MFC], IsRibbonMiniToolBar
- CMFCRibbonMiniToolBar [MFC], SetCommands
- CMFCRibbonMiniToolBar [MFC], Show
- CMFCRibbonMiniToolBar [MFC], ShowWithContextMenu
ms.assetid: 7017e963-aeaf-4fe9-b540-e15a7ed41e94
ms.openlocfilehash: 7215349323f8039bccb24860e4e5ad663bd24bcd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273938"
---
# <a name="cmfcribbonminitoolbar-class"></a>CMFCRibbonMiniToolBar 类

实现上下文快捷工具栏。

## <a name="syntax"></a>语法

```
class CMFCRibbonMiniToolBar : public CMFCRibbonPanelMenu
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CMFCRibbonMiniToolBar`|默认构造函数。|
|`CMFCRibbonMiniToolBar::~CMFCRibbonMiniToolBar`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|`CMFCRibbonMiniToolBar::CreateObject`|由框架用于创建此类类型的动态实例。|
|`CMFCRibbonMiniToolBar::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCRibbonMiniToolBar::IsContextMenuMode](#iscontextmenumode)||
|[CMFCRibbonMiniToolBar::IsRibbonMiniToolBar](#isribbonminitoolbar)|（重写 `CMFCPopupMenu::IsRibbonMiniToolBar`。）|
|[CMFCRibbonMiniToolBar::SetCommands](#setcommands)|设置要在工具栏上显示的命令的列表。|
|[CMFCRibbonMiniToolBar::Show](#show)|在指定的屏幕坐标上显示浮动工具栏。|
|[CMFCRibbonMiniToolBar::ShowWithContextMenu](#showwithcontextmenu)|显示浮动工具栏以及上下文菜单。|

## <a name="remarks"></a>备注

通常于用户在文档中选择对象后显示浮动工具栏。 例如，用户在文字处理程序中选择文本块后，应用程序将显示包含文本格式设置命令的浮动工具栏。

鼠标指针位于浮动工具栏边界之外时，浮动工具栏将变透明。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

`CMFCRibbonPanelMenu`

[CMFCRibbonMiniToolBar](../../mfc/reference/cmfcribbonminitoolbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxRibbonMiniToolBar

## <a name="cmfcribbonminitoolbarsetcommands"></a><a name="setcommands"></a> CMFCRibbonMiniToolBar::SetCommands

设置要在工具栏上显示的命令的列表。

```cpp
void SetCommands(
    CMFCRibbonBar* pRibbonBar,
    const CList<UINT,UINT>& lstCommands);
```

### <a name="parameters"></a>parameters

*pRibbonBar*<br/>
中迷你工具栏搜索要显示的按钮的功能区栏。

*lstCommands*<br/>
中要在微型工具栏上显示的命令的列表。 搜索所有功能区类别以查找相关按钮。

### <a name="remarks"></a>备注

使用此函数可设置要在微型工具栏中显示的命令的列表。

### <a name="example"></a>示例

下面的示例演示如何使用类的 `SetCommands` 方法 `CMFCRibbonMiniToolBar` 。 此代码片段是 [MS Office 2007 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_MSOffice2007Demo#9](../../mfc/reference/codesnippet/cpp/cmfcribbonminitoolbar-class_1.cpp)]

## <a name="cmfcribbonminitoolbarshow"></a><a name="show"></a> CMFCRibbonMiniToolBar：： Show

在指定的屏幕坐标上显示浮动工具栏。

```
BOOL Show(
    int x,
    int y);
```

### <a name="parameters"></a>parameters

*x*<br/>
中指定微型工具栏在屏幕坐标中的水平位置。

*y*<br/>
中指定微型工具栏在屏幕坐标中的垂直位置。

### <a name="return-value"></a>返回值

如果已成功显示迷你工具栏，则为 TRUE;否则为 FALSE。

## <a name="cmfcribbonminitoolbarshowwithcontextmenu"></a><a name="showwithcontextmenu"></a> CMFCRibbonMiniToolBar::ShowWithContextMenu

显示浮动工具栏以及上下文菜单。

```
BOOL ShowWithContextMenu(
    int x,
    int y,
    UINT uiMenuResID,
    CWnd* pWndOwner);
```

### <a name="parameters"></a>parameters

*x*<br/>
中指定上下文菜单在屏幕坐标中的水平位置。

*y*<br/>
中指定上下文菜单在屏幕坐标中的垂直位置。

*uiMenuResID*<br/>
中指定要显示的上下文菜单的资源 ID。

*pWndOwner*<br/>
中标识从上下文菜单接收消息的窗口。

### <a name="return-value"></a>返回值

如果成功显示上下文菜单，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

使用此函数可显示具有上下文菜单的浮动工具栏。 上下文菜单位于迷你工具栏的下面。

## <a name="cmfcribbonminitoolbariscontextmenumode"></a><a name="iscontextmenumode"></a> CMFCRibbonMiniToolBar::IsContextMenuMode

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
BOOL IsContextMenuMode() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonminitoolbarisribbonminitoolbar"></a><a name="isribbonminitoolbar"></a> CMFCRibbonMiniToolBar::IsRibbonMiniToolBar

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual BOOL IsRibbonMiniToolBar() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)

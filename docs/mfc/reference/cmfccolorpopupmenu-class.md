---
title: CMFCColorPopupMenu 类
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: d668a7bd2b5226de906ca146c7b7e882b97f4640
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88560980"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu 类

表示一个弹出菜单，用户可以使用该菜单选择文档或应用程序中的颜色。

## <a name="syntax"></a>语法

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|||
|-|-|
|“属性”|说明|
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|构造 `CMFCColorPopupMenu` 对象。|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|析构函数。|

### <a name="public-methods"></a>公共方法

|||
|-|-|
|“属性”|说明|
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|创建可停靠的撕颜色条。  (重写 [CMFCPopupMenu：： CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar)。 ) |
|[CMFCColorPopupMenu::GetMenuBar](#getmenubar)|返回嵌入到弹出菜单中的 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 。  (重写 [CMFCPopupMenu：： GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar)。 ) |
|`CMFCColorPopupMenu::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCColorPopupMenu::SetPropList](#setproplist)|设置嵌入对象的属性网格控件对象 `CMFCColorBar` 。|

### <a name="data-members"></a>数据成员

|||
|-|-|
|名称|说明|
|`m_bEnabledInCustomizeMode`|确定是否显示颜色条的布尔值。|
|`m_wndColorBar`|`CMFCColorBar`提供颜色选择的对象。|

### <a name="remarks"></a>备注

此类继承类的弹出菜单功能 `CMFCPopupMenu` ，并管理 `CMFCColorBar` 提供颜色选择的对象。 如果工具栏框架处于自定义模式并且 `m_bEnabledInCustomizeMode` 成员设置为 FALSE，则不会显示颜色栏对象。 有关自定义模式的详细信息，请参阅 [CMFCToolBar：： IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

有关的详细信息 `CMFCColorBar` ，请参阅 [CMFCColorBar 类](../../mfc/reference/cmfccolorbar-class.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>要求

**标头：** afxcolorpopupmenu

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a> CMFCColorPopupMenu::CMFCColorPopupMenu

构造 `CMFCColorPopupMenu` 对象。

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>参数

*颜色*<br/>
中框架在弹出菜单上显示的颜色的数组。

*color*<br/>
中默认选定的颜色。

*lpszAutoColor*<br/>
中 *自动* (默认) 颜色 "按钮的文本标签，或为 NULL。

"自动" 按钮的标准标签为 " **自动**"。

*lpszOtherColor*<br/>
中" *其他* " 按钮的文本标签，可显示更多颜色选项，或为 NULL。

"其他" 按钮的标准标签为 "其他 **颜色 ...**"。

*lpszDocColors*<br/>
中"文档颜色" 按钮的文本标签。 "文档颜色" 调色板列出了文档当前使用的所有颜色。

*lstDocColors*<br/>
中文档当前使用的颜色的列表。

*nColumns*<br/>
中颜色数组具有的列数。

*nHorzDockRows*<br/>
中颜色栏水平停靠时的行数。

*nVertDockColumns*<br/>
中颜色栏垂直停靠时所具有的列数。

*colorAutomatic*<br/>
中单击 "自动" 按钮时，框架应用的默认颜色。

*uiCommandID*<br/>
中颜色栏控件命令 ID。

*bStdColorDlg*<br/>
中一个布尔值，指示是显示标准系统颜色对话框还是显示 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) 对话框。

*pParentBtn*<br/>
中指向父按钮的指针。

*nID*<br/>
中命令 ID。

### <a name="remarks"></a>备注

每个重载构造函数将 `m_bEnabledInCustomizeMode` 成员设置为 FALSE。

### <a name="example"></a>示例

下面的示例演示如何构造 `CMFCColorPopupMenu` 对象。

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a> CMFCColorPopupMenu::CreateTearOffBar

创建可停靠的撕颜色条。

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>参数

*pWndMain*\
中指向被撕条的父窗口的指针。

*uiID*\
中撕分隔条的命令 ID。

*lpszName*\
中拆离栏的窗口文本。

### <a name="return-value"></a>返回值

指向新的撕控件栏对象的指针。

### <a name="remarks"></a>备注

此方法创建 [CMFCColorBar 类](../../mfc/reference/cmfccolorbar-class.md) 对象并将其转换为 [CPane 类](../../mfc/reference/cpane-class.md) 指针。 可以使用[MFC 类对象的类型强制](../../mfc/reference/type-casting-of-mfc-class-objects.md)转换中所述的其中一个强制转换宏，将此值强制转换回[CMFCColorBar 类](../../mfc/reference/cmfccolorbar-class.md)指针。

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a> CMFCColorPopupMenu::GetMenuBar

返回嵌入到弹出菜单中的 [CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md) 。

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>返回值

指向嵌入的的指针 `CMFCPopupMenuBar` 。

### <a name="remarks"></a>备注

颜色弹出菜单具有嵌入的 [CMFCPopupMenuBar 类](../../mfc/reference/cmfcpopupmenubar-class.md) 对象。 如果你的应用程序使用不同的嵌入类型，则在派生类中重写此方法。

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a> CMFCColorPopupMenu::SetPropList

设置嵌入对象的属性网格控件对象 `CMFCColorBar` 。

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>参数

*pWndList*<br/>
中指向属性网格控件对象的指针。

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)

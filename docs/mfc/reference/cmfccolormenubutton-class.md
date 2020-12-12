---
description: 了解详细信息： CMFCColorMenuButton 类
title: CMFCColorMenuButton 类
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 4ba0934e872adc4e4b33c2ae5700ecb0fc46e6d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327677"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton 类

`CMFCColorMenuButton`类支持用于启动颜色选取器对话框的菜单命令或工具栏按钮。

## <a name="syntax"></a>语法

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|构造 `CMFCColorMenuButton` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|启用和禁用定位在常规颜色按钮之上的 "自动" 按钮。  (标准系统 "自动" 按钮标记为 " **自动**"。 ) |
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|启用显示特定于文档的颜色而不是系统颜色。|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|启用和禁用 "其他" 按钮，该按钮位于常规颜色按钮的下方。  (标准系统 "其他" 按钮标记为 "其他 **颜色**"。 ) |
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|启用用于脱离颜色窗格的功能。|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|检索当前自动颜色。|
|[CMFCColorMenuButton：： GetColor](#getcolor)|检索当前按钮的颜色。|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|检索对应于指定命令 ID 的颜色。|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|当父窗口更改时由框架调用。|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|打开颜色选择对话框。|
|[CMFCColorMenuButton::SetColor](#setcolor)|设置当前颜色按钮的颜色。|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|设置指定颜色菜单按钮的颜色。|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|为指定的颜色设置新名称。|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|设置对象显示的列数 `CMFCColorBar` 。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCColorMenuButton：： CopyFrom](#copyfrom)|将另一个工具栏按钮复制到当前按钮。|
|[CMFCColorMenuButton：： CreatePopupMenu](#createpopupmenu)|创建颜色选取器对话框。|
|[CMFCColorMenuButton：： IsEmptyMenuAllowed](#isemptymenuallowed)|指示是否支持空菜单。|
|[CMFCColorMenuButton：： OnDraw](#ondraw)|由框架调用以显示按钮上的图像。|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|在 `CMFCColorMenuButton` 工具栏自定义对话框列表中显示对象之前，由框架调用。|

## <a name="remarks"></a>备注

若要将原始菜单命令或工具栏按钮替换为 `CMFCColorMenuButton` 对象，请创建 `CMFCColorMenuButton` 对象，设置任何适当的 [CMFCColorBar 类](../../mfc/reference/cmfccolorbar-class.md) 样式，然后调用 `ReplaceButton` [CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md) 的方法。 如果自定义工具栏，请调用 [CMFCToolBarsCustomizeDialog：： ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) 方法。

"颜色选取器" 对话框是在 [CMFCColorMenuButton：： CreatePopupMenu](#createpopupmenu) 事件处理程序的处理过程中创建的。 事件处理程序使用 WM_COMMAND 消息通知父框架。 `CMFCColorMenuButton`对象发送分配给原始菜单命令或工具栏按钮的控件 ID。

## <a name="example"></a>示例

下面的示例演示如何通过使用类中的各种方法来创建和配置 "颜色" 菜单按钮 `CMFCColorMenuButton` 。 在此示例中， `CPalette` 首先创建一个对象，然后使用该对象构造类的对象 `CMFCColorMenuButton` 。 `CMFCColorMenuButton`然后，通过启用其自动和其他按钮，并设置其颜色和列数来配置该对象。 此代码是 [Word Pad 示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>要求

**标头：** afxcolormenubutton

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a> CMFCColorMenuButton::CMFCColorMenuButton

构造 `CMFCColorMenuButton` 对象。

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>parameters

*uiCmdID*<br/>
中按钮命令 ID。

*lpszText*<br/>
中按钮文本。

*pPalette*<br/>
中指向按钮调色板的指针。

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

第一个构造函数是默认构造函数。 对象的当前颜色和自动颜色初始化为黑色 (RGB (0，0，0) # A3。

第二个构造函数将按钮初始化为对应于指定命令 ID 的颜色。

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a> CMFCColorMenuButton：： CopyFrom

将一个 [CMFCToolBarMenuButton 类](../../mfc/reference/cmfctoolbarmenubutton-class.md)派生对象复制到另一个。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>parameters

*src*<br/>
中要复制的源按钮。

### <a name="remarks"></a>备注

重写此方法以复制从对象派生的对象 `CMFCColorMenuButton` 。

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a> CMFCColorMenuButton：： CreatePopupMenu

创建颜色选取器对话框。

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>返回值

表示颜色选取器对话框的对象。

### <a name="remarks"></a>备注

当用户按下颜色菜单按钮时，框架会调用此方法。

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> CMFCColorMenuButton::EnableAutomaticButton

启用和禁用定位在常规颜色按钮之上的 "自动" 按钮。  (标准系统 "自动" 按钮标记为 " **自动**"。 ) 

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中指定按钮变为自动时显示的按钮文本。

*colorAutomatic*<br/>
中指定新的自动颜色。

*bEnable*<br/>
中指定按钮是否自动。

### <a name="remarks"></a>备注

"自动" 按钮应用当前默认颜色。

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a> CMFCColorMenuButton::EnableDocumentColors

启用显示特定于文档的颜色而不是系统颜色。

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中指定按钮文本。

*bEnable*<br/>
中若要显示特定于文档的颜色，则为 TRUE; 否则为 FALSE 以显示系统颜色。

### <a name="remarks"></a>备注

使用此方法可以在用户单击颜色菜单按钮时显示当前文档颜色或系统调色板颜色。

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a> CMFCColorMenuButton::EnableOtherButton

启用和禁用 "其他" 按钮，该按钮位于常规颜色按钮的下方。  (标准系统 "其他" 按钮标记为 "其他 **颜色**"。 ) 

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
中指定按钮文本。

*bAltColorDlg*<br/>
中指定 TRUE 以显示 `CMFCColorDialog` 对话框，或指定 FALSE 以显示 "标准系统颜色" 对话框。

*bEnable*<br/>
中指定 TRUE 以显示 "其他" 按钮;否则为 FALSE。 默认值为 TRUE。

### <a name="remarks"></a>备注

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a> CMFCColorMenuButton::EnableTearOff

启用用于脱离颜色窗格的功能。

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>parameters

*uiID*<br/>
中指定脱离窗格的 ID。

*nVertDockColumns*<br/>
中指定垂直停靠颜色窗格中的列数，同时处于撕状态。

*nHorzDockRows*<br/>
中指定水平停靠的颜色窗格在撕状态下的行数。

### <a name="remarks"></a>备注

调用此方法可为按下按钮时弹出的颜色窗格启用 "撕停" 功能 `CMFCColorMenuButton` 。

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> CMFCColorMenuButton::GetAutomaticColor

检索当前自动颜色。

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>返回值

表示当前自动颜色的 RGB 颜色值。

### <a name="remarks"></a>备注

调用此方法以获取 [CMFCColorMenuButton：： EnableAutomaticButton](#enableautomaticbutton)设置的自动颜色。

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a> CMFCColorMenuButton：： GetColor

检索当前按钮的颜色。

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>返回值

按钮的颜色。

### <a name="remarks"></a>备注

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a> CMFCColorMenuButton::GetColorByCmdID

检索对应于指定命令 ID 的颜色。

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>parameters

*uiCmdID*<br/>
中命令 ID。

### <a name="return-value"></a>返回值

与指定的命令 ID 相对应的颜色。

### <a name="remarks"></a>备注

在应用程序中有多个颜色按钮时使用此方法。 用户单击颜色按钮时，按钮会将 WM_COMMAND 消息中的命令 ID 发送到其父项。 `GetColorByCmdID`方法使用命令 ID 来检索相应的颜色。

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a> CMFCColorMenuButton：： IsEmptyMenuAllowed

指示是否支持空菜单。

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>返回值

如果允许空菜单，则为非零值;否则为零。

### <a name="remarks"></a>备注

默认情况下支持空菜单。 重写此方法以更改派生类中的此行为。

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a> CMFCColorMenuButton::OnChangeParentWnd

当父窗口更改时由框架调用。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>parameters

*pWndParent*<br/>
中指向新的父窗口的指针。

### <a name="remarks"></a>备注

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a> CMFCColorMenuButton：： OnDraw

由框架调用以显示按钮上的图像。

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中限定要重新绘制的区域的矩形。

*pImages*<br/>
中指向工具栏图像的列表。

*bHorz*<br/>
中若要指定工具栏处于水平停靠状态，则为 TRUE;否则为 FALSE。 默认值为 TRUE。

*bCustomizeMode*<br/>
中如果为 TRUE，则指定应用程序处于自定义模式;否则为 FALSE。 默认值为 FALSE。

*bHighlight*<br/>
中若要指定按钮突出显示，则为 TRUE;否则为 FALSE。 默认值为 FALSE。

*bDrawBorder*<br/>
中若要指定显示按钮的边框，则为 TRUE;否则为 FALSE。 默认值为 TRUE。

*bGrayDisabledButtons*<br/>
中如果指定 "禁用" 按钮灰显 (灰显) ，则为 TRUE;否则为 FALSE。 默认值为 TRUE。

### <a name="remarks"></a>备注

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a> CMFCColorMenuButton::OnDrawOnCustomizeList

在 `CMFCColorMenuButton` 工具栏自定义对话框列表中显示对象之前，由框架调用。

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中限定要绘制的按钮的矩形。

*bSelected*<br/>
中如果为 TRUE，则指定按钮处于选中状态;否则为 FALSE。

### <a name="return-value"></a>返回值

按钮的宽度。

### <a name="remarks"></a>备注

当在 `CMFCColorMenuButton` 工具栏自定义过程中在列表框中显示某个对象时，框架会调用此方法。

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a> CMFCColorMenuButton::OpenColorDialog

打开颜色选择对话框。

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>parameters

*colorDefault*<br/>
中在 "颜色" 对话框中选择的默认颜色。

*colorRes*<br/>
弄返回用户从 "颜色" 对话框中选择的颜色。

### <a name="return-value"></a>返回值

如果用户选择新颜色，则为非零值;否则为零。

### <a name="remarks"></a>备注

单击菜单按钮时，调用此方法以打开 "颜色" 对话框。 如果返回值为非零值，则用户选择的颜色存储在 *colorRes* 参数中。 使用 [CMFCColorMenuButton：： EnableOtherButton](#enableotherbutton) 方法在 "标准颜色" 对话框和 " [CMFCColorDialog 类](../../mfc/reference/cmfccolordialog-class.md) " 对话框之间切换。

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a> CMFCColorMenuButton::SetColor

设置当前颜色按钮的颜色。

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>parameters

*clr*<br/>
中RGB 颜色值。

*bNotify*<br/>
中若要将 *clr* 参数颜色应用于任何关联的菜单按钮或工具栏按钮，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此方法可更改当前颜色按钮的颜色。 如果 *bNotify* 参数为非零值，则任何关联的弹出菜单或工具栏上相应按钮的颜色将更改为 *clr* 参数指定的颜色。

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a> CMFCColorMenuButton::SetColorByCmdID

设置指定颜色菜单按钮的颜色。

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>parameters

*uiCmdID*<br/>
中颜色菜单按钮的资源 ID。

*color*<br/>
中RGB 颜色值。

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a> CMFCColorMenuButton::SetColorName

为指定的颜色设置新名称。

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>parameters

*color*<br/>
中其名称更改的颜色的 RGB 值。

*strName*<br/>
中颜色的新名称。

### <a name="remarks"></a>备注

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a> CMFCColorMenuButton::SetColumnsNumber

设置在颜色选择控件中显示的列数 ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) 对象) 。

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>parameters

*nColumns*<br/>
中要显示的列数。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar 类](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog 类](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton 类](../../mfc/reference/cmfccolorbutton-class.md)

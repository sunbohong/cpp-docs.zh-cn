---
title: CMFCBaseVisualManager 类
ms.date: 11/04/2016
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
ms.openlocfilehash: 28efe75c3c825c04c88f9f2263a3db2d83d4f3af
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561318"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager 类

派生的可视化管理器和 Windows 主题 API 之间的一层。

`CMFCBaseVisualManager` 加载 UxTheme.dll （如果可用），并管理对 Windows 主题 API 方法的访问。

此类仅供内部使用。

## <a name="syntax"></a>语法

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|||
|-|-|
|“属性”|说明|
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|构造并初始化一个 `CMFCBaseVisualManager` 对象。|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|析构函数。|

### <a name="public-methods"></a>公共方法

|||
|-|-|
|“属性”|说明|
|[CMFCBaseVisualManager：:D rawCheckBox](#drawcheckbox)|使用当前 Windows 主题绘制复选框控件。|
|[CMFCBaseVisualManager：:D rawComboBorder](#drawcomboborder)|使用当前 Windows 主题绘制组合框边框。|
|[CMFCBaseVisualManager：:D rawComboDropButton](#drawcombodropbutton)|使用当前 Windows 主题绘制组合框下拉按钮。|
|[CMFCBaseVisualManager：:D rawPushButton](#drawpushbutton)|使用当前 Windows 主题绘制一个按钮。|
|[CMFCBaseVisualManager：:D rawRadioButton](#drawradiobutton)|使用当前 Windows 主题绘制单选按钮控件。|
|[CMFCBaseVisualManager：:D rawStatusBarProgress](#drawstatusbarprogress)|使用当前 Windows 主题 ( [CMFCStatusBar 类](../../mfc/reference/cmfcstatusbar-class.md)) 在状态栏控件上绘制进度栏。|
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|使用当前 Windows 主题填充 rebar 控件的背景。|
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|获取当前的 Windows 主题。|

### <a name="protected-methods"></a>受保护的方法

|||
|-|-|
|名称|说明|
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|调用 `CloseThemeData` 中获得的所有句柄 `UpdateSystemColors` 。|
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|调用 `OpenThemeData` 以获取用于绘制各种控件的句柄：窗口、工具栏、按钮等。|

## <a name="remarks"></a>备注

不需要直接实例化此类的对象。

由于它是所有可视化管理器的基类，因此你可以仅调用 [CMFCVisualManager：： GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)，获取指向当前视觉对象管理器的指针，并访问 `CMFCBaseVisualManager` 使用该指针的方法。 但是，如果您必须使用当前 Windows 主题显示控件，则最好使用 `CMFCVisualManagerWindows` 接口。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>要求

**标头：** afxvisualmanager

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a> CMFCBaseVisualManager::CleanUpThemes

调用 `CloseThemeData` 中获得的所有句柄 `UpdateSystemColors` 。

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>备注

仅限内部使用。

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a> CMFCBaseVisualManager::CMFCBaseVisualManager

构造并初始化一个 `CMFCBaseVisualManager` 对象。

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a> CMFCBaseVisualManager：:D rawCheckBox

使用当前 Windows 主题绘制复选框控件。

```
virtual BOOL DrawCheckBox(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    int nState,
    BOOL bEnabled,
    BOOL bPressed);

);
```

### <a name="parameters"></a>参数

*pDC*<br/>
中指向设备上下文的指针

*rect*<br/>
中复选框的边框。

*bHighlighted*<br/>
中指定是否突出显示复选框。

*nState*<br/>
[in] 0 表示未选中，1表示选中正常，

2适用于 mixed normal。

*bEnabled*<br/>
中指定是否启用复选框。

*bPressed*<br/>
中指定是否按下复选框。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

*NState*的值对应于下面的复选框样式。

|nState|复选框样式|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a> CMFCBaseVisualManager：:D rawComboBorder

使用当前 Windows 主题绘制组合框边框。

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>参数

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中组合框边框的边框。

*bDisabled*<br/>
中指定组合框边框是否处于禁用状态。

*bIsDropped*<br/>
中指定是否下拉组合框边框。

*bIsHighlighted*<br/>
中指定是否突出显示组合框边框。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a> CMFCBaseVisualManager：:D rawComboDropButton

使用当前 Windows 主题绘制组合框下拉按钮。

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>参数

*pDC*\
中指向设备上下文的指针。

*rect*\
中组合框下拉按钮的边框。

*bDisabled*\
中指定组合框下拉按钮是否处于禁用状态。

*bIsDropped*\
中指定是否下拉组合框下拉按钮。

*bIsHighlighted*\
中指定是否突出显示组合框下拉按钮。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a> CMFCBaseVisualManager：:D rawPushButton

使用当前 Windows 主题绘制一个按钮。

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>参数

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中"推送" 按钮的边框。

*pButton*<br/>
中指向要绘制的 [CMFCButton 类](../../mfc/reference/cmfcbutton-class.md) 对象的指针。

*uiState*<br/>
中掉. 状态是从 *pButton*获取的。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a> CMFCBaseVisualManager：:D rawRadioButton

使用当前 Windows 主题绘制单选按钮控件。

```
virtual BOOL DrawRadioButton(
    CDC* pDC,
    CRect rect,
    BOOL bHighlighted,
    BOOL bChecked,
    BOOL bEnabled,
    BOOL bPressed);
```

### <a name="parameters"></a>参数

*pDC*<br/>
中指向设备上下文的指针。

*rect*<br/>
中单选按钮的边框。

*bHighlighted*<br/>
中指定是否突出显示单选按钮。

*bChecked*<br/>
中指定是否选中单选按钮。

*bEnabled*<br/>
中指定是否启用单选按钮。

*bPressed*<br/>
中指定是否按下单选按钮。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a> CMFCBaseVisualManager：:D rawStatusBarProgress

使用当前 Windows 主题 ( [CMFCStatusBar 类](../../mfc/reference/cmfcstatusbar-class.md)) 在状态栏控件上绘制进度栏。

```
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,
    CMFCStatusBar* pStatusBar,
    CRect rectProgress,
    int nProgressTotal,
    int nProgressCurr,
    COLORREF clrBar,
    COLORREF clrProgressBarDest,
    COLORREF clrProgressText,
    BOOL bProgressText);
```

### <a name="parameters"></a>参数

*pDC*<br/>
中指向设备上下文的指针。

*pStatusBar*<br/>
中指向状态栏的指针。 忽略此值。

*rectProgress*<br/>
中 *PDC* 坐标中进度栏的边框。

*nProgressTotal*<br/>
中总进度值。

*nProgressCurr*<br/>
中当前进度值。

*clrBar*<br/>
中开始颜色。 `CMFCBaseVisualManager` 忽略此情况。 派生类可以使用它进行颜色渐变。

*clrProgressBarDest*<br/>
中结束颜色。 `CMFCBaseVisualManager` 忽略此情况。 派生类可以使用它进行颜色渐变。

*clrProgressText*<br/>
中进度文本颜色。 `CMFCBaseVisualManager` 忽略此情况。 文本颜色由定义 `afxGlobalData.clrBtnText` 。

*bProgressText*<br/>
中指定是否显示进度文本。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a> CMFCBaseVisualManager::FillReBarPane

使用当前 Windows 主题填充 rebar 控件的背景。

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>参数

*pDC*<br/>
中指向设备上下文的指针。

*pBar*<br/>
中指向应绘制背景的窗格的指针。

*rectClient*<br/>
中要填充的区域的边框。

### <a name="return-value"></a>返回值

如果启用主题 API，则为 TRUE;否则为 FALSE。

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a> CMFCBaseVisualManager::GetStandardWindowsTheme

获取当前的 Windows 主题。

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>返回值

当前选定的 Windows 主题颜色。 可以是下列枚举值之一：

- `WinXpTheme_None` -没有启用主题。

- `WinXpTheme_NonStandard` -选择了 "非标准主题" (意味着选择了主题，但没有从以下列表中) 。

- `WinXpTheme_Blue` -blue 主题 (Luna) 。

- `WinXpTheme_Olive` -橄榄色。

- `WinXpTheme_Silver` -白银主题。

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a> CMFCBaseVisualManager::UpdateSystemColors

调用 `OpenThemeData` 以获取用于绘制各种控件的句柄：窗口、工具栏、按钮等。

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>备注

仅限内部使用。

## <a name="see-also"></a>另请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)

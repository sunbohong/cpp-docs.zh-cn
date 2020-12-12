---
description: 了解详细信息： CTooltipManager 类
title: CTooltipManager 类
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: 0ec6d691abbceb7026fe9656c17ff899f1d07759
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318541"
---
# <a name="ctooltipmanager-class"></a>CTooltipManager 类

维护有关工具提示的运行时信息。 `CTooltipManager` 类在每个应用程序中实例化一次。

## <a name="syntax"></a>语法

```
class CTooltipManager : public CObject
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTooltipManager::CreateToolTip](#createtooltip)|为指定的 Windows 控件类型创建工具提示控件。|
|[CTooltipManager::DeleteToolTip](#deletetooltip)|删除工具提示控件。|
|[CTooltipManager::SetTooltipParams](#settooltipparams)|自定义指定 Windows 控件类型工具提示的可视外观。|
|[CTooltipManager::SetTooltipText](#settooltiptext)|设置工具提示控件的文本和说明。|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>备注

在应用程序中使用 [CMFCToolTipCtrl 类](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo` 和 `CTooltipManager` 来实现自定义的工具提示。 有关如何使用这些 tooltip 类的示例，请参阅 [CMFCToolTipCtrl 类](../../mfc/reference/cmfctooltipctrl-class.md) 主题。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>要求

**标头：** afxtooltipmanager

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a> CTooltipManager：： CreateToolTip

创建 tooltip 控件。

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>parameters

*pToolTip*<br/>
弄对工具提示指针的引用。 当函数返回时，它设置为指向新创建的工具提示。

*pWndParent*<br/>
中Tooltip 的父级。

nType<br/>
中工具提示的类型。

### <a name="return-value"></a>返回值

如果工具提示已成功创建，则为非零值。

### <a name="remarks"></a>备注

必须调用 [CTooltipManager：:D eletetooltip](#deletetooltip) 删除在 *pToolTip* 中传递回来的 tooltip 控件。

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)根据 *n* 指定的工具提示类型设置所创建的每个工具提示的可视显示参数。 若要更改一个或多个工具提示类型的参数，请调用 [CTooltipManager：： SetTooltipParams](#settooltipparams)。

下表列出了有效的工具提示类型：

|Tooltip 类型|控件类别|示例类型|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|按钮。|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|标题栏。|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|不适合其他类别的任何控件。|无。|
|AFX_TOOLTIP_TYPE_DOCKBAR|可停靠的窗格。|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|文本框。|无。|
|AFX_TOOLTIP_TYPE_MINIFRAME|微型框。|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Planner。|无。|
|AFX_TOOLTIP_TYPE_RIBBON|功能区栏。|CMFCRibbonBar、CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|选项卡控件。|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|工具栏。|CMFCToolBar、CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|工具箱。|无。|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a> CTooltipManager：:D eleteToolTip

删除工具提示控件。

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>parameters

*pToolTip*<br/>
[in，out]指向要销毁的工具提示的指针的引用。

### <a name="remarks"></a>备注

为[CTooltipManager：： CreateToolTip](#createtooltip)创建的每个[CToolTipCtrl 类](../../mfc/reference/ctooltipctrl-class.md)调用此方法。 父控件应从其处理程序中调用此方法 `OnDestroy` 。 若要从框架中正确删除工具提示，这是必需的。 此方法在返回之前将 *pToolTip* 设置为 NULL。

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a> CTooltipManager：： SetTooltipParams

自定义指定 Windows 控件类型的 tooltip 控件的外观。

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>parameters

*nTypes*<br/>
中指定控件类型。

*pRTC*<br/>
中自定义工具提示的运行时类。

*pParams*<br/>
中Tooltip 参数。

### <a name="remarks"></a>备注

此方法设置 [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) 创建工具提示时使用的运行时类和初始参数。 当控件调用 [CTooltipManager：： CreateToolTip](#createtooltip) 并传入作为 *nTypes* 指示的类型之一的工具提示类型时，工具提示管理器会创建一个 tooltip 控件，该控件是 *pRTC* 指定的运行时类的实例，并将 *pParams* 指定的参数传递给新的工具提示。

调用此方法时，所有现有的工具提示所有者都将收到 AFX_WM_UPDATETOOLTIPS 消息，并且必须通过使用 [CTooltipManager：： CreateToolTip](#createtooltip)重新创建其工具提示。

*nTypes* 可以是 [CTooltipManager：： CreateToolTip](#createtooltip) 使用的有效 tooltip 类型的任意组合，也可以 AFX_TOOLTIP_TYPE_ALL。 如果传递 AFX_TOOLTIP_TYPE_ALL，则将影响所有工具提示类型。

### <a name="example"></a>示例

下面的示例演示如何使用类的 `SetTooltipParams` 方法 `CTooltipManager` 。 此代码片段属于 [Draw Client 示例](../../overview/visual-cpp-samples.md)。

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a> CTooltipManager：： SetTooltipText

设置工具提示的文本和说明。

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>parameters

*pTI*<br/>
中指向 TOOLINFO 对象的指针。

*pToolTip*<br/>
[in，out]一个指针，指向要为其设置文本和说明的 tooltip 控件。

nType<br/>
中指定与此工具提示关联的控件的类型。

*strText*<br/>
中要设置为工具提示文本的文本。

*lpszDescr*<br/>
中指向工具提示说明的指针。 可以为 NULL。

### <a name="remarks"></a>备注

创建工具提示时， *n* 的值必须与 [CTooltipManager：： CreateToolTip](#createtooltip)的 *n* 参数的值相同。

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a> CTooltipManager：： UpdateTooltips

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolTipCtrl 类](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFCToolTipInfo 类](../../mfc/reference/cmfctooltipinfo-class.md)

---
description: 了解详细信息： CMFCDesktopAlertWnd 类
title: CMFCDesktopAlertWnd Class
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: 45b75bdbd24a88a7eacff124bb07ac81e7703c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330090"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class

`CMFCDesktopAlertWnd`类实现显示在屏幕上的无模式对话框的功能，以向用户通知事件。

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

## <a name="syntax"></a>语法

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCDesktopAlertWnd：： Create](#create)|创建并初始化桌面警报窗口。|
|[CMFCDesktopAlertWnd：： GetAnimationSpeed](#getanimationspeed)|返回动画速度。|
|[CMFCDesktopAlertWnd：： GetAnimationType](#getanimationtype)|返回动画类型。|
|[CMFCDesktopAlertWnd：： GetAutoCloseTime](#getautoclosetime)|返回自动关闭超时。|
|[CMFCDesktopAlertWnd：： GetCaptionHeight](#getcaptionheight)|返回标题的高度。|
|[CMFCDesktopAlertWnd：： GetDialogSize](#getdialogsize)||
|[CMFCDesktopAlertWnd：： GetLastPos](#getlastpos)|返回桌面警报窗口在屏幕上的最后一个有效位置。|
|[CMFCDesktopAlertWnd：： GetTransparency](#gettransparency)|返回透明度级别。|
|[CMFCDesktopAlertWnd：： HasSmallCaption](#hassmallcaption)|确定是否显示带有小标题的桌面警报窗口。|
|[CMFCDesktopAlertWnd：： OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd：： OnClickLinkButton](#onclicklinkbutton)|当用户单击位于桌面警报菜单上的链接按钮时由框架调用。|
|[CMFCDesktopAlertWnd：： OnCommand](#oncommand)|当用户从菜单中选择项、当子控件发送通知消息时，或在翻译加速键击时，框架会调用此成员函数。  (将重写 [CWnd：： OnCommand](../../mfc/reference/cwnd-class.md#oncommand)。 ) |
|[CMFCDesktopAlertWnd：： OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd：:P rocessCommand](#processcommand)||
|[CMFCDesktopAlertWnd：： SetAnimationSpeed](#setanimationspeed)|设置新的动画速度。|
|[CMFCDesktopAlertWnd：： SetAnimationType](#setanimationtype)|设置动画类型。|
|[CMFCDesktopAlertWnd：： SetAutoCloseTime](#setautoclosetime)|设置自动关闭超时。|
|[CMFCDesktopAlertWnd：： SetSmallCaption](#setsmallcaption)|在小型和普通字幕之间切换。|
|[CMFCDesktopAlertWnd：： SetTransparency](#settransparency)|设置透明度级别。|

## <a name="remarks"></a>备注

桌面警报窗口可以是透明的，它可能会显示动画效果，并且在指定的延迟之后或用户通过单击 "关闭" 按钮)  (将其关闭。

桌面警报窗口还可以包含一个默认对话框，该对话框又包含一个图标、 (标签) 的消息文本和一个链接。 或者，桌面警报窗口可以包含应用程序资源中的自定义对话框。

可以通过两个步骤创建桌面警报窗口。 首先，调用构造函数来构造 `CMFCDesktopAlertWnd` 对象。 然后，调用 [CMFCDesktopAlertWnd：： create](#create) 成员函数以创建窗口并将其附加到 `CMFCDesktopAlertWnd` 对象。

`CMFCDesktopAlertWnd`对象创建一个特殊的子对话框，用于填充桌面警报窗口的工作区。 此对话框拥有所有定位在其上的控件。

若要在弹出窗口中显示自定义对话框，请执行以下步骤：

1. 从 `CMFCDesktopAlertDialog` 派生一个类。

1. 在资源中创建子对话框模板。

1. 调用 [CMFCDesktopAlertWnd：： Create](#create) ，使用对话框模板的资源 ID 和指向派生类的运行时类信息的指针。

1. 对自定义对话框进行编程以处理来自寄宿控件的所有通知，或对承载的控件进行编程以直接处理这些通知。

使用以下函数来控制桌面警报窗口的行为：

- 通过调用 [CMFCDesktopAlertWnd：： SetAnimationType](#setanimationtype)设置动画类型。 有效选项包括 "展开"、"幻灯片" 和 "淡化"。

- 通过调用 [CMFCDesktopAlertWnd：： SetAnimationSpeed](#setanimationspeed)设置动画帧速度。

- 通过调用 [CMFCDesktopAlertWnd：： SetTransparency](#settransparency)设置透明度级别。

- 通过调用 [CMFCDesktopAlertWnd：： SetSmallCaption](#setsmallcaption)将标题的大小更改为 small。 小标题为7像素高。

## <a name="example"></a>示例

下面的示例演示如何使用类中的各种方法 `CMFCDesktopAlertWnd` 配置 `CMFCDesktopAlertWnd` 对象。 该示例演示如何设置动画类型、设置弹出窗口的透明度、指定 "警报" 窗口显示小标题，并设置在警报窗口自动关闭前经过的时间。 该示例还演示了如何创建和初始化桌面警报窗口。 此代码片段是 [桌面警报演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>要求

**标头：** afxDesktopAlertWnd

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a> CMFCDesktopAlertWnd：： Create

创建并初始化桌面警报窗口。

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>parameters

*pWndOwner*<br/>
[in，out]指定警报窗口的所有者。 然后，该所有者将接收桌面警报窗口的所有通知。 此值不能为 NULL。

*uiDlgResID*<br/>
中指定警报窗口的资源 ID。

*hMenu*<br/>
中指定用户单击菜单按钮时显示的菜单。 如果为 NULL，则不会显示菜单按钮。

*ptPos*<br/>
中使用屏幕坐标指定显示警报窗口的初始位置。 如果此参数 (-1，-1) ，则在屏幕的右下角将显示警报窗口。

*pRTIDlgBar*<br/>
中自定义对话框类的运行时类信息，该对话框涵盖警报窗口的工作区。

*params*<br/>
中指定用于创建警报窗口的参数。

### <a name="return-value"></a>返回值

如果成功创建警报窗口，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此方法可创建警报窗口。 警报窗口的工作区包含一个子对话框，该对话框承载向用户显示的所有控件。

第一种方法重载会创建一个警报窗口，其中包含从应用程序资源加载的子对话框。 第一种方法重载还可以指定自定义对话框类的运行时类信息。

第二个方法重载创建包含默认控件的警报窗口。 可以通过修改 [CMFCDesktopAlertWndInfo 类](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)来指定要显示的控件。

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a> CMFCDesktopAlertWnd：： GetAnimationSpeed

返回动画速度。

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>返回值

警报窗口的动画速度（以毫秒为单位）。

### <a name="remarks"></a>备注

动画速度介绍了 "警报" 窗口打开和关闭的速度。

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a> CMFCDesktopAlertWnd：： GetAnimationType

返回动画类型。

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>返回值

以下动画类型之一：

- NO_ANIMATION

- 展开

- 第

- 淡化

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a> CMFCDesktopAlertWnd：： GetAutoCloseTime

返回自动关闭超时。

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>返回值

警报时段将自动关闭的时间（以毫秒为单位）。

### <a name="remarks"></a>备注

使用此方法来确定应经过多长时间后，警报时段才会自动关闭。

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a> CMFCDesktopAlertWnd：： GetCaptionHeight

返回标题的高度。

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>返回值

标题的高度（以像素为单位）。

### <a name="remarks"></a>备注

此方法可在派生类中重写。 默认实现：返回 (7 像素) 的小标题高度值（如果弹出窗口应显示小标题）或从 Windows API 函数获取的值 `GetSystemMetrics(SM_CYSMCAPTION)` 。

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a> CMFCDesktopAlertWnd：： GetLastPos

返回桌面警报窗口在屏幕上的最后一个位置。

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>返回值

屏幕坐标中的点。

### <a name="remarks"></a>备注

此方法返回屏幕上警报窗口的最后一个有效位置。

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a> CMFCDesktopAlertWnd：： GetTransparency

返回透明度级别。

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>返回值

介于0到255（含）之间的透明度级别。 值越大，窗口的不透明度就越多。

### <a name="remarks"></a>备注

使用此方法可检索警报窗口的当前透明度级别。

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a> CMFCDesktopAlertWnd：： HasSmallCaption

确定 "桌面警报" 窗口的标题是小标题还是常规大小的标题。

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>返回值

如果弹出窗口显示小标题，则为 TRUE;如果弹出窗口显示的标题为固定大小，则为 FALSE。

### <a name="remarks"></a>备注

使用此方法可以确定弹出窗口是具有小标题还是常规大小的标题。 默认情况下，小标题为7像素高。 可以通过调用 Windows API 函数获取常规大小标题的高度 `GetSystemMetrics(SM_CYCAPTION)` 。

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a> CMFCDesktopAlertWnd：： OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>parameters

中 *CPoint&*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a> CMFCDesktopAlertWnd：： OnClickLinkButton

当用户单击位于桌面警报菜单上的链接按钮时由框架调用。

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>parameters

*uiCmdID*<br/>
中未使用此参数。

### <a name="return-value"></a>返回值

始终为 FALSE。

### <a name="remarks"></a>备注

如果希望在用户单击警报窗口上的链接时收到通知，则在派生类中重写此方法。

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a> CMFCDesktopAlertWnd：： OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>parameters

中 *wParam*<br/>

中 *lParam*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a> CMFCDesktopAlertWnd：： OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>parameters

中 *pDC*<br/>

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a> CMFCDesktopAlertWnd：:P rocessCommand

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>parameters

中 *hwnd*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a> CMFCDesktopAlertWnd：： SetAnimationSpeed

设置新的动画速度。

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>parameters

*nSpeed*<br/>
中指定新动画的速度（以毫秒为单位）。

### <a name="remarks"></a>备注

调用此方法可设置警报窗口的动画速度。 默认动画速度为30毫秒。

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a> CMFCDesktopAlertWnd：： SetAnimationType

设置动画类型。

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>参数

type<br/>
中指定动画类型。

### <a name="remarks"></a>备注

调用此方法可设置动画类型。 可以指定以下值之一：

- NO_ANIMATION

- 展开

- 第

- 淡化

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a> CMFCDesktopAlertWnd：： SetAutoCloseTime

设置自动关闭超时。

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>parameters

*n*<br/>
中警报窗口自动关闭前经过的时间（以毫秒为单位）。

### <a name="remarks"></a>备注

如果用户不与窗口交互，则 "警报" 窗口将在指定时间后自动关闭。

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a> CMFCDesktopAlertWnd：： SetSmallCaption

在小型和标准标题之间切换。

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>parameters

*bSmallCaption*<br/>
中若要指定警报窗口显示小标题，则为 TRUE;否则为 FALSE，则指定 "警报" 窗口显示一个大小相同的标题。

### <a name="remarks"></a>备注

调用此方法可显示小标题或常规大小的标题。 默认情况下，小标题为7像素高。 可以通过调用 Windows API 函数获取常规标题的大小 `GetSystemMetrics(SM_CYCAPTION)` 。

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a> CMFCDesktopAlertWnd：： SetTransparency

设置弹出窗口的透明度级别。

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>parameters

*nTransparency*<br/>
中指定透明度级别。 此值必须介于0到255（含）之间。 值越大，窗口的不透明度就越多。

### <a name="remarks"></a>备注

调用此函数可设置弹出窗口的透明度级别。

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a> CMFCDesktopAlertWnd：： GetDialogSize

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWndInfo 类](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CMFCDesktopAlertDialog 类](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[CWnd 类](../../mfc/reference/cwnd-class.md)

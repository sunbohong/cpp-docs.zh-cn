---
description: 了解详细信息： CMFCDesktopAlertWndButton 类
title: CMFCDesktopAlertWndButton 类
ms.date: 11/04/2016
f1_keywords:
- CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCaptionButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWndButton::IsCloseButton
helpviewer_keywords:
- CMFCDesktopAlertWndButton [MFC], IsCaptionButton
- CMFCDesktopAlertWndButton [MFC], IsCloseButton
ms.assetid: df39a0c8-0c39-4ab0-8c64-78c5b2c4ecaf
ms.openlocfilehash: 0c645f4ec79aaa58364cfa9688d19915ece205bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330080"
---
# <a name="cmfcdesktopalertwndbutton-class"></a>CMFCDesktopAlertWndButton 类

允许将按钮添加到 "桌面警报" 对话框。

## <a name="syntax"></a>语法

```
class CMFCDesktopAlertWndButton : public CMFCButton
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|-|-|
|`CMFCDesktopAlertWndButton::CMFCDesktopAlertWndButton`|默认构造函数。|
|`CMFCDesktopAlertWndButton::~CMFCDesktopAlertWndButton`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|-|-|
|[CMFCDesktopAlertWndButton::IsCaptionButton](#iscaptionbutton)|确定按钮是否显示在警报对话框的标题区中。|
|[CMFCDesktopAlertWndButton::IsCloseButton](#isclosebutton)|确定按钮是否关闭警报对话框。|

### <a name="data-members"></a>数据成员

|名称|描述|
|-|-|
|`CMFCDesktopAlertWndButton::m_bIsCaptionButton`|一个布尔值，该值指定按钮是否显示在警报对话框的标题区中。|
|`CMFCDesktopAlertWndButton::m_bIsCloseButton`|一个布尔值，该值指定按钮是否关闭警报对话框。|

### <a name="remarks"></a>备注

默认情况下，构造函数将 `m_bIsCaptionButton` 和 `m_bIsCloseButton` 数据成员设置为 FALSE。 `CMFCDesktopAlertDialog` `m_bIsCaptionButton` 如果按钮定位在警报对话框的标题区中，则父对象将设置为 TRUE。 `CMFCDesktopAlertDialog`类创建一个 `CMFCDesktopAlertWndButton` 对象，该对象用作关闭警报对话框并将设置为 TRUE 的按钮 `m_bIsCloseButton` 。

将 `CMFCDesktopAlertWndButton` 对象添加到对象中，就 `CMFCDesktopAlertDialog` 像添加任何按钮一样。 有关的详细信息 `CMFCDesktopAlertDialog` ，请参阅 [CMFCDesktopAlertDialog 类](../../mfc/reference/cmfcdesktopalertdialog-class.md)。

## <a name="example"></a>示例

下面的示例演示如何使用 `SetImage` 类中的方法 `CMFCDesktopAlertWndButton` 。 此代码片段是 [桌面警报演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_DesktopAlertDemo#4](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_1.h)]
[!code-cpp[NVC_MFC_DesktopAlertDemo#5](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndbutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCDesktopAlertWndButton](../../mfc/reference/cmfcdesktopalertwndbutton-class.md)

## <a name="requirements"></a>要求

**标头：** afxdesktopalertwnd

## <a name="cmfcdesktopalertwndbuttoniscaptionbutton"></a><a name="iscaptionbutton"></a> CMFCDesktopAlertWndButton::IsCaptionButton

确定按钮是否显示在警报对话框的标题区中。

```
BOOL IsCaptionButton() const;
```

### <a name="return-value"></a>返回值

如果按钮显示在警报对话框的标题区中，则为非零值;否则为0。

## <a name="cmfcdesktopalertwndbuttonisclosebutton"></a><a name="isclosebutton"></a> CMFCDesktopAlertWndButton::IsCloseButton

确定按钮是否关闭警报对话框。

```
BOOL IsCloseButton() const;
```

### <a name="return-value"></a>返回值

如果按钮关闭警报对话框，则为非零值;否则为0。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertDialog 类](../../mfc/reference/cmfcdesktopalertdialog-class.md)

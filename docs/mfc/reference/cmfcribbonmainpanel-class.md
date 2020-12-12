---
description: 了解详细信息： CMFCRibbonMainPanel 类
title: CMFCRibbonMainPanel 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::Add
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddRecentFilesList
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToBottom
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::AddToRight
- AFXRIBBONMAINPANEL/CMFCRibbonMainPanel::GetCommandsFrame
helpviewer_keywords:
- CMFCRibbonMainPanel [MFC], Add
- CMFCRibbonMainPanel [MFC], AddRecentFilesList
- CMFCRibbonMainPanel [MFC], AddToBottom
- CMFCRibbonMainPanel [MFC], AddToRight
- CMFCRibbonMainPanel [MFC], GetCommandsFrame
ms.assetid: 1af78798-5e75-4365-9c81-a54aa5679602
ms.openlocfilehash: 823a1ce8a8684ca791f838346a1fb50727096a62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321801"
---
# <a name="cmfcribbonmainpanel-class"></a>CMFCRibbonMainPanel 类

实现在单击 [CMFCRibbonApplicationButton](../../mfc/reference/cmfcribbonapplicationbutton-class.md)时显示的功能区面板。

## <a name="syntax"></a>语法

```
class CMFCRibbonMainPanel : public CMFCRibbonPanel
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCRibbonMainPanel::CMFCRibbonMainPanel`|默认构造函数。|
|`CMFCRibbonMainPanel::~CMFCRibbonMainPanel`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonMainPanel：： Add](#add)|将功能区元素添加到应用程序按钮面板的左窗格中。  (重写 [CMFCRibbonPanel：： Add](../../mfc/reference/cmfcribbonpanel-class.md#add). ) |
|[CMFCRibbonMainPanel::AddRecentFilesList](#addrecentfileslist)|将文本字符串添加到 "最近使用的文件" 列表菜单。|
|[CMFCRibbonMainPanel::AddToBottom](#addtobottom)|将功能区元素添加到功能区应用程序面板的底部窗格中。|
|[CMFCRibbonMainPanel::AddToRight](#addtoright)|将功能区元素添加到应用程序按钮面板的右窗格中。|
|`CMFCRibbonMainPanel::CreateObject`|由框架用于创建此类类型的动态实例。|
|[CMFCRibbonMainPanel::GetCommandsFrame](#getcommandsframe)|返回一个矩形，该矩形表示功能区主面板的区域。|
|`CMFCRibbonMainPanel::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|

## <a name="remarks"></a>备注

`CMFCRibbonMainPanel`打开应用程序面板时，框架会显示。 它包含三个窗格：

- 左窗格包含与文件相关联的命令，例如 **打开**、 **保存**、 **打印** 和 **关闭**。 若要向此窗格添加命令，请调用 [CMFCRibbonMainPanel：： add](#add)。

- 右窗格包含用于修改您在左窗格中单击的命令的选项。 例如，如果在左窗格中单击 " **另存为** "，右窗格会显示可用的文件类型。 若要将项添加到此窗格，请调用 [CMFCRibbonMainPanel：： AddToRight](#addtoright)。

- 下窗格包含的按钮允许您更改应用程序的设置并退出程序。 若要将项添加到此窗格，请调用 [CMFCRibbonMainPanel：： AddToBottom](#addtobottom)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonPanel](../../mfc/reference/cmfcribbonpanel-class.md)

[CMFCRibbonMainPanel](../../mfc/reference/cmfcribbonmainpanel-class.md)

## <a name="requirements"></a>要求

**标头：** afxRibbonMainPanel

## <a name="cmfcribbonmainpaneladd"></a><a name="add"></a> CMFCRibbonMainPanel：： Add

将功能区元素添加到应用程序按钮面板的左窗格中。

```
virtual void Add(CMFCRibbonBaseElement* pElem);
```

### <a name="parameters"></a>parameters

*pElem*<br/>
[in，out]指向要添加到主面板的功能区元素的指针。

### <a name="remarks"></a>备注

将功能区元素添加到面板。 使用此方法添加的元素将位于主面板的左列中。

## <a name="cmfcribbonmainpaneladdrecentfileslist"></a><a name="addrecentfileslist"></a> CMFCRibbonMainPanel::AddRecentFilesList

将文本字符串添加到 "最近使用的文件" 列表菜单。

```cpp
void AddRecentFilesList(
    LPCTSTR lpszLabel,
    int nWidth = 300);
```

### <a name="parameters"></a>parameters

*lpszLabel*<br/>
指定要添加到 "最近使用的文件" 列表中的字符串。

*nWidth*<br/>
指定 "最近使用的文件" 列表面板的宽度（以像素为单位）。

### <a name="remarks"></a>备注

## <a name="cmfcribbonmainpaneladdtobottom"></a><a name="addtobottom"></a> CMFCRibbonMainPanel::AddToBottom

将功能区元素添加到功能区应用程序面板的底部窗格中。

```cpp
void AddToBottom(CMFCRibbonMainPanelButton* pElem);
```

### <a name="parameters"></a>parameters

*pElem*<br/>
[in，out]一个指针，指向要添加到主面板底部的功能区元素。

### <a name="remarks"></a>备注

## <a name="cmfcribbonmainpaneladdtoright"></a><a name="addtoright"></a> CMFCRibbonMainPanel::AddToRight

将功能区元素添加到应用程序按钮面板的右窗格中。

```cpp
void AddToRight(
    CMFCRibbonBaseElement* pElem,
    int nWidth = 300);
```

### <a name="parameters"></a>parameters

*pElem*<br/>
一个指针，指向要添加到主面板右侧的功能区元素。

*nWidth*<br/>
指定右面板的宽度（以像素为单位）。

### <a name="remarks"></a>备注

使用此函数可将功能区元素添加到右侧面板。 右侧面板通常显示 "最近使用的文件" 列表，但您可以在此处添加任何其他功能区元素。

## <a name="cmfcribbonmainpanelgetcommandsframe"></a><a name="getcommandsframe"></a> CMFCRibbonMainPanel::GetCommandsFrame

返回一个矩形，该矩形表示功能区主面板的区域。

```
CRect GetCommandsFrame() const;
```

### <a name="return-value"></a>返回值

一个表示功能区主面板的区域的矩形。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel 类](../../mfc/reference/cmfcribbonpanel-class.md)

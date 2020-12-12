---
description: 了解详细信息： CMFCRibbonQuickAccessToolBarDefaultState 类
title: CMFCRibbonQuickAccessToolBarDefaultState 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::AddCommand
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::CopyFrom
- AFXRIBBONQUICKACCESSTOOLBAR/CMFCRibbonQuickAccessToolBarDefaultState::RemoveAll
helpviewer_keywords:
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CMFCRibbonQuickAccessToolBarDefaultState
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], AddCommand
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], CopyFrom
- CMFCRibbonQuickAccessToolBarDefaultState [MFC], RemoveAll
ms.assetid: eca99200-b87b-47ba-b2e8-2f3f2444b176
ms.openlocfilehash: d6cd0c32cd8698259de0a78a6a6a7dc42012e92f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321795"
---
# <a name="cmfcribbonquickaccesstoolbardefaultstate-class"></a>CMFCRibbonQuickAccessToolBarDefaultState 类

一个帮助器类，它管理定位在功能区栏 ( [CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)) 上的快速访问工具栏的默认状态。

## <a name="syntax"></a>语法

```
class CMFCRibbonQuickAccessToolBarDefaultState
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState](#cmfcribbonquickaccesstoolbardefaultstate)|构造 `CMFCRibbonQuickAccessToolbarDefaultState` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonQuickAccessToolBarDefaultState：： AddCommand](#addcommand)|将命令添加到快速访问工具栏的默认状态。 这不会更改工具栏本身。|
|[CMFCRibbonQuickAccessToolBarDefaultState：： CopyFrom](#copyfrom)|将一个快速访问工具栏的属性复制到另一个。|
|[CMFCRibbonQuickAccessToolBarDefaultState：： RemoveAll](#removeall)|从快速访问工具栏中删除所有命令。 这不会更改工具栏本身。|

## <a name="remarks"></a>备注

在应用程序中创建快速访问工具栏后，建议通过调用 [CMFCRibbonBar：： SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate)设置其默认状态。 当用户在应用程序的 "**选项**" 对话框的 "**自定义**" 页上单击 "**重置**" 按钮时，将还原此默认状态。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMFCRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md)

## <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCRibbonQuickAccessToolbarDefaultState` ，以及如何将命令添加到快速访问工具栏的默认状态。

[!code-cpp[NVC_MFC_RibbonApp#21](../../mfc/reference/codesnippet/cpp/cmfcribbonquickaccesstoolbardefaultstate-class_1.cpp)]

## <a name="requirements"></a>要求

**标头：** afxribbonquickaccesstoolbar

## <a name="cmfcribbonquickaccesstoolbardefaultstateaddcommand"></a><a name="addcommand"></a> CMFCRibbonQuickAccessToolBarDefaultState：： AddCommand

将命令添加到快速访问工具栏的默认状态。

```cpp
void AddCommand(
    UINT uiCmd,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>parameters

*[in] uiCmd*<br/>
指定命令 ID。

*[in] bIsVisible*<br/>
当快速访问工具栏处于默认状态时，设置该命令的可见性。

### <a name="remarks"></a>备注

将命令添加到 CMFCRibbonQuickAccessToolBarDefaultState 可完成三个结果。 首先，每个添加的命令都列在快速访问工具栏右侧的下拉列表中。 通过这种方式，用户可以在快速访问工具栏中轻松地添加或删除该命令。 其次，在用户单击 "**自定义**" 对话框中的 "**重置**" 按钮时，"快速访问工具栏" 将重置为仅显示那些以默认状态列出的命令。 第三，如果未调用 [CMFCRibbonBar：： SetQuickAccessCommands](../../mfc/reference/cmfcribbonbar-class.md#setquickaccesscommands)，则在用户首次运行应用程序时，快速访问工具栏将使用此列表中的可见命令作为默认的可见命令。 添加了所需的所有命令后，调用 [CMFCRibbonBar：： SetQuickAccessDefaultState](../../mfc/reference/cmfcribbonbar-class.md#setquickaccessdefaultstate) 将此实例设置为该功能区栏的快速访问工具栏的默认状态。

## <a name="cmfcribbonquickaccesstoolbardefaultstatecopyfrom"></a><a name="copyfrom"></a> CMFCRibbonQuickAccessToolBarDefaultState：： CopyFrom

将一个快速访问工具栏的属性复制到另一个。

```cpp
void CopyFrom(const CMFCRibbonQuickAccessToolBarDefaultState& src);
```

### <a name="parameters"></a>parameters

*src*<br/>
中对 `CMFCRibbonQuickAccessToolBarDefaultState` 要从中进行复制的源对象的引用。

### <a name="remarks"></a>备注

此方法 `CMFCRibbonQuickAccessToolBarDefaultState` 通过使用 [CMFCRibbonQuickAccessToolBarDefaultState：： AddCommand](#addcommand) 方法将每个命令从源对象复制到此对象。

## <a name="cmfcribbonquickaccesstoolbardefaultstatecmfcribbonquickaccesstoolbardefaultstate"></a><a name="cmfcribbonquickaccesstoolbardefaultstate"></a> CMFCRibbonQuickAccessToolBarDefaultState::CMFCRibbonQuickAccessToolBarDefaultState

构造快速访问工具栏默认状态对象。

```
CMFCRibbonQuickAccessToolBarDefaultState();
```

### <a name="remarks"></a>备注

默认情况下， [CMFRibbonQuickAccessToolBarDefaultState](../../mfc/reference/cmfcribbonquickaccesstoolbardefaultstate-class.md) 的新实例所包含的命令的列表为空。

## <a name="cmfcribbonquickaccesstoolbardefaultstateremoveall"></a><a name="removeall"></a> CMFCRibbonQuickAccessToolBarDefaultState：： RemoveAll

在快速访问工具栏中清除默认命令的列表。

```cpp
void RemoveAll();
```

### <a name="remarks"></a>备注

此函数从此实例中删除先前对 [CMFCRibbonQuickAccessToolBarDefaultState：： AddCommand](#addcommand) 调用的所有命令。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)

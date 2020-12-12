---
description: 了解详细信息： CMFCTasksPaneTaskGroup 类
title: CMFCTasksPaneTaskGroup 类
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: 6b09923c70ad6208b1b029e6ad555c22cd4c771f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254698"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup 类

`CMFCTasksPaneTaskGroup`类是[CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)控件使用的帮助器类。 `CMFCTasksPaneTaskGroup` 类型的对象表示一个任务组 。 任务组是框架在具有折叠按钮的单独框中显示的项列表。 此框可具有一个可选标题（组名）。 如果一个组处于折叠状态，则任务列表不可见。

## <a name="syntax"></a>语法

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup：： CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|构造 `CMFCTasksPaneTaskGroup` 对象。|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup：： SetACCData](#setaccdata)|确定当前任务组的辅助功能数据。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup：： m_bIsBottom](#m_bisbottom)|确定任务组是否与任务窗格控件的底部对齐。|
|[CMFCTasksPaneTaskGroup：： m_bIsCollapsed](#m_biscollapsed)|确定任务组是否折叠。|
|[CMFCTasksPaneTaskGroup：： m_bIsSpecial](#m_bisspecial)|确定任务组是否为 *特殊组。* 框架以不同的颜色显示特殊的标题。|
|[CMFCTasksPaneTaskGroup：： m_lstTasks](#m_lsttasks)|包含任务的内部列表。|
|[CMFCTasksPaneTaskGroup：： m_rect](#m_rect)|指定组标题的边框。|
|[CMFCTasksPaneTaskGroup：： m_rectGroup](#m_rectgroup)|指定组的边框。|
|[CMFCTasksPaneTaskGroup：： m_strName](#m_strname)|指定组的名称。|

## <a name="remarks"></a>备注

下图显示了一个扩展的任务组：

![已展开的任务组](../../mfc/reference/media/nexttaskgrpexpand.png "已展开的任务组")

下图显示了一个折叠的任务组：

![已折叠的任务组](../../mfc/reference/media/nexttaskgrpcollapse.png "已折叠的任务组")

下图显示了不带标题的任务组：

![无标题的任务组](../../mfc/reference/media/nexttaskgrpnocapt.png "无标题的任务组")

下图显示了两个任务组。 将标志设置为 TRUE，将第一个任务组标记为特殊 `m_bIsSpecial` ，同时第二个任务组不是特殊组。 请注意，第一个任务组的标题比第二个任务组的标题更暗：

![特殊任务组](../../mfc/reference/media/nexttaskgrpspecial.png "特殊任务组")

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>要求

**标头：** afxtaskspane。h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a> CMFCTasksPaneTaskGroup：： CMFCTasksPaneTaskGroup

构造 `CMFCTasksPaneTaskGroup` 对象。

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>parameters

*lpszName*<br/>
指定组标题中组的名称。

*bIsBottom*<br/>
指定组是否与任务窗格控件的底部对齐。

*bIsSpecial*<br/>
指定组是否被指定为 *特殊* 组，以及是否使用不同的颜色填充组标题。

*bIsCollapsed*<br/>
指定组是否折叠。

*pPage*<br/>
指定此任务组所属的属性页。

*hIcon*<br/>
指定在组标题中显示的图标。

### <a name="remarks"></a>备注

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a> CMFCTasksPaneTaskGroup：： m_bIsBottom

确定任务组是否与任务窗格控件的底部对齐。

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>备注

只有一个组可以与任务窗格控件的底部对齐。 必须最后添加此任务组。 有关详细信息，请参阅 [CMFCTasksPane：： AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)。

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a> CMFCTasksPaneTaskGroup：： m_bIsCollapsed

确定任务组是否折叠。

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>备注

可以通过调用 [CMFCTasksPane：： EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)，启用或禁用折叠任务窗格上的组的功能。

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a> CMFCTasksPaneTaskGroup：： m_bIsSpecial

确定任务组是否是 *特殊* 的，以及是否应使用不同的颜色来标识特殊任务组的标题。

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>备注

如果你的应用程序使用的是 Windows XP 视觉主题且 `m_bIsSpecial` 为 FALSE，则框架将 `DrawThemeBackground` 使用 EBP_NORMALGROUPBACKGROUND 标志调用。 如果 `m_bIsSpecial` 为 TRUE，则框架将调用 `DrawThemeBackground` 并带有 EBP_SPECIALGROUPBACKGROUND 标志。

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a> CMFCTasksPaneTaskGroup：： m_lstTasks

包含任务的内部列表。

```
CObList m_lstTasks;
```

### <a name="remarks"></a>备注

若要填充此列表，请调用 [CMFCTasksPane：： AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask)。

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTaskGroup：： m_rect

指定组标题的边框。

```
CRect m_rect;
```

### <a name="remarks"></a>备注

此值由框架自动计算。

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a> CMFCTasksPaneTaskGroup：： m_rectGroup

指定组的边框。

```
CRect m_rectGroup;
```

### <a name="remarks"></a>备注

此值由框架自动计算。

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTaskGroup：： m_strName

指定组的名称。

```
CString m_strName;
```

### <a name="remarks"></a>备注

如果此值为空，则不显示组标题，并且不能折叠组。

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTaskGroup：： SetACCData

确定当前任务组的辅助功能数据。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>parameters

*pParent*<br/>
中表示当前任务组的父窗口。

*data*<br/>
弄一个类型为的对象，该对象 `CAccessibilityData` 用当前任务组的可访问性数据填充。

### <a name="return-value"></a>返回值

如果已成功用当前任务组的可访问性数据填充 *数据* 参数，则为 TRUE;否则为 FALSE。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane 类](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask 类](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar 类](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject 类](../../mfc/reference/cobject-class.md)

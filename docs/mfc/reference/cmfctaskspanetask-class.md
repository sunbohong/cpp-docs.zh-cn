---
description: 了解详细信息： CMFCTasksPaneTask 类
title: CMFCTasksPaneTask 类
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
ms.openlocfilehash: 8dad8520c938cae655143464189897d216a5f3ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306763"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask 类

`CMFCTasksPaneTask`类是一个帮助器类，它表示任务窗格控件的任务 ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)) 。 任务对象表示任务组 ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)) 中的项。 每个任务可具有在用户单击任务和显示在任务名称左侧的图标时框架所执行的命令。

## <a name="syntax"></a>语法

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCTasksPaneTask：： CMFCTasksPaneTask](#cmfctaskspanetask)|创建并初始化一个 `CMFCTasksPaneTask` 对象。|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCTasksPaneTask：： SetACCData](#setaccdata)|确定当前任务的辅助功能数据。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCTasksPaneTask：： m_bAutoDestroyWindow](#m_bautodestroywindow)|确定任务窗口是否自动销毁。|
|[CMFCTasksPaneTask：： m_bIsBold](#m_bisbold)|确定框架是否以粗体文本绘制任务标签。|
|[CMFCTasksPaneTask：： m_dwUserData](#m_dwuserdata)|包含框架与任务关联的用户定义数据。 如果任务没有关联数据，则设置为零。|
|[CMFCTasksPaneTask：： m_hwndTask](#m_hwndtask)|任务窗口的句柄。|
|[CMFCTasksPaneTask：： m_nIcon](#m_nicon)|框架在任务旁显示的图像的图像列表中的索引。|
|[CMFCTasksPaneTask：： m_nWindowHeight](#m_nwindowheight)|任务窗口的高度。 如果任务没有任务窗口，此值为零。|
|[CMFCTasksPaneTask：： m_pGroup](#m_pgroup)|指向 `CMFCTasksPaneTaskGroup` 此任务所属的的指针。|
|[CMFCTasksPaneTask：： m_rect](#m_rect)|指定任务的边框。|
|[CMFCTasksPaneTask：： m_strName](#m_strname)|任务的名称。|
|[CMFCTasksPaneTask：： m_uiCommandID](#m_uicommandid)|指定用户单击任务时框架执行的命令的命令 ID。 如果此值不是有效的命令 ID，则任务将被视为简单标签。|

## <a name="remarks"></a>备注

下图显示了包含三个任务的任务组：

![已展开的任务组](../../mfc/reference/media/nexttaskgrpexpand.png "已展开的任务组")

> [!NOTE]
> 如果任务没有有效的命令 ID，则会将其视为简单标签。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>要求

**标头：** afxtaskspane。h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a> CMFCTasksPaneTask：： CMFCTasksPaneTask

创建并初始化一个 `CMFCTasksPaneTask` 对象。

```
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,
    LPCTSTR lpszName,
    int nIcon,
    UINT uiCommandID,
    DWORD dwUserData = 0,
    HWND hwndTask = NULL,
    BOOL bAutoDestroyWindow = FALSE,
    int nWindowHeight = 0);
```

### <a name="parameters"></a>parameters

*pGroup*<br/>
指定任务所属的 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 。

*lpszName*<br/>
指定任务的名称。

*nIcon*<br/>
指定图像列表中任务图像的索引。

*uiCommandID*<br/>
指定单击任务时执行的命令的命令 ID。

*dwUserData*<br/>
用户定义数据。

*hwndTask*<br/>
指定任务窗口的句柄。

*bAutoDestroyWindow*<br/>
如果为 TRUE，则任务窗口将自动销毁。

*nWindowHeight*<br/>
指定任务窗口的高度。

### <a name="remarks"></a>备注

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a> CMFCTasksPaneTask：： m_bAutoDestroyWindow

确定任务窗口是否自动销毁。

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>备注

如果设置为 TRUE，则指定 ( [CMFCTasksPaneTask：： m_hwndTask](#m_hwndtask)) 应自动销毁的任务窗口;否则为 FALSE。

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a> CMFCTasksPaneTask：： m_bIsBold

确定是否以粗体文本绘制任务标签。

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>备注

将此成员设置为 TRUE 可显示任务标签的粗体文本。

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a> CMFCTasksPaneTask：： m_dwUserData

包含与任务关联的用户定义数据。 如果没有与任务相关联的数据，则设置为零。

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>备注

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a> CMFCTasksPaneTask：： m_hwndTask

任务窗口的句柄。

```
HWND m_hwndTask;
```

### <a name="remarks"></a>备注

若要添加任务窗口，请调用 [CMFCTasksPane：： AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)。

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a> CMFCTasksPaneTask：： m_nIcon

图像列表中的索引位置，该位置标识在指定任务旁显示的图像。

```
int m_nIcon;
```

### <a name="remarks"></a>备注

图像列表由 [CMFCTasksPane：： SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist)设置。

`m_nIcon`如果要显示不含图像的任务，则设置为-1。

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a> CMFCTasksPaneTask：： m_nWindowHeight

任务窗口的高度。 如果任务没有任务窗口，此值为零。

```
int m_nWindowHeight;
```

### <a name="remarks"></a>备注

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a> CMFCTasksPaneTask：： m_pGroup

指向此任务所属的 [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) 的指针。

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>备注

每个任务都必须具有父组。 可以通过调用 [CMFCTasksPane：： AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)将组添加到任务窗格。

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTask：： m_rect

指定任务的边框。

```
CRect m_rect;
```

### <a name="remarks"></a>备注

此值由框架在绘制任务时计算。

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTask：： m_strName

任务的名称。

```
CString m_strName;
```

### <a name="remarks"></a>备注

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a> CMFCTasksPaneTask：： m_uiCommandID

指定用户单击任务时执行的命令的命令 ID。 如果此值不是有效的命令 ID，则任务将被视为简单标签。

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>备注

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTask：： SetACCData

确定当前任务的辅助功能数据。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>parameters

*pParent*<br/>
中表示当前任务的父窗口。

*data*<br/>
弄一个类型为的对象，该对象 `CAccessibilityData` 用当前任务的可访问性数据填充。

### <a name="return-value"></a>返回值

如果已成功用当前任务的可访问性数据填充 *数据* 参数，则为 TRUE;否则为 FALSE。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CObject 类](../../mfc/reference/cobject-class.md)

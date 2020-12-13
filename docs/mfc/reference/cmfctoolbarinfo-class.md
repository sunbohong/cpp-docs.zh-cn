---
description: 了解详细信息： CMFCToolBarInfo 类
title: CMFCToolBarInfo 类
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo
- AFXTOOLBAR/CMFCToolBarInfo::m_uiColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeColdResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiLargeHotResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuDisabledResID
- AFXTOOLBAR/CMFCToolBarInfo::m_uiMenuResID
helpviewer_keywords:
- CMFCToolBarInfo [MFC], m_uiColdResID
- CMFCToolBarInfo [MFC], m_uiDisabledResID
- CMFCToolBarInfo [MFC], m_uiHotResID
- CMFCToolBarInfo [MFC], m_uiLargeColdResID
- CMFCToolBarInfo [MFC], m_uiLargeDisabledResID
- CMFCToolBarInfo [MFC], m_uiLargeHotResID
- CMFCToolBarInfo [MFC], m_uiMenuDisabledResID
- CMFCToolBarInfo [MFC], m_uiMenuResID
ms.assetid: 6dc84482-eaaa-491f-aa5d-dd7a57886b46
ms.openlocfilehash: 9b85ef4f39c8b42c35975a15836a21e7cc6dd6b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331703"
---
# <a name="cmfctoolbarinfo-class"></a>CMFCToolBarInfo 类

包含处于不同状态的工具栏图像的资源 ID。 `CMFCToolBarInfo` 是一个帮助器类，用于作为 [CMFCToolBar：： LoadToolBarEx](../../mfc/reference/cmfctoolbar-class.md#loadtoolbarex) 方法的参数。

## <a name="syntax"></a>语法

```
class CMFCToolBarInfo
```

## <a name="members"></a>成员

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCToolBarInfo：： m_uiColdResID](#m_uicoldresid)|包含普通 (冷) 工具栏图像的工具栏位图的资源 ID。|
|[CMFCToolBarInfo：： m_uiDisabledResID](#m_uidisabledresid)|包含禁用工具栏图像的工具栏位图的资源 ID。|
|[CMFCToolBarInfo：： m_uiHotResID](#m_uihotresid)|包含选定 (热) 工具栏图像的工具栏位图的资源 ID。|
|[CMFCToolBarInfo：： m_uiLargeColdResID](#m_uilargecoldresid)|工具栏位图的资源 ID，其中包含大型的常规工具栏图像。|
|[CMFCToolBarInfo：： m_uiLargeDisabledResID](#m_uilargedisabledresid)|包含大的禁用工具栏图像的工具栏位图的资源 ID。|
|[CMFCToolBarInfo：： m_uiLargeHotResID](#m_uilargehotresid)|包含所选工具栏图像的工具栏位图的资源 ID。|
|[CMFCToolBarInfo：： m_uiMenuDisabledResID](#m_uimenudisabledresid)|包含禁用的菜单图像的工具栏位图的资源 ID。|
|[CMFCToolBarInfo：： m_uiMenuResID](#m_uimenuresid)|包含菜单图像的工具栏位图的资源 ID。|

## <a name="remarks"></a>备注

完整的工具栏位图包含小工具栏图像 (按钮) 固定大小。 存储在对象中的每个资源 ID `CMFCToolBarInfo` 都是一种位图，其中包含以单个状态 (的一组完整的工具栏图像，如) 的选中、禁用、大或菜单图像。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMFCToolBarInfo](../../mfc/reference/cmfctoolbarinfo-class.md)

## <a name="requirements"></a>要求

**标头：** afxtoolbar

## <a name="cmfctoolbarinfom_uicoldresid"></a><a name="m_uicoldresid"></a> CMFCToolBarInfo：： m_uiColdResID

指定工具栏的所有常规按钮图像的资源 ID。

```
UINT m_uiColdResID;
```

## <a name="cmfctoolbarinfom_uidisabledresid"></a><a name="m_uidisabledresid"></a> CMFCToolBarInfo：： m_uiDisabledResID

为工具栏的 "按钮不可用" 图像指定资源 ID。

```
UINT m_uiDisabledResID;
```

## <a name="cmfctoolbarinfom_uihotresid"></a><a name="m_uihotresid"></a> CMFCToolBarInfo：： m_uiHotResID

指定工具栏的所有突出显示的按钮图像的资源 ID。

```
UINT m_uiHotResID
```

## <a name="cmfctoolbarinfom_uilargecoldresid"></a><a name="m_uilargecoldresid"></a> CMFCToolBarInfo：： m_uiLargeColdResID

指定工具栏的所有大型常规按钮图像的资源 ID。

```
UINT m_uiLargeColdResID
```

## <a name="cmfctoolbarinfom_uilargedisabledresid"></a><a name="m_uilargedisabledresid"></a> CMFCToolBarInfo：： m_uiLargeDisabledResID

指定工具栏的所有大禁用按钮图像的资源 ID。

```
UINT m_uiLargeDisabledResID;
```

## <a name="cmfctoolbarinfom_uilargehotresid"></a><a name="m_uilargehotresid"></a> CMFCToolBarInfo：： m_uiLargeHotResID

指定工具栏的所有大型突出显示图像的资源 ID。

```
UINT m_uiLargeHotResID;
```

## <a name="cmfctoolbarinfom_uimenudisabledresid"></a><a name="m_uimenudisabledresid"></a> CMFCToolBarInfo：： m_uiMenuDisabledResID

指定工具栏的 "命令不可用" 图像的资源 ID。

```
UINT m_uiMenuDisabledResID;
```

## <a name="cmfctoolbarinfom_uimenuresid"></a><a name="m_uimenuresid"></a> CMFCToolBarInfo：： m_uiMenuResID

指定工具栏的所有常规菜单项图像的资源 ID。

```
UINT m_uiMenuResID;
```

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar 类](../../mfc/reference/cmfctoolbar-class.md)

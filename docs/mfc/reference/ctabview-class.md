---
description: 了解详细信息： CTabView 类
title: CTabView 类
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: 59d4169bae108575fcf4844ec7c5c6e1e6681e28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345051"
---
# <a name="ctabview-class"></a>CTabView 类

`CTabView`类简化了在使用 MFC 文档/视图体系结构的应用程序中 ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) 的选项卡控件类的使用。

## <a name="syntax"></a>语法

```
class CTabbedView : public CView
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTabView::AddView](#addview)|将新视图添加到选项卡控件。|
|[CTabView::FindTab](#findtab)|返回选项卡控件中指定视图的索引。|
|[CTabView::GetActiveView](#getactiveview)|返回指向当前活动视图的指针|
|[CTabView::GetTabControl](#gettabcontrol)|返回对与视图关联的选项卡控件的引用。|
|[CTabView::RemoveView](#removeview)|从选项卡控件中删除视图。|
|[CTabView::SetActiveView](#setactiveview)|使视图处于活动状态。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CTabView::IsScrollBar](#isscrollbar)|在创建选项卡视图时由框架调用，以确定选项卡视图是否具有共享的水平滚动条。|
|[CTabView：： OnActivateView](#onactivateview)|当选项卡视图设为活动或非活动状态时由框架调用。|

## <a name="remarks"></a>备注

使用此类可以轻松地将选项卡式视图放置到文档/视图应用程序中。 `CTabView` 是 `CView` 包含嵌入对象的派生类 `CMFCTabCtrl` 。 `CTabView` 处理支持对象所需的所有消息 `CMFCTabCtrl` 。 只需从派生类 `CTabView` 并将其插入应用程序，然后 `CView` 使用方法添加派生类 `AddView` 。 选项卡控件将以选项卡的形式显示这些视图。

例如，您可能有一个可以通过不同的方式表示的文档：电子表格、图表、可编辑的窗体等。 您可以根据需要创建单个视图来绘制数据，将数据插入到 `CTabView` 派生的对象中，并使其具有选项卡式，无需任何其他编码。

[TabbedView 示例： MFC 选项卡式视图应用程序](../../overview/visual-cpp-samples.md) 阐释了的用法 `CTabView` 。

## <a name="example"></a>示例

下面的示例演示如何 `CTabView` 在 TabbedView 示例中使用。

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>要求

**标头：** afxTabView

## <a name="ctabviewaddview"></a><a name="addview"></a> CTabView::AddView

向选项卡控件添加视图。

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>parameters

*pViewClass*<br/>
中指向插入视图的运行时类的指针。

*strViewLabel*<br/>
中指定选项卡的文本。

*iIndex*<br/>
中指定从零开始的位置，将在该位置插入视图。 如果位置为-1，则在末尾插入新选项卡。

*pContext*<br/>
中指向视图的的指针 `CCreateContext` 。

### <a name="return-value"></a>返回值

如果此方法成功，则为视图索引。 否则，为 -1。

### <a name="remarks"></a>备注

调用此函数可将视图添加到框架中嵌入的选项卡控件。

## <a name="ctabviewfindtab"></a><a name="findtab"></a> CTabView::FindTab

返回选项卡控件中指定视图的索引。

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>parameters

*hWndView*<br/>
中视图的句柄。

### <a name="return-value"></a>返回值

如果找到，则为视图的索引;否则为-1。

### <a name="remarks"></a>备注

调用此函数可检索具有指定句柄的视图的索引。

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a> CTabView::GetActiveView

返回指向当前活动视图的指针。

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>返回值

指向活动视图的有效指针; 如果没有活动视图，则为 NULL。

### <a name="remarks"></a>备注

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a> CTabView::GetTabControl

返回对与视图关联的选项卡控件的引用。

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>返回值

对与视图关联的选项卡控件的引用。

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a> CTabView::IsScrollBar

在创建选项卡视图时由框架调用，以确定选项卡视图是否具有共享的水平滚动条。

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>返回值

如果应将选项卡视图与共享滚动条一起创建，则为 TRUE。 否则为 FALSE。

### <a name="remarks"></a>备注

在创建 *CTabView* 对象时，框架会调用此方法。

重写 *CTabView* 派生类中的 *IsScrollBar* 方法，如果想要创建具有共享水平滚动条的视图，则返回 TRUE。

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a> CTabView：： OnActivateView

当选项卡视图设为活动或非活动状态时由框架调用。

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>parameters

*view*<br/>
中指向视图的指针。

### <a name="remarks"></a>备注

默认实现不执行任何操作。 在派生类中重写此方法 `CTabView` 以处理此通知。

## <a name="ctabviewremoveview"></a><a name="removeview"></a> CTabView::RemoveView

从选项卡控件中删除视图。

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>parameters

*iTabNum*<br/>
中要删除的视图的索引。

### <a name="return-value"></a>返回值

如果此方法成功，则为已移除视图的索引。 否则为-1。

### <a name="remarks"></a>备注

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a> CTabView::SetActiveView

使视图处于活动状态。

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>parameters

*iTabNum*<br/>
中选项卡视图的从零开始的索引。

### <a name="return-value"></a>返回值

如果指定的视图处于活动状态，则为 TRUE; 如果该视图的索引无效，则为 FALSE。

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CMFCTabCtrl：： SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[CView 类](../../mfc/reference/cview-class.md)

---
description: 了解详细信息： CMFCHeaderCtrl 类
title: CListCtrl
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: a6be476e095dc4a013705657e259a90d7cafe0d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265371"
---
# <a name="cmfcheaderctrl-class"></a>CListCtrl

`CMFCHeaderCtrl`类支持对标头控件中的多个列进行排序。

## <a name="syntax"></a>语法

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCHeaderCtrl：： CMFCHeaderCtrl](#cmfcheaderctrl)|构造 `CMFCHeaderCtrl` 对象。|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCHeaderCtrl：： EnableMultipleSort](#enablemultiplesort)|启用或禁用当前标头控件的 *多个列排序* 模式。|
|[CMFCHeaderCtrl：： GetColumnState](#getcolumnstate)|指示列是否未排序，或者是否按升序或降序排序。|
|[CMFCHeaderCtrl：： GetSortColumn](#getsortcolumn)|检索标头控件中第一个已排序列的从零开始的索引。|
|`CMFCHeaderCtrl::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCHeaderCtrl：： IsAscending](#isascending)|指示标头控件中的任何列是否按升序排序。|
|[CMFCHeaderCtrl：： IsDialogControl](#isdialogcontrol)|指示当前标头控件的父窗口是否为对话框。|
|[CMFCHeaderCtrl：： IsMultipleSort](#ismultiplesort)|指示当前标头控件是否处于 *多列排序* 模式。|
|[CMFCHeaderCtrl：： RemoveSortColumn](#removesortcolumn)|从排序列列表中删除指定的列。|
|[CMFCHeaderCtrl：： SetSortColumn](#setsortcolumn)|设置标头控件中指定列的排序顺序。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCHeaderCtrl：： OnDrawItem](#ondrawitem)|由框架调用，用于绘制标头控件列。|
|[CMFCHeaderCtrl：： OnDrawSortArrow](#ondrawsortarrow)|由框架调用，用于绘制排序箭头。|
|[CMFCHeaderCtrl：： OnFillBackground](#onfillbackground)|由框架调用以填充标头控件列的背景。|

## <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCHeaderCtrl` ，以及如何为当前标头控件启用 *多种列排序* 模式。

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>备注

`CMFCHeaderCtrl`类在标题控件列上绘制排序箭头，以指示该列已排序。 如果父列表控件中一组列 ( [CMFCListCtrl 类](../../mfc/reference/cmfclistctrl-class.md)) 可以同时进行排序，则使用 *多列排序* 模式。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>要求

**标头：** afxheaderctrl

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a> CMFCHeaderCtrl：： CMFCHeaderCtrl

构造 `CMFCHeaderCtrl` 对象。

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>备注

此构造函数将以下成员变量初始化为指定的值：

|成员变量|值|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|true|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|Null|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a> CMFCHeaderCtrl：： EnableMultipleSort

启用或禁用当前标头控件的 *多个列排序* 模式。

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中若要启用多列排序模式，则为 TRUE;若要禁用多列排序模式并从已排序列的列表中删除任何列，则为 FALSE。 默认值为 TRUE。

### <a name="remarks"></a>备注

使用此方法可以启用或禁用多个列排序模式。 如果标题控件处于多列排序模式，则两列或更多列可以参与排序。

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a> CMFCHeaderCtrl：： GetColumnState

指示列是否未排序，或者是否按升序或降序排序。

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>parameters

*iColumn*<br/>
中列的从零开始的索引。

### <a name="return-value"></a>返回值

指示指定列的排序状态的值。 下表列出了可能的值：

|值|描述|
|-----------|-----------------|
|-1|按降序排序。|
|0|未排序。|
|1|按升序排序。|

### <a name="remarks"></a>备注

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a> CMFCHeaderCtrl：： GetSortColumn

检索标头控件中第一个已排序列的从零开始的索引。

```
int GetSortColumn() const;
```

### <a name="return-value"></a>返回值

已排序的列的索引; 如果未找到排序的列，则为-1。

### <a name="remarks"></a>备注

如果标头控件处于 *多列排序* 模式，并且您在调试模式下编译了应用程序，则此方法将断言并建议您改用 [CMFCHeaderCtrl：： GetColumnState](#getcolumnstate) 方法。 如果标头控件处于多列排序模式，并且您在零售模式下编译了应用程序，则此方法将返回-1。

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a> CMFCHeaderCtrl：： IsAscending

指示标头控件中的任何列是否按升序排序。

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>返回值

如果标头控件中的任何列按升序排序，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

此方法返回的值用于在标题控件项上显示相应的排序箭头。 使用 [CMFCHeaderCtrl：： SetSortColumn](#setsortcolumn) 方法设置排序顺序。

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a> CMFCHeaderCtrl：： IsDialogControl

指示当前标头控件的父窗口是否为对话框。

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>返回值

如果当前标头控件的父窗口是一个对话框，则为 TRUE;否则为 FALSE。

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a> CMFCHeaderCtrl：： IsMultipleSort

指示当前标头控件是否处于 *多列排序* 模式。

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>返回值

如果启用多个列排序模式，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

使用 [CMFCHeaderCtrl：： EnableMultipleSort](#enablemultiplesort) 方法启用或禁用多列排序模式。 如果标题控件处于多列排序模式，则两列或更多列可以参与排序。

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a> CMFCHeaderCtrl：： OnDrawItem

由框架调用，用于绘制标头控件列。

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*iItem*<br/>
中要绘制的项的从零开始的索引。

*rect*<br/>
中要绘制的项的边框。

*bIsPressed*<br/>
中若要绘制处于按下状态的项，则为 TRUE;否则为 FALSE。

*bIsHighlighted*<br/>
中若要绘制突出显示状态的项，则为 TRUE;否则为 FALSE。

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a> CMFCHeaderCtrl：： OnDrawSortArrow

由框架调用，用于绘制排序箭头。

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rectArrow*<br/>
中排序箭头的边框。

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a> CMFCHeaderCtrl：： OnFillBackground

由框架调用以填充标头控件列的背景。

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

### <a name="remarks"></a>备注

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a> CMFCHeaderCtrl：： RemoveSortColumn

从排序列列表中删除指定的列。

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>parameters

*iColumn*<br/>
中要移除的列的从零开始的索引。

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a> CMFCHeaderCtrl：： SetSortColumn

设置标头控件中指定列的排序顺序。

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>parameters

*iColumn*<br/>
中标头控件列的从零开始的索引。 如果此参数小于零，则此方法将从排序列列表中删除所有列。

*bAscending*<br/>
中指定 *iColumn* 参数指定的列的排序顺序。 若要设置升序，则为 TRUE;若要设置降序，则为 FALSE。 默认值为 TRUE。

*b*<br/>
中若要设置 *iColumn* 参数指定的列的排序顺序，则为 TRUE。

如果当前标头控件处于 *多列排序* 模式，则此方法会将指定列添加到排序列列表中。 使用 [CMFCHeaderCtrl：： EnableMultipleSort](#enablemultiplesort) 设置多列排序模式。

如果未设置多列排序模式，并且在调试模式下编译此方法，则此方法将断言。 如果未设置多列排序模式，并且此方法是在零售模式下编译的，则此方法首先从排序列列表中移除所有列，然后将指定列添加到列表中。

若要首先从排序列列表中删除所有列，然后将指定列添加到列表中，则为 FALSE。 默认值是 FALSE。

### <a name="remarks"></a>备注

使用此方法可设置列的排序顺序。 如有必要，此方法会将该列添加到排序列列表。 标头控件使用排序顺序绘制向上或向下的排序箭头。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl 类](../../mfc/reference/cmfclistctrl-class.md)

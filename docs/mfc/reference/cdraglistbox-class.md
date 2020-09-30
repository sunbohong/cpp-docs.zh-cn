---
title: CDragListBox 类
ms.date: 11/04/2016
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: b260d3a88fc8c3f2d341005c1e47cfd9ab668e1e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500364"
---
# <a name="cdraglistbox-class"></a>CDragListBox 类

除提供 Windows 列表框功能外， `CDragListBox` 类还允许用户在列表框中移动列表框项，如文件名。

## <a name="syntax"></a>语法

```
class CDragListBox : public CListBox
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDragListBox::CDragListBox](#cdraglistbox)|构造 `CDragListBox` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDragListBox：： BeginDrag](#begindrag)|在拖动操作开始时由框架调用。|
|[CDragListBox::CancelDrag](#canceldrag)|当拖动操作已取消时由框架调用。|
|[CDragListBox：:D ragging](#dragging)|在拖动操作过程中由框架调用。|
|[CDragListBox：:D rawInsert](#drawinsert)|绘制拖动列表框的插入指南。|
|[CDragListBox：:D ropped](#dropped)|在删除项后由框架调用。|
|[CDragListBox::ItemFromPt](#itemfrompt)|返回正在拖动的项的坐标。|

## <a name="remarks"></a>备注

具有此功能的列表框允许用户按照对用户最有用的任何方式对列表中的项进行排序。 默认情况下，列表框会将项移动到列表中的新位置。 但是， `CDragListBox` 可以自定义对象以复制项，而不是移动项。

与类关联的列表框控件 `CDragListBox` 不能具有 LBS_SORT 或 LBS_MULTIPLESELECT 样式。 有关列表框样式的说明，请参阅 [列表框样式](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)。

若要在应用程序的现有对话框中使用 "拖动列表" 框，请使用对话框编辑器向对话框模板添加一个列表框控件，然后将 "类别" `Control` 和 "变量类型" (的成员变量分配 `CDragListBox`) 对应于对话框模板中的列表框控件。

有关将控件分配给成员变量的详细信息，请参阅用于 [定义对话框控件的成员变量的快捷方式](../../windows/adding-editing-or-deleting-controls.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>要求

**标头：** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a> CDragListBox：： BeginDrag

当发生可能开始拖动操作的事件时（如按鼠标左键），由框架调用。

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>parameters

*pt*<br/>
一个 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象，它包含所拖动的项的坐标。

### <a name="return-value"></a>返回值

如果允许拖动，则为非零; 否则为0。

### <a name="remarks"></a>备注

如果要控制拖动操作开始时所发生的情况，请重写此函数。 默认实现将捕获鼠标并保持拖动模式，直到用户单击鼠标左键或按 ESC 键，此时拖动操作取消。

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a> CDragListBox::CancelDrag

当拖动操作已取消时由框架调用。

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>parameters

*pt*<br/>
一个 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象，它包含所拖动的项的坐标。

### <a name="remarks"></a>备注

重写此函数以处理列表框控件的任何特殊处理。

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a> CDragListBox::CDragListBox

构造 `CDragListBox` 对象。

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a> CDragListBox：:D ragging

当在对象中拖动列表框项时由框架调用 `CDragListBox` 。

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>parameters

*pt*<br/>
一个 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象，它包含光标的 x 和 y 屏幕坐标。

### <a name="return-value"></a>返回值

要显示的光标的资源 ID。 可能的值如下：

- DL_COPYCURSOR 指示将复制该项。

- DL_MOVECURSOR 指示将移动该项。

- DL_STOPCURSOR 指示当前拖放目标不可接受。

### <a name="remarks"></a>备注

默认行为返回 DL_MOVECURSOR。 如果要提供附加功能，请重写此函数。

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a> CDragListBox：:D rawInsert

由框架调用，用于在具有指定索引的项前绘制插入指南。

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>parameters

*nItem*<br/>
插入点的从零开始的索引。

### <a name="remarks"></a>备注

如果值为-1，则清除插入指南。 重写此函数以修改插入指南的外观或行为。

## <a name="cdraglistboxdropped"></a><a name="dropped"></a> CDragListBox：:D ropped

当在对象中删除项时由框架调用 `CDragListBox` 。

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>parameters

*nSrcIndex*<br/>
指定已删除字符串的从零开始的索引。

*pt*<br/>
一个 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象，它包含放置站点的坐标。

### <a name="remarks"></a>备注

默认行为是将列表框项及其数据复制到新位置，然后删除原始项。 重写此函数以自定义默认行为，如启用要拖动到列表中的其他位置的列表框项的副本。

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a> CDragListBox::ItemFromPt

调用此函数可检索位于 *pt*的列表框项的从零开始的索引。

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>parameters

*pt*<br/>
一个 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象，它包含列表框中某个点的坐标。

*bAutoScroll*<br/>
如果允许滚动，则为非零; 否则为0。

### <a name="return-value"></a>返回值

拖动列表框项的从零开始的索引。

## <a name="see-also"></a>请参阅

[MFC 示例 TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox 类](../../mfc/reference/clistbox-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CListBox 类](../../mfc/reference/clistbox-class.md)

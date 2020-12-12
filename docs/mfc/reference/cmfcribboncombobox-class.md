---
description: 了解详细信息： CMFCRibbonComboBox 类
title: CMFCRibbonComboBox 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
ms.openlocfilehash: be4078145817d06fafddb76f2cefbd0df0083503
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293660"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox 类

`CMFCRibbonComboBox`类实现可添加到功能区栏、功能区面板或功能区弹出菜单的组合框控件。

## <a name="syntax"></a>语法

```cpp
class CMFCRibbonComboBox : public CMFCRibbonEdit
```

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|名称|描述|
|----------|-----------------|
|[CMFCRibbonComboBox：： CMFCRibbonComboBox](#cmfcribboncombobox)|构造 CMFCRibbonComboBox 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonComboBox：： AddItem](#additem)|将唯一项追加到列表框。|
|[CMFCRibbonComboBox：:D eleteItem](#deleteitem)|从列表框中删除指定项。|
|[CMFCRibbonComboBox：： EnableDropDownListResize](#enabledropdownlistresize)|指定列表框在下拉时是否可以更改大小。|
|[CMFCRibbonComboBox：： FindItem](#finditem)|返回列表框中与指定字符串匹配的第一项的索引。|
|[CMFCRibbonComboBox：： GetCount](#getcount)|返回列表框中的项数。|
|[CMFCRibbonComboBox：： GetCurSel](#getcursel)|获取列表框中当前选定项的索引。|
|[CMFCRibbonComboBox：： GetDropDownHeight](#getdropdownheight)|当下拉列表框时，获取列表框的高度。|
|[CMFCRibbonComboBox：： GetIntermediateSize](#getintermediatesize)|返回在中间模式下显示的组合框的大小。|
|[CMFCRibbonComboBox：： GetItem](#getitem)|返回与列表框中指定索引处的项关联的字符串。|
|[CMFCRibbonComboBox：： GetItemData](#getitemdata)|返回与列表框中指定索引处的项关联的数据。|
|[CMFCRibbonComboBox：： HasEditBox](#haseditbox)|指示控件是否包含编辑框。|
|[CMFCRibbonComboBox：： IsResizeDropDownList](#isresizedropdownlist)|指示列表框的大小是否可以调整。|
|[CMFCRibbonComboBox：： OnSelectItem](#onselectitem)|当用户选择列表框中的项时由框架调用。|
|[CMFCRibbonComboBox：： RemoveAllItems](#removeallitems)|删除列表框中的所有项并清除编辑框。|
|[CMFCRibbonComboBox：： SelectItem](#selectitem)|选择列表框中的项。|
|[CMFCRibbonComboBox：： SetDropDownHeight](#setdropdownheight)|在下拉列表框时设置列表框的高度。|

## <a name="remarks"></a>备注

功能区组合框包含一个列表框，其中包含与用户可编辑的静态标签或标签组合在一起的列表框。 创建功能区组合框时，必须指定所需的类型。

## <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCRibbonComboBox` ，将项添加到组合框，在组合框中选择一项，然后将组合框添加到面板。

[!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)

[CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)

## <a name="requirements"></a>要求

**标头：** afxribboncombobox

## <a name="cmfcribboncomboboxadditem"></a><a name="additem"></a> CMFCRibbonComboBox：： AddItem

将唯一项追加到列表框。

```cpp
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,
    DWORD_PTR dwData=0);
```

### <a name="parameters"></a>parameters

*lpszItem*<br/>
中要添加的项的字符串。

*dwData*<br/>
中与要添加的项关联的数据。

### <a name="return-value"></a>返回值

追加项的从零开始的索引。

## <a name="cmfcribboncomboboxcmfcribboncombobox"></a><a name="cmfcribboncombobox"></a> CMFCRibbonComboBox：： CMFCRibbonComboBox

构造 `CMFCRibbonComboBox` 对象。

```cpp
public:
CMFCRibbonComboBox(
    UINT nID,
    BOOL bHasEditBox=TRUE,
    Int nWidth=-1,
    LPCTSTR lpszLabel=NULL,
    Int nImage=-1);

protected:
CMFCRibbonComboBox();
```

### <a name="parameters"></a>parameters

*nID*<br/>
中组合框的 ID。

*bHasEditBox*<br/>
中如果要在控件中使用编辑框，则为 TRUE;否则为 FALSE。

*nWidth*<br/>
中组合框的宽度（以像素为单位）;对于默认宽度，为-1。

*lpszLabel*<br/>
中组合框的显示标签。

*n*<br/>
中组合框的小图像索引。

### <a name="remarks"></a>备注

默认宽度为108像素。

## <a name="cmfcribboncomboboxdeleteitem"></a><a name="deleteitem"></a> CMFCRibbonComboBox：:D eleteItem

从列表框中删除指定项。

```cpp
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中要删除的项的从零开始的索引。

*dwData*<br/>
中与要删除的项关联的数据。

*lpszText*<br/>
中要删除的项的字符串。 如果存在多个具有相同字符串的项，则删除第一项。

### <a name="return-value"></a>返回值

如果指定的项已被删除，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxenabledropdownlistresize"></a><a name="enabledropdownlistresize"></a> CMFCRibbonComboBox：： EnableDropDownListResize

指定列表框在下拉时是否可以更改大小。

```cpp
void EnableDropDownListResize(BOOL bEnable=FALSE);
```

### <a name="parameters"></a>parameters

*bEnable*<br/>
中若要启用大小调整，则为 TRUE;若要禁用调整大小，则为 FALSE。

### <a name="remarks"></a>备注

当调整大小时，列表框的大小将更改为适合它所显示的项。

## <a name="cmfcribboncomboboxfinditem"></a><a name="finditem"></a> CMFCRibbonComboBox：： FindItem

返回列表框中与指定字符串匹配的第一项的索引。

```cpp
int FindItem(LPCTSTR lpszText) const;
```

### <a name="parameters"></a>parameters

*lpszText*<br/>
中列表框中的项的字符串。

### <a name="return-value"></a>返回值

项的从零开始的索引;如果未找到该项，则为-1。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxgetcount"></a><a name="getcount"></a> CMFCRibbonComboBox：： GetCount

返回列表框中的项数。

```cpp
INT_PTR GetCount() const;
```

### <a name="return-value"></a>返回值

列表框中的项数，如果列表框不包含任何项，则为0。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxgetcursel"></a><a name="getcursel"></a> CMFCRibbonComboBox：： GetCurSel

获取列表框中当前选定项的索引。

```cpp
int GetCurSel() const;
```

### <a name="return-value"></a>返回值

列表框中当前选定项的从零开始的索引;如果未选择任何项，则为-1。

## <a name="cmfcribboncomboboxgetdropdownheight"></a><a name="getdropdownheight"></a> CMFCRibbonComboBox：： GetDropDownHeight

当下拉列表框时，获取列表框的高度。

```cpp
int GetDropDownHeight();
```

### <a name="return-value"></a>返回值

列表框的高度（以像素为单位）。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonComboBox：： GetIntermediateSize

返回在中间模式下显示的组合框的大小。

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向组合框的设备上下文的指针。

### <a name="return-value"></a>返回值

组合框的大小。

### <a name="remarks"></a>备注

返回的大小取决于组合框显示小图像时的大小。

## <a name="cmfcribboncomboboxgetitem"></a><a name="getitem"></a> CMFCRibbonComboBox：： GetItem

返回与列表框中指定索引处的项关联的字符串。

```cpp
LPCTSTR GetItem(int iIndex) const;
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中列表框中某项的从零开始的索引。

### <a name="return-value"></a>返回值

指向与项关联的字符串的指针;否则，如果索引参数无效，或者索引参数为-1，并且在组合框中未选择任何项，则为 NULL。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxgetitemdata"></a><a name="getitemdata"></a> CMFCRibbonComboBox：： GetItemData

返回与列表框中指定索引处的项关联的数据。

```cpp
DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中列表框中某项的从零开始的索引。

### <a name="return-value"></a>返回值

与该项关联的数据;如果项不存在，则为; 如果索引参数为-1 且列表框中没有选定项，则为0。

## <a name="cmfcribboncomboboxhaseditbox"></a><a name="haseditbox"></a> CMFCRibbonComboBox：： HasEditBox

指示控件是否包含编辑框。

```cpp
BOOL HasEditBox() const;
```

### <a name="return-value"></a>返回值

如果控件包含编辑框，则为 TRUE; 否则为。否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxisresizedropdownlist"></a><a name="isresizedropdownlist"></a> CMFCRibbonComboBox：： IsResizeDropDownList

指示列表框的大小是否可以调整。

```cpp
BOOL IsResizeDropDownList() const;
```

### <a name="return-value"></a>返回值

如果可以调整列表框的大小，则为 TRUE;否则为 FALSE。 [CMFCRibbonComboBox：： EnableDropDownListResize](#enabledropdownlistresize)

### <a name="remarks"></a>备注

可以通过使用 [CMFCRibbonComboBox：： EnableDropDownListResize](#enabledropdownlistresize) 方法启用列表框的大小调整。

## <a name="cmfcribboncomboboxonselectitem"></a><a name="onselectitem"></a> CMFCRibbonComboBox：： OnSelectItem

当用户选择列表框中的项时由框架调用。

```cpp
virtual void OnSelectItem(int nItem);
```

### <a name="parameters"></a>parameters

*nItem*<br/>
中选定项的索引。

### <a name="remarks"></a>备注

如果要处理用户输入选择，请重写此方法。

## <a name="cmfcribboncomboboxremoveallitems"></a><a name="removeallitems"></a> CMFCRibbonComboBox：： RemoveAllItems

删除列表框中的所有项并清除编辑框。

```cpp
void RemoveAllItems();
```

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxselectitem"></a><a name="selectitem"></a> CMFCRibbonComboBox：： SelectItem

选择列表框中的项。

```cpp
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中列表框中某项的从零开始的索引。

*dwData*<br/>
中与列表框中的项关联的数据。

*lpszText*<br/>
中列表框中的项的字符串。

### <a name="return-value"></a>返回值

如果方法成功，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cmfcribboncomboboxsetdropdownheight"></a><a name="setdropdownheight"></a> CMFCRibbonComboBox：： SetDropDownHeight

在下拉列表框时设置列表框的高度。

```cpp
void SetDropDownHeight(int nHeight);
```

### <a name="parameters"></a>parameters

*nHeight*<br/>
中列表框的高度（以像素为单位）。

### <a name="remarks"></a>备注

默认高度为150像素。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonEdit 类](../../mfc/reference/cmfcribbonedit-class.md)

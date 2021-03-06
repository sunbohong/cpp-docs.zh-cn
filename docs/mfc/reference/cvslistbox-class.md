---
description: 了解详细信息： CVSListBox 类
title: CVSListBox 类
ms.date: 11/19/2018
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
ms.openlocfilehash: 6912eccd4cc8e7c78407d0cda0a0dc1305d0bde8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344973"
---
# <a name="cvslistbox-class"></a>CVSListBox 类

`CVSListBox`类支持可编辑列表控件。

## <a name="syntax"></a>语法

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CVSListBox：： CVSListBox](#cvslistbox)|构造 `CVSListBox` 对象。|
|`CVSListBox::~CVSListBox`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CVSListBox：： AddItem](#additem)|将字符串添加到列表控件。 （重写 `CVSListBoxBase::AddItem`。）|
|[CVSListBox：： EditItem](#edititem)|对列表控件项的文本启动编辑操作。 （重写 `CVSListBoxBase::EditItem`。）|
|[CVSListBox：： GetCount](#getcount)|检索可编辑列表控件中的字符串的数目。 （重写 `CVSListBoxBase::GetCount`。）|
|[CVSListBox：： GetItemData](#getitemdata)|检索与可编辑列表控件项关联的特定于应用程序的32位值。 （重写 `CVSListBoxBase::GetItemData`。）|
|[CVSListBox：： GetItemText](#getitemtext)|检索可编辑列表控件项的文本。 （重写 `CVSListBoxBase::GetItemText`。）|
|[CVSListBox：： GetSelItem](#getselitem)|检索可编辑列表控件中当前选定项的从零开始的索引。 （重写 `CVSListBoxBase::GetSelItem`。）|
|`CVSListBox::PreTranslateMessage`|转换窗口消息，然后将其调度到 [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage) 和 [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 函数。 有关详细信息和方法语法，请参阅 [CWnd：:P retranslatemessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)。 （重写 `CVSListBoxBase::PreTranslateMessage`。）|
|[CVSListBox：： RemoveItem](#removeitem)|删除可编辑列表控件中的项。 （重写 `CVSListBoxBase::RemoveItem`。）|
|[CVSListBox：： SelectItem](#selectitem)|选择可编辑的列表控件字符串。 （重写 `CVSListBoxBase::SelectItem`。）|
|[CVSListBox：： SetItemData](#setitemdata)|将特定于应用程序的32位值与可编辑的列表控件项关联。 （重写 `CVSListBoxBase::SetItemData`。）|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CVSListBox：： GetListHwnd](#getlisthwnd)|返回当前嵌入的列表视图控件的句柄。|

## <a name="remarks"></a>备注

`CVSListBox`类提供一组编辑按钮，用户可以使用这些按钮来创建、修改、删除或重新排列列表控件中的项。

下面是可编辑列表控件的图片。 选择名为 "Item2" 的第二个列表项进行编辑。

![CVSListBox 控件](../../mfc/reference/media/cvslistbox.png "CVSListBox 控件")

如果使用资源编辑器来添加可编辑列表控件，请注意，编辑器的 " **工具箱** " 窗格不提供预定义的可编辑列表控件。 相反，请添加静态控件，如 " **分组框** " 控件。 框架使用静态控件作为占位符来指定可编辑列表控件的大小和位置。

若要在对话框模板中使用可编辑的列表控件，请 `CVSListBox` 在对话框类中声明变量。 若要支持变量与控件之间的数据交换，请 `DDX_Control` 在对话框的方法中定义一个宏项 `DoDataExchange` 。 默认情况下，不使用 "编辑" 按钮创建可编辑列表控件。 使用继承的 CVSListBoxBase：： SetStandardButtons 方法启用 "编辑" 按钮。

有关详细信息，请参阅示例目录 `New Controls` 示例、Page3 和 Page3 文件。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>要求

**标头：** afxvslistbox

## <a name="cvslistboxadditem"></a><a name="additem"></a> CVSListBox：： AddItem

将字符串添加到列表控件。

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>parameters

*strIext*<br/>
中对字符串的引用。

*dwData*<br/>
中与字符串关联的应用程序特定的32位值。 默认值为 0。

*iIndex*<br/>
中将保留字符串的位置的从零开始的索引。 如果 *iIndex* 参数为-1，则字符串将被添加到列表的末尾。 默认值为 -1。

### <a name="return-value"></a>返回值

列表控件中字符串位置的从零开始的索引。

### <a name="remarks"></a>备注

使用 [CVSListBox：： GetItemData](#getitemdata) 方法检索 *dwData* 参数指定的值。 此值可以是应用程序特定的整数，也可以是指向其他数据的指针。

## <a name="cvslistboxcvslistbox"></a><a name="cvslistbox"></a> CVSListBox：： CVSListBox

构造 `CVSListBox` 对象。

```
CVSListBox();
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cvslistboxedititem"></a><a name="edititem"></a> CVSListBox：： EditItem

对列表控件项的文本启动编辑操作。

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中列表控件项的从零开始的索引。

### <a name="return-value"></a>返回值

如果编辑操作成功启动，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

用户可以通过双击项的标签或按 **F2** 键或 **空格键** （当项具有焦点时）来启动编辑操作。

## <a name="cvslistboxgetcount"></a><a name="getcount"></a> CVSListBox：： GetCount

检索可编辑列表控件中的字符串的数目。

```
virtual int GetCount() const;
```

### <a name="return-value"></a>返回值

列表控件中的项数。

### <a name="remarks"></a>备注

请注意，此计数比最后一项的索引值大1，因为该索引是从零开始的。

## <a name="cvslistboxgetitemdata"></a><a name="getitemdata"></a> CVSListBox：： GetItemData

检索与可编辑列表控件项关联的特定于应用程序的32位值。

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中可编辑列表控件项的从零开始的索引。

### <a name="return-value"></a>返回值

与指定项关联的32位值。

### <a name="remarks"></a>备注

使用 [CVSListBox：： SetItemData](#setitemdata) 或 [CVSListBox：： AddItem](#additem) 方法将32位值与列表控件项关联。 此值可以是应用程序特定的整数，也可以是指向其他数据的指针。

## <a name="cvslistboxgetitemtext"></a><a name="getitemtext"></a> CVSListBox：： GetItemText

检索可编辑列表控件项的文本。

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中可编辑列表控件项的从零开始的索引。

### <a name="return-value"></a>返回值

一个 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 对象，其中包含指定项的文本。

### <a name="remarks"></a>备注

## <a name="cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a> CVSListBox：： GetListHwnd

返回当前嵌入的列表视图控件的句柄。

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>返回值

嵌入的列表视图控件的句柄。

### <a name="remarks"></a>备注

使用此方法可检索支持类的嵌入列表视图控件的句柄 `CVSListBox` 。

## <a name="cvslistboxgetselitem"></a><a name="getselitem"></a> CVSListBox：： GetSelItem

检索可编辑列表控件中当前选定项的从零开始的索引。

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>返回值

如果此方法成功，则为当前选定项的从零开始的索引;否则为-1。

### <a name="remarks"></a>备注

## <a name="cvslistboxremoveitem"></a><a name="removeitem"></a> CVSListBox：： RemoveItem

删除可编辑列表控件中的项。

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中可编辑列表控件项的从零开始的索引。

### <a name="return-value"></a>返回值

如果删除了指定的项，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cvslistboxselectitem"></a><a name="selectitem"></a> CVSListBox：： SelectItem

选择可编辑的列表控件字符串。

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>parameters

*iItem*<br/>
中可编辑列表控件项的从零开始的索引。

### <a name="return-value"></a>返回值

如果此方法成功，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

此方法选择指定的项，如果需要，则将该项滚动到视图中。

## <a name="cvslistboxsetitemdata"></a><a name="setitemdata"></a> CVSListBox：： SetItemData

将特定于应用程序的32位值与可编辑的列表控件项关联。

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>parameters

*iIndex*<br/>
中可编辑列表控件项的从零开始的索引。

*dwData*<br/>
中32位值。 此值可以是应用程序特定的整数，也可以是指向其他数据的指针。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)

---
description: 了解详细信息： CMFCKeyMapDialog 类
title: CMFCKeyMapDialog 类
ms.date: 11/04/2016
f1_keywords:
- CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::CMFCKeyMapDialog
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::DoModal
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::FormatItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::GetCommandKeys
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnInsertItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintHeader
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnPrintItem
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::OnSetColumns
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::PrintKeyMap
- AFXKEYMAPDIALOG/CMFCKeyMapDialog::SetColumnsWidth
helpviewer_keywords:
- CMFCKeyMapDialog [MFC], CMFCKeyMapDialog
- CMFCKeyMapDialog [MFC], DoModal
- CMFCKeyMapDialog [MFC], FormatItem
- CMFCKeyMapDialog [MFC], GetCommandKeys
- CMFCKeyMapDialog [MFC], OnInsertItem
- CMFCKeyMapDialog [MFC], OnPrintHeader
- CMFCKeyMapDialog [MFC], OnPrintItem
- CMFCKeyMapDialog [MFC], OnSetColumns
- CMFCKeyMapDialog [MFC], PrintKeyMap
- CMFCKeyMapDialog [MFC], SetColumnsWidth
ms.assetid: 5feb4942-d636-462d-a162-0104dd320f4e
ms.openlocfilehash: e339edb54b9c381dd2b27c9ee3ec7566308ae434
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265228"
---
# <a name="cmfckeymapdialog-class"></a>CMFCKeyMapDialog 类

`CMFCKeyMapDialog`类支持将命令映射到键盘上的键的控件。

## <a name="syntax"></a>语法

```
class CMFCKeyMapDialog : public CDialogEx
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCKeyMapDialog::CMFCKeyMapDialog](#cmfckeymapdialog)|构造 `CMFCKeyMapDialog` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCKeyMapDialog：:D oModal](#domodal)|显示 "键盘映射" 对话框。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCKeyMapDialog::FormatItem](#formatitem)|由框架调用，用于生成描述键映射的字符串。 默认情况下，该字符串包含命令名称、所使用的快捷键和快捷键说明。|
|[CMFCKeyMapDialog::GetCommandKeys](#getcommandkeys)|检索一个字符串，该字符串包含与指定命令关联的快捷键的列表。|
|[CMFCKeyMapDialog::OnInsertItem](#oninsertitem)|在向支持键盘映射控件的内部列表控件中插入新项之前，由框架调用。|
|[CMFCKeyMapDialog::OnPrintHeader](#onprintheader)|由框架调用，用于在新页上打印键盘地图的标题。|
|[CMFCKeyMapDialog::OnPrintItem](#onprintitem)|由框架调用以打印键盘映射项。|
|[CMFCKeyMapDialog::OnSetColumns](#onsetcolumns)|由框架调用，用于为支持键盘映射控件的内部列表控件中的列设置标题。|
|[CMFCKeyMapDialog：:P rintKeyMap](#printkeymap)|当用户单击 " **打印** " 按钮时由框架调用。|
|[CMFCKeyMapDialog::SetColumnsWidth](#setcolumnswidth)|由框架调用，用于设置支持键盘映射控件的内部列表控件中的列的宽度。|

## <a name="remarks"></a>备注

使用 `CMFCKeyMapDialog` 类实现可调整大小的键盘映射对话框。 对话框使用列表视图控件来显示键盘快捷方式及其关联命令。

若要 `CMFCKeyMapDialog` 在应用程序中使用类，请将指向主框架窗口的指针作为参数传递到 `CMFCKeyMapDialog` 构造函数。 然后调用 `DoModal` 方法以启动模式对话框。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CDialogEx](../../mfc/reference/cdialogex-class.md)

[CMFCKeyMapDialog](../../mfc/reference/cmfckeymapdialog-class.md)

## <a name="requirements"></a>要求

**标头：** afxkeymapdialog

## <a name="cmfckeymapdialogcmfckeymapdialog"></a><a name="cmfckeymapdialog"></a> CMFCKeyMapDialog::CMFCKeyMapDialog

构造 `CMFCKeyMapDialog` 对象。

```
CMFCKeyMapDialog(
    CFrameWnd* pWndParentFrame,
    BOOL bEnablePrint=FALSE);
```

### <a name="parameters"></a>parameters

*pWndParentFrame*<br/>
中指向对象的父窗口的指针 `CMFCKeyMapDialog` 。

*bEnablePrint*<br/>
中如果可以打印快捷键的列表，则为 TRUE;否则为 FALSE。 默认值为 FALSE。

### <a name="remarks"></a>备注

### <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCKeyMapDialog` 。 此示例是 [Visual Studio 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_VisualStudioDemo#21](../../mfc/codesnippet/cpp/cmfckeymapdialog-class_1.cpp)]

## <a name="cmfckeymapdialogdomodal"></a><a name="domodal"></a> CMFCKeyMapDialog：:D oModal

显示 "键盘映射" 对话框。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>返回值

传递给 [CDialog：： EndDialog](../../mfc/reference/cdialog-class.md#enddialog) 方法的有符号整数，如 IDOK 或 IDCANCEL。 方法反过来会关闭对话框。 有关详细信息，请参阅 [CDialog：:D omodal](../../mfc/reference/cdialog-class.md#domodal)。

### <a name="remarks"></a>备注

"键盘映射" 对话框可用于选择快捷键并将其分配给各种类别的命令。 此外，您可以将所选快捷键及其说明复制到剪贴板。

## <a name="cmfckeymapdialogformatitem"></a><a name="formatitem"></a> CMFCKeyMapDialog::FormatItem

由框架调用，用于生成描述键映射的字符串。 默认情况下，该字符串包含命令名称、所使用的快捷键和快捷键说明。

```
virtual CString FormatItem(int nItem) const;
```

### <a name="parameters"></a>parameters

*nItem*<br/>
中键映射内部列表中项的从零开始的索引。

### <a name="return-value"></a>返回值

一个 `CString` 包含格式化项文本的对象。

### <a name="remarks"></a>备注

## <a name="cmfckeymapdialoggetcommandkeys"></a><a name="getcommandkeys"></a> CMFCKeyMapDialog::GetCommandKeys

检索字符串值。 字符串包含与指定命令关联的快捷键的列表。

```
virtual CString GetCommandKeys(UINT uiCmdID) const;
```

### <a name="parameters"></a>parameters

*uiCmdID*<br/>
中命令 ID。

### <a name="return-value"></a>返回值

用分号分隔的 ( ";") 与指定命令关联的快捷键的列表。

### <a name="remarks"></a>备注

## <a name="cmfckeymapdialogoninsertitem"></a><a name="oninsertitem"></a> CMFCKeyMapDialog::OnInsertItem

在将新项插入到支持键盘映射控件的内部列表控件之前，由框架调用。

```
virtual void OnInsertItem(
    CMFCToolBarButton* pButton,
    int nItem);
```

### <a name="parameters"></a>parameters

*pButton*<br/>
中一个指针，指向用于将键盘键组合映射到命令名称和说明的工具栏按钮。 键映射项存储在内部列表控件中。

*nItem*<br/>
中从零开始的索引，它指定在内部列表控件中插入新键映射项的位置。

### <a name="remarks"></a>备注

## <a name="cmfckeymapdialogonprintheader"></a><a name="onprintheader"></a> CMFCKeyMapDialog::OnPrintHeader

由框架调用，用于在新页上打印键盘地图的标题。

```
virtual int OnPrintHeader(
    CDC& dc,
    int nPage,
    int cx) const;
```

### <a name="parameters"></a>parameters

*dc*<br/>
中打印机的设备上下文。

*nPage*<br/>
中要打印的页码。

*cx*<br/>
中标头的水平偏移量（以像素为单位）。

### <a name="return-value"></a>返回值

如果成功，则为打印文本的高度。 有关详细信息，请参阅 [CDC：:D rawtext](../../mfc/reference/cdc-class.md#drawtext)的返回值部分。

### <a name="remarks"></a>备注

框架使用此方法来打印键盘映射。 默认情况下，此方法将打印页码、应用程序名称和对话框标题。

## <a name="cmfckeymapdialogonprintitem"></a><a name="onprintitem"></a> CMFCKeyMapDialog::OnPrintItem

由框架调用以打印键盘映射项。

```
virtual int OnPrintItem(
    CDC& dc,
    int nItem,
    int y,
    int cx,
    BOOL bCalcHeight) const;
```

### <a name="parameters"></a>parameters

*dc*<br/>
中打印机的设备上下文。

*nItem*<br/>
中要打印的项的从零开始的索引。

*y*<br/>
中页面顶部与项的位置之间的垂直偏移量。

*cx*<br/>
中页面左侧与项的位置之间的水平偏移量。

*bCalcHeight*<br/>
中若要计算打印项的最佳高度，为 TRUE;若为 FALSE，则截断打印项，使其适应默认空间。

### <a name="return-value"></a>返回值

打印项的高度。

### <a name="remarks"></a>备注

框架调用此方法来打印 "键映射" 对话框项。 默认情况下，此方法将打印项的命令名称、快捷键和命令说明。

## <a name="cmfckeymapdialogonsetcolumns"></a><a name="onsetcolumns"></a> CMFCKeyMapDialog::OnSetColumns

由框架调用，用于为支持键盘映射控件的内部列表控件中的列设置标题。

```
virtual void OnSetColumns();
```

### <a name="remarks"></a>备注

默认情况下，此方法从三个资源中获取列的标题。 命令列标题来自 IDS_AFXBARRES_COMMAND，键列标题来自 IDS_AFXBARRES_KEYS，说明列标题来自 IDS_AFXBARRES_DESCRIPTION。

## <a name="cmfckeymapdialogprintkeymap"></a><a name="printkeymap"></a> CMFCKeyMapDialog：:P rintKeyMap

当用户单击 " **打印** " 按钮时由框架调用。

```
virtual void PrintKeyMap();
```

### <a name="remarks"></a>备注

`PrintKeyMap`方法打印键映射。 它启动一个新的打印作业，然后重复调用 [CMFCKeyMapDialog：： OnPrintHeader](#onprintheader) 和 [CMFCKeyMapDialog：： OnPrintItem](#onprintitem) 方法，直到打印所有键映射。

## <a name="cmfckeymapdialogsetcolumnswidth"></a><a name="setcolumnswidth"></a> CMFCKeyMapDialog::SetColumnsWidth

由框架调用，用于设置支持键盘映射控件的内部列表控件中的列的宽度。

```
virtual void SetColumnsWidth();
```

### <a name="remarks"></a>备注

此方法将内部列表控件的列设置为默认宽度。 首先，计算快捷键列的宽度。 然后，将剩余宽度的三分之一分配给 command 列，其余的三分之二则分配给 description 列。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager 类](../../mfc/reference/ckeyboardmanager-class.md)

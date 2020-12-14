---
description: 了解详细信息： CPrintInfo 结构
title: CPrintInfo 结构
ms.date: 11/04/2016
f1_keywords:
- CPrintInfo
helpviewer_keywords:
- CPrintInfo structure [MFC]
ms.assetid: 0b3de849-d050-4386-9a14-f4c1a25684f7
ms.openlocfilehash: 355bcf2f04b32756ae16147465054e945d70cf78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343383"
---
# <a name="cprintinfo-structure"></a>CPrintInfo 结构

存储有关打印或打印预览作业的信息。

## <a name="syntax"></a>语法

```
struct CPrintInfo
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CPrintInfo：： GetFromPage](#getfrompage)|返回要打印的第一页的页码。|
|[CPrintInfo：： GetMaxPage](#getmaxpage)|返回文档的最后一页的页码。|
|[CPrintInfo：： GetMinPage](#getminpage)|返回文档的第一页的页码。|
|[CPrintInfo：： GetOffsetPage](#getoffsetpage)|返回在 DocObject 打印作业中打印的 DocObject 项的第一页之前的页数。|
|[CPrintInfo：： GetToPage](#gettopage)|返回要打印的最后一页的页码。|
|[CPrintInfo：： SetMaxPage](#setmaxpage)|设置文档的最后一页的页码。|
|[CPrintInfo：： SetMinPage](#setminpage)|设置文档的第一页的页码。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CPrintInfo：： m_bContinuePrinting](#m_bcontinueprinting)|包含一个标志，该标志指示框架是否应继续执行打印循环。|
|[CPrintInfo：： m_bDirect](#m_bdirect)|包含一个标志，该标志指示是否在不显示 "打印" 对话框) 的情况下直接打印文档 (。|
|[CPrintInfo：： m_bDocObject](#m_bdocobject)|包含一个标志，该标志指示要打印的文档是否为 DocObject。|
|[CPrintInfo：： m_bPreview](#m_bpreview)|包含一个标志，该标志指示是否正在预览文档。|
|[CPrintInfo：： m_dwFlags](#m_dwflags)|指定 DocObject 打印操作。|
|[CPrintInfo：： m_lpUserData](#m_lpuserdata)|包含指向用户创建的结构的指针。|
|[CPrintInfo：： m_nCurPage](#m_ncurpage)|标识当前正在打印的页的编号。|
|[CPrintInfo：： m_nJobNumber](#m_njobnumber)|指定操作系统为当前打印作业分配的作业编号|
|[CPrintInfo：： m_nNumPreviewPages](#m_nnumpreviewpages)|标识预览窗口中显示的页数;1或2。|
|[CPrintInfo：： m_nOffsetPage](#m_noffsetpage)|指定合并 DocObject 打印作业中特定 DocObject 的第一页的偏移量。|
|[CPrintInfo：： m_pPD](#m_ppd)|包含指向 `CPrintDialog` 用于 "打印" 对话框的对象的指针。|
|[CPrintInfo：： m_rectDraw](#m_rectdraw)|指定定义当前可用页面区域的矩形。|
|[CPrintInfo：： m_strPageDesc](#m_strpagedesc)|包含页码显示的格式字符串。|

## <a name="remarks"></a>备注

`CPrintInfo` 为结构，并且不具有基类。

`CPrintInfo`每次选择 "打印" 或 "打印预览" 命令时，框架都将创建一个对象，并在命令完成时销毁该命令。

`CPrintInfo` 同时包含有关打印作业的信息，如要打印的页面范围以及打印作业的当前状态，例如当前正在打印的页面。 某些信息存储在关联的 [CPrintDialog](../../mfc/reference/cprintdialog-class.md) 对象中;此对象包含用户在 "打印" 对话框中输入的值。

在 `CPrintInfo` 打印过程中，对象在框架和视图类之间传递，并用于在两者之间交换信息。 例如，框架通过为的成员赋值，通知视图类要打印的文档页 `m_nCurPage` `CPrintInfo` ; 视图类检索值并执行指定页的实际打印。

另一个示例是文档长度在打印之前是未知的。 在这种情况下，每次打印页面时，view 类都会测试文档的结尾。 当到达末尾时，视图类将的成员设置 `m_bContinuePrinting` `CPrintInfo` 为 FALSE; 这将通知框架停止打印循环。

`CPrintInfo``CView`在 "另请参阅" 下列出的成员函数使用。 有关 Microsoft 基础类库提供的打印体系结构的详细信息，请参阅 [框架窗口](../../mfc/frame-windows.md) 和 [文档/视图体系结构](../../mfc/document-view-architecture.md) 和文章 [打印](../../mfc/printing.md) 和 [打印：多页文档](../../mfc/multipage-documents.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CPrintInfo`

## <a name="requirements"></a>要求

**标头：** afxext。h

## <a name="cprintinfogetfrompage"></a><a name="getfrompage"></a> CPrintInfo：： GetFromPage

调用此函数可检索要打印的第一页的页码。

```
UINT GetFromPage() const;
```

### <a name="return-value"></a>返回值

要打印的第一页的页码。

### <a name="remarks"></a>备注

这是用户在 "打印" 对话框中指定的值，它存储在 `CPrintDialog` 成员引用的对象中 `m_pPD` 。 如果用户没有指定值，则默认值为文档的第一页。

## <a name="cprintinfogetmaxpage"></a><a name="getmaxpage"></a> CPrintInfo：： GetMaxPage

调用此函数可检索文档的最后一页的页码。

```
UINT GetMaxPage() const;
```

### <a name="return-value"></a>返回值

文档的最后一页的页码。

### <a name="remarks"></a>备注

此值存储在 `CPrintDialog` 成员引用的对象中 `m_pPD` 。

## <a name="cprintinfogetminpage"></a><a name="getminpage"></a> CPrintInfo：： GetMinPage

调用此函数可检索文档的第一页的页码。

```
UINT GetMinPage() const;
```

### <a name="return-value"></a>返回值

文档的第一页的页码。

### <a name="remarks"></a>备注

此值存储在 `CPrintDialog` 成员引用的对象中 `m_pPD` 。

## <a name="cprintinfogetoffsetpage"></a><a name="getoffsetpage"></a> CPrintInfo：： GetOffsetPage

调用此函数可检索从 DocObject 客户端打印多个 DocObject 项时的偏移量。

```
UINT GetOffsetPage() const;
```

### <a name="return-value"></a>返回值

在 DocObject 打印作业中打印的 DocObject 项的第一页之前的页数。

### <a name="remarks"></a>备注

此值由 `m_nOffsetPage` 成员引用。 打印为包含其他活动文档的 DocObject 时，文档的第一页的编号为 `m_nOffsetPage` + 1。 `m_nOffsetPage`仅当值为 TRUE 时，成员才有效 `m_bDocObject` 。

## <a name="cprintinfogettopage"></a><a name="gettopage"></a> CPrintInfo：： GetToPage

调用此函数可检索要打印的最后一页的页码。

```
UINT GetToPage() const;
```

### <a name="return-value"></a>返回值

要打印的最后一页的页码。

### <a name="remarks"></a>备注

这是用户在 "打印" 对话框中指定的值，它存储在 `CPrintDialog` 成员引用的对象中 `m_pPD` 。 如果用户没有指定值，则默认值为文档的最后一页。

## <a name="cprintinfom_bcontinueprinting"></a><a name="m_bcontinueprinting"></a> CPrintInfo：： m_bContinuePrinting

包含一个标志，该标志指示框架是否应继续执行打印循环。

### <a name="remarks"></a>备注

如果要执行打印时分页，则可以在文档结束后将此成员设置为 "FALSE" `CView::OnPrepareDC` 。 如果已使用成员函数指定打印作业开始时文档的长度，则无需修改此变量 `SetMaxPage` 。 该 `m_bContinuePrinting` 成员是类型为 BOOL 的公共变量。

## <a name="cprintinfom_bdirect"></a><a name="m_bdirect"></a> CPrintInfo：： m_bDirect

如果 "打印" 对话框将绕过直接打印，框架将此成员设置为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

当您从 shell 打印时或使用命令 ID ID_FILE_PRINT_DIRECT 打印完成打印时，通常会跳过 "打印" 对话框。

通常不会更改此成员，但如果确实要更改此成员，请在重写[cview：： OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)中的[oprepareprinting:D](../../mfc/reference/cview-class.md#doprepareprinting)之前更改此成员。

## <a name="cprintinfom_bdocobject"></a><a name="m_bdocobject"></a> CPrintInfo：： m_bDocObject

包含一个标志，该标志指示要打印的文档是否为 DocObject。

### <a name="remarks"></a>备注

数据成员 `m_dwFlags` 和 `m_nOffsetPage` 无效，除非此标志为 TRUE。

## <a name="cprintinfom_bpreview"></a><a name="m_bpreview"></a> CPrintInfo：： m_bPreview

包含一个标志，该标志指示是否正在预览文档。

### <a name="remarks"></a>备注

这由框架根据用户执行的命令进行设置。 对于打印预览作业，不显示 "打印" 对话框。 该 `m_bPreview` 成员是类型为 BOOL 的公共变量。

## <a name="cprintinfom_dwflags"></a><a name="m_dwflags"></a> CPrintInfo：： m_dwFlags

包含指定 DocObject 打印操作的标志的组合。

### <a name="remarks"></a>备注

仅当数据成员为 TRUE 时才有效 `m_bDocObject` 。

标志可以是以下一个或多个值：

- PRINTFLAG_MAYBOTHERUSER

- PRINTFLAG_PROMPTUSER

- PRINTFLAG_USERMAYCHANGEPRINTER

- PRINTFLAG_RECOMPOSETODEVICE

- PRINTFLAG_DONTACTUALLYPRINT

- PRINTFLAG_FORCEPROPERTIES

- PRINTFLAG_PRINTTOFILE

## <a name="cprintinfom_lpuserdata"></a><a name="m_lpuserdata"></a> CPrintInfo：： m_lpUserData

包含指向用户创建的结构的指针。

### <a name="remarks"></a>备注

您可以使用它来存储您不希望存储在视图类中的特定于打印的数据。 该 `m_lpUserData` 成员是 LPVOID 类型的公共变量。

## <a name="cprintinfom_ncurpage"></a><a name="m_ncurpage"></a> CPrintInfo：： m_nCurPage

包含当前页的编号。

### <a name="remarks"></a>备注

框架 `CView::OnPrepareDC` `CView::OnPrint` 为文档的每一页都调用一次，每次为此成员指定一个不同的值; 其值范围是从返回的值 `GetFromPage` 到由返回的值 `GetToPage` 。 使用和重写中的此 `CView::OnPrepareDC` 成员 `CView::OnPrint` 打印文档的指定页。

当首次调用预览模式时，框架会读取此成员的值，以确定应最初预览文档的哪一页。 您可以在的重写中设置此成员的值 `CView::OnPreparePrinting` ，以便在进入预览模式时保持用户在文档中的当前位置。 `m_nCurPage`成员是 UINT 类型的公共变量。

## <a name="cprintinfom_njobnumber"></a><a name="m_njobnumber"></a> CPrintInfo：： m_nJobNumber

指示操作系统为当前打印作业分配的作业编号。

### <a name="remarks"></a>备注

如果作业尚未打印，此值可能会 SP_ERROR (也就是说，如果 `CPrintInfo` 对象是新构建的，并且尚未用于打印) ，或在启动作业时出错。

## <a name="cprintinfom_nnumpreviewpages"></a><a name="m_nnumpreviewpages"></a> CPrintInfo：： m_nNumPreviewPages

包含预览模式下显示的页数;它可以是1或2。

### <a name="remarks"></a>备注

`m_nNumPreviewPages`成员是 UINT 类型的公共变量。

## <a name="cprintinfom_noffsetpage"></a><a name="m_noffsetpage"></a> CPrintInfo：： m_nOffsetPage

包含组合 DocObject 打印作业中特定 DocObject 的第一页之前的页数。

## <a name="cprintinfom_ppd"></a><a name="m_ppd"></a> CPrintInfo：： m_pPD

包含一个指向对象的指针，该 `CPrintDialog` 对象用于显示打印作业的 "打印" 对话框。

### <a name="remarks"></a>备注

`m_pPD`成员是声明为指向的指针的公共变量 `CPrintDialog` 。

## <a name="cprintinfom_rectdraw"></a><a name="m_rectdraw"></a> CPrintInfo：： m_rectDraw

指定以逻辑坐标表示的页面可用的绘图区域。

### <a name="remarks"></a>备注

你可能希望在替代中引用此项 `CView::OnPrint` 。 您可以使用此成员跟踪打印页眉、页脚等后仍可用的区域。 该 `m_rectDraw` 成员是类型的公共变量 `CRect` 。

## <a name="cprintinfom_strpagedesc"></a><a name="m_strpagedesc"></a> CPrintInfo：： m_strPageDesc

包含用于在打印预览期间显示页码的格式字符串;此字符串包含两个子字符串，一个用于单页显示，另一个用于双页显示，每个子字符串由 "\n" 字符终止。

### <a name="remarks"></a>备注

框架使用 "Page%u\nPages% u-%u\n" 作为默认值。 如果需要不同的页码格式，请在重写中指定格式字符串 `CView::OnPreparePrinting` 。 该 `m_strPageDesc` 成员是类型的公共变量 `CString` 。

## <a name="cprintinfosetmaxpage"></a><a name="setmaxpage"></a> CPrintInfo：： SetMaxPage

调用此函数可指定文档的最后一页的页码。

```cpp
void SetMaxPage(UINT nMaxPage);
```

### <a name="parameters"></a>parameters

*nMaxPage*<br/>
文档的最后一页的页码。

### <a name="remarks"></a>备注

此值存储在 `CPrintDialog` 成员引用的对象中 `m_pPD` 。 如果文档的长度在打印之前是已知的，则从的重写中调用此函数 `CView::OnPreparePrinting` 。 如果文档的长度取决于用户在 "打印" 对话框中指定的设置，请从的重写调用此函数 `CView::OnBeginPrinting` 。 如果文档的长度在打印之前是未知的，请使用 `m_bContinuePrinting` 成员来控制打印循环。

### <a name="example"></a>示例

  请参阅 [CView：： OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)的示例。

## <a name="cprintinfosetminpage"></a><a name="setminpage"></a> CPrintInfo：： SetMinPage

调用此函数可指定文档的第一页的页码。

```cpp
void SetMinPage(UINT nMinPage);
```

### <a name="parameters"></a>parameters

*nMinPage*<br/>
文档的第一页的页码。

### <a name="remarks"></a>备注

页码通常从1开始。 此值存储在 `CPrintDialog` 成员引用的对象中 `m_pPD` 。

## <a name="see-also"></a>请参阅

[MFC 示例 DIBLOOK](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CView::OnBeginPrinting](../../mfc/reference/cview-class.md#onbeginprinting)<br/>
[CView：： OnEndPrinting](../../mfc/reference/cview-class.md#onendprinting)<br/>
[CView：： OnEndPrintPreview](../../mfc/reference/cview-class.md#onendprintpreview)<br/>
[CView：： OnPrepareDC](../../mfc/reference/cview-class.md#onpreparedc)<br/>
[CView：： OnPreparePrinting](../../mfc/reference/cview-class.md#onprepareprinting)<br/>
[CView：： OnPrint](../../mfc/reference/cview-class.md#onprint)

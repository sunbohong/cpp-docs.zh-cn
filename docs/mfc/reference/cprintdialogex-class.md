---
description: 了解详细信息： CPrintDialogEx 类
title: CPrintDialogEx 类
ms.date: 11/04/2016
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
ms.openlocfilehash: 2f0d124422efa641c3ace833a5970b364a5cbc48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301459"
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx 类

封装由 Windows 打印属性表提供的服务。

## <a name="syntax"></a>语法

```
class CPrintDialogEx : public CCommonDialog
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|构造 `CPrintDialogEx` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|在不显示 "打印" 对话框的情况下创建打印机设备上下文。|
|[CPrintDialogEx：:D oModal](#domodal)|显示对话框并允许用户进行选择。|
|[CPrintDialogEx::GetCopies](#getcopies)|检索请求的副本数。|
|[CPrintDialogEx::GetDefaults](#getdefaults)|在不显示对话框的情况下检索设备默认值。|
|[CPrintDialogEx::GetDeviceName](#getdevicename)|检索当前所选打印机设备的名称。|
|[CPrintDialogEx::GetDevMode](#getdevmode)|检索 `DEVMODE` 结构。|
|[CPrintDialogEx：： GetDriverName](#getdrivername)|检索系统定义的打印机设备驱动程序的名称。|
|[CPrintDialogEx::GetPortName](#getportname)|检索当前选定的打印机端口的名称。|
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|检索打印机设备上下文的句柄。|
|[CPrintDialogEx：:P rintAll](#printall)|确定是否打印文档的所有页。|
|[CPrintDialogEx：:P rintCollate](#printcollate)|确定是否请求逐份打印副本。|
|[CPrintDialogEx：:P rintCurrentPage](#printcurrentpage)|确定是否打印文档的当前页。|
|[CPrintDialogEx：:P rintRange](#printrange)|确定是否仅打印指定范围的页面。|
|[CPrintDialogEx：:P rintSelection](#printselection)|确定是否仅打印当前选定的项。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CPrintDialogEx：： m_pdex](#m_pdex)|用于自定义对象的结构 `CPrintDialogEx` 。|

## <a name="remarks"></a>备注

您可以依赖于框架来处理应用程序打印过程的许多方面。 有关使用框架来处理打印任务的详细信息，请参阅文章 [打印](../../mfc/printing.md)。

如果希望应用程序在不使用框架的情况下处理打印，则可以使用 `CPrintDialogEx` 提供的构造函数的 "按原样" 类，也可以从派生您自己的对话类， `CPrintDialogEx` 并编写一个构造函数来满足您的需求。 在这两种情况下，这些对话框的行为类似于标准 MFC 对话框，因为它们是从类派生的 `CCommonDialog` 。

若要使用 `CPrintDialogEx` 对象，请先使用 `CPrintDialogEx` 构造函数创建对象。 构造该对话框后，您可以设置或修改 [m_pdex](#m_pdex) 结构中的任何值以初始化对话框控件的值。 `m_pdex`结构的类型为[PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw)。 有关此结构的详细信息，请参阅 Windows SDK。

如果没有 `m_pdex` 为和成员提供自己的句柄 `hDevMode` `hDevNames` ，请确保在 `GlobalFree` 完成该对话框后，为这些句柄调用 Windows 函数。

初始化对话框控件后，调用 `DoModal` 成员函数以显示对话框，并允许用户选择打印选项。 `DoModal`返回时，可以确定用户是否选择了 "确定"、"应用" 或 "取消" 按钮。

如果用户按 "确定"，则可以使用 `CPrintDialogEx` 的成员函数来检索用户输入的信息。

此 `CPrintDialogEx::GetDefaults` 成员函数可用于检索当前打印机默认值，而不会显示对话框。 此方法无需用户交互。

您可以使用 Windows `CommDlgExtendedError` 函数来确定初始化对话框期间是否发生了错误，并了解有关该错误的详细信息。 有关此函数的详细信息，请参阅 Windows SDK。

有关使用的详细信息 `CPrintDialogEx` ，请参阅 [通用对话框类](../../mfc/common-dialog-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

`IObjectWithSite`

`IPrintDialogCallback`

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`CPrintDialogEx`

## <a name="requirements"></a>要求

**标头：** afxdlgs

## <a name="cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a> CPrintDialogEx::CPrintDialogEx

构造 Windows 打印属性表。

```
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,
    CWnd* pParentWnd = NULL);
```

### <a name="parameters"></a>parameters

dwFlags <br/>
可用于自定义对话框的设置的一个或多个标志，使用按位 "或" 运算符组合在一起。 例如，PD_ALLPAGES 标志将默认打印范围设置为文档的所有页。 有关这些标志的详细信息，请参阅 Windows SDK 中的 [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 结构。

*pParentWnd*<br/>
指向对话框的父窗口或所有者窗口的指针。

### <a name="remarks"></a>备注

此成员函数仅构造对象。 使用 `DoModal` 成员函数来显示对话框。

## <a name="cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a> CPrintDialogEx::CreatePrinterDC

从 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 和 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 结构中 (DC) 创建打印机设备上下文。

```
HDC CreatePrinterDC();
```

### <a name="return-value"></a>返回值

新创建的打印机设备上下文的句柄。

### <a name="remarks"></a>备注

返回的 DC 还会存储在 `hDC` [m_pdex](#m_pdex)的成员中。

此 DC 被假定为当前打印机 DC，并且必须删除任何其他以前获得的打印机 Dc。 可以调用此函数，并使用生成的 DC，无需显示 "打印" 对话框。

## <a name="cprintdialogexdomodal"></a><a name="domodal"></a> CPrintDialogEx：:D oModal

调用此函数以显示 Windows Print 属性表，并允许用户选择各种打印选项，如副本数、页面范围以及是否应逐份打印副本。

```
virtual INT_PTR DoModal();
```

### <a name="return-value"></a>返回值

INT_PTR 返回值实际上是 HRESULT。 请参阅 Windows SDK 中 [PrintDlgEx](/previous-versions/windows/desktop/legacy/ms646942\(v=vs.85\)) 的返回值部分。

### <a name="remarks"></a>备注

如果希望通过设置结构的成员来初始化各种打印对话框选项 `m_pdex` ，应在调用之前执行此操作 `DoModal` ，但在构造对话框对象之后。

调用后 `DoModal` ，可以调用其他成员函数来检索用户在对话框中输入的设置或信息。

如果在调用时使用 PD_RETURNDC 标志 `DoModal` ，则将在 m_pdex 的成员中返回打印机 DC `hDC` 。 [](#m_pdex) 必须通过调用方调用 [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) 来释放此 DC `CPrintDialogEx` 。

## <a name="cprintdialogexgetcopies"></a><a name="getcopies"></a> CPrintDialogEx::GetCopies

在调用 `DoModal` 以检索请求的副本数后调用此函数。

```
int GetCopies() const;
```

### <a name="return-value"></a>返回值

请求的副本数。

## <a name="cprintdialogexgetdefaults"></a><a name="getdefaults"></a> CPrintDialogEx::GetDefaults

调用此函数可检索默认打印机的设备默认值，而不会显示对话框。

```
BOOL GetDefaults();
```

### <a name="return-value"></a>返回值

如果成功，则为 TRUE; 否则为 FALSE。

### <a name="remarks"></a>备注

从 [DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea) 和 [DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames) 结构中 (DC) 创建打印机设备上下文。

`GetDefaults` 不显示打印属性页。 相反，它会将 `hDevNames` m_pdex 的和成员设置为 `hDevMode` 处理系统默认打印机初始化的[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)和[DEVNAMES](/windows/win32/api/commdlg/ns-commdlg-devnames)结构。 [](#m_pdex) `hDevNames`和都 `hDevMode` 必须为 NULL 或 `GetDefaults` 失败。

如果设置了 PD_RETURNDC 标志，此函数将不会只返回 `hDevNames` 和 `hDevMode` (位于 `m_pdex.hDevNames` 和 `m_pdex.hDevMode`) 到调用方，但也将在中返回打印机 DC `m_pdex.hDC` 。 当您完成对象时，调用方负责删除打印机 DC 并在句柄上调用 Windows [GlobalFree](/windows/win32/api/winbase/nf-winbase-globalfree) 函数 `CPrintDialogEx` 。

## <a name="cprintdialogexgetdevicename"></a><a name="getdevicename"></a> CPrintDialogEx::GetDeviceName

在调用 [DoModal](#domodal) 以检索当前所选打印机的名称后，或在调用 [GetDefaults](#getdefaults) 检索默认打印机的名称后，调用此函数。

```
CString GetDeviceName() const;
```

### <a name="return-value"></a>返回值

当前选定的打印机的名称。

### <a name="remarks"></a>备注

`CString` `GetDeviceName` `lpszDeviceName` 在对[CDC：： CreateDC](../../mfc/reference/cdc-class.md#createdc)的调用中，使用指向返回的对象的指针作为的值。

## <a name="cprintdialogexgetdevmode"></a><a name="getdevmode"></a> CPrintDialogEx::GetDevMode

在调用 [DoModal](#domodal) 或 [GetDefaults](#getdefaults) 后调用此函数可检索有关打印设备的信息。

```
LPDEVMODE GetDevMode() const;
```

### <a name="return-value"></a>返回值

[DEVMODE](/windows/win32/api/wingdi/ns-wingdi-devmodea)数据结构，其中包含有关打印机驱动程序的设备初始化和环境的信息。 必须使用 Windows SDK 中描述的 Windows [GlobalUnlock](/windows/win32/api/winbase/nf-winbase-globalunlock) 函数来解锁此结构使用的内存。

## <a name="cprintdialogexgetdrivername"></a><a name="getdrivername"></a> CPrintDialogEx：： GetDriverName

在调用 [DoModal](#domodal) 或 [GetDefaults](#getdefaults) 后调用此函数可检索系统定义的打印机设备驱动程序的名称。

```
CString GetDriverName() const;
```

### <a name="return-value"></a>返回值

一个， `CString` 指定系统定义的驱动程序名称。

### <a name="remarks"></a>备注

`CString` `GetDriverName` 在对 [CDC：： CreateDC](../../mfc/reference/cdc-class.md#createdc)的调用中，使用指向作为 *lpszDriverName* 值返回的对象的指针。

## <a name="cprintdialogexgetportname"></a><a name="getportname"></a> CPrintDialogEx::GetPortName

调用 [DoModal](#domodal) 或 [GetDefaults](#getdefaults) 后调用此函数可检索当前选定的打印机端口的名称。

```
CString GetPortName() const;
```

### <a name="return-value"></a>返回值

当前选定的打印机端口的名称。

## <a name="cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a> CPrintDialogEx::GetPrinterDC

返回打印机设备上下文的句柄。

```
HDC GetPrinterDC() const;
```

### <a name="return-value"></a>返回值

打印机设备上下文的句柄。

### <a name="remarks"></a>备注

使用 Windows [DeleteDC](/windows/win32/api/wingdi/nf-wingdi-deletedc) 函数时，必须调用该函数以删除设备上下文。

## <a name="cprintdialogexm_pdex"></a><a name="m_pdex"></a> CPrintDialogEx：： m_pdex

一个 PRINTDLGEX 结构，其成员存储对话框对象的特征。

```
PRINTDLGEX m_pdex;
```

### <a name="remarks"></a>备注

构造对象之后 `CPrintDialogEx` ，您可以使用在 `m_pdex` 调用 [DoModal](#domodal) 成员函数之前设置对话框的各个方面。 有关结构的详细信息 `m_pdex` ，请参阅 Windows SDK 中的 [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 。

如果 `m_pdex` 直接修改数据成员，将重写任何默认行为。

## <a name="cprintdialogexprintall"></a><a name="printall"></a> CPrintDialogEx：:P rintAll

调用后调用此函数 `DoModal` 可确定是否要打印文档中的所有页。

```
BOOL PrintAll() const;
```

### <a name="return-value"></a>返回值

如果文档中的所有页面都要打印，则为 TRUE;否则为 FALSE。

## <a name="cprintdialogexprintcollate"></a><a name="printcollate"></a> CPrintDialogEx：:P rintCollate

调用后调用此函数 `DoModal` 可确定打印机是否应逐份打印文档的所有打印副本。

```
BOOL PrintCollate() const;
```

### <a name="return-value"></a>返回值

如果用户在对话框中选中了 "逐份打印" 复选框，则为 TRUE;否则为 FALSE。

## <a name="cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a> CPrintDialogEx：:P rintCurrentPage

在调用后调用此函数 `DoModal` 可确定是否在文档中打印当前页。

```
BOOL PrintCurrentPage() const;
```

### <a name="return-value"></a>返回值

如果在 "打印" 对话框中选择了 " **打印当前页** "，则为 TRUE;否则为 FALSE。

## <a name="cprintdialogexprintrange"></a><a name="printrange"></a> CPrintDialogEx：:P rintRange

调用后调用此函数 `DoModal` 可确定是否仅打印文档中的一系列页面。

```
BOOL PrintRange() const;
```

### <a name="return-value"></a>返回值

如果仅打印文档中的一系列页面，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

可以从 [m_pdex](#m_pdex) 确定指定的页范围 (请参阅 `nPageRanges` `nMaxPageRanges` `lpPageRanges` Windows SDK) 中 [PRINTDLGEX](/windows/win32/api/commdlg/ns-commdlg-printdlgexw) 结构中的、和。

## <a name="cprintdialogexprintselection"></a><a name="printselection"></a> CPrintDialogEx：:P rintSelection

调用后调用此函数 `DoModal` 可确定是否仅打印当前选定的项。

```
BOOL PrintSelection() const;
```

### <a name="return-value"></a>返回值

如果仅打印选定项，则为 TRUE;否则为 FALSE。

## <a name="see-also"></a>请参阅

[CCommonDialog 类](../../mfc/reference/ccommondialog-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CPrintInfo 结构](../../mfc/reference/cprintinfo-structure.md)

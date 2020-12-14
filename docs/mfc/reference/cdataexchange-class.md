---
description: 了解详细信息： CDataExchange 类
title: CDataExchange 类
ms.date: 11/04/2016
f1_keywords:
- CDataExchange
- AFXWIN/CDataExchange
- AFXWIN/CDataExchange::CDataExchange
- AFXWIN/CDataExchange::Fail
- AFXWIN/CDataExchange::PrepareCtrl
- AFXWIN/CDataExchange::PrepareEditCtrl
- AFXWIN/CDataExchange::PrepareOleCtrl
- AFXWIN/CDataExchange::m_bSaveAndValidate
- AFXWIN/CDataExchange::m_pDlgWnd
helpviewer_keywords:
- CDataExchange [MFC], CDataExchange
- CDataExchange [MFC], Fail
- CDataExchange [MFC], PrepareCtrl
- CDataExchange [MFC], PrepareEditCtrl
- CDataExchange [MFC], PrepareOleCtrl
- CDataExchange [MFC], m_bSaveAndValidate
- CDataExchange [MFC], m_pDlgWnd
ms.assetid: 84ed6113-325d-493e-a75d-223f03a992b8
ms.openlocfilehash: 36d11dc2b74142bd869b0e7b459d8bdb888b2cef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222172"
---
# <a name="cdataexchange-class"></a>CDataExchange 类

支持 Microsoft 基础类使用的对话框数据交换 (DDX) 和对话框数据验证 (DDV) 例程。

## <a name="syntax"></a>语法

```
class CDataExchange
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDataExchange：： CDataExchange](#cdataexchange)|构造 `CDataExchange` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDataExchange：： Fail](#fail)|当验证失败时调用。 将焦点重置到上一个控件并引发异常。|
|[CDataExchange：:P repareCtrl](#preparectrl)|准备用于数据交换或验证的指定控件。 用于 nonedit 控件。|
|[CDataExchange：:P repareEditCtrl](#prepareeditctrl)|为数据交换或验证准备指定的编辑控件。|
|[CDataExchange：:P repareOleCtrl](#prepareolectrl)|准备指定的 OLE 控件以便进行数据交换或验证。 用于 nonedit 控件。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CDataExchange：： m_bSaveAndValidate](#m_bsaveandvalidate)|用于指示 DDX 和 DDV 方向的标志。|
|[CDataExchange：： m_pDlgWnd](#m_pdlgwnd)|发生数据交换的对话框或窗口。|

## <a name="remarks"></a>备注

`CDataExchange` 没有基类。

如果要为自定义数据类型或控件编写数据交换例程，或者编写自己的数据验证例程，请使用此类。 有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框](../../mfc/dialog-boxes.md)。

`CDataExchange`对象提供 DDX 和 DDV 所需的上下文信息。 如果使用 DDX 来填充数据成员的对话框控件初始值，则标志 *m_bSaveAndValidate* 为 FALSE。 当使用 DDX 将对话框控件的当前值设置为数据成员，并使用 DDV 来验证数据值时，标志 *m_bSaveAndValidate* 为 TRUE。 如果 DDV 验证失败，DDV 过程将显示一个消息框，说明输入错误。 然后，DDV 过程将调用 `Fail` 以将焦点重置为有问题的控件，并引发异常来停止验证过程。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CDataExchange`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cdataexchangecdataexchange"></a><a name="cdataexchange"></a> CDataExchange：： CDataExchange

调用此成员函数以构造 `CDataExchange` 对象。

```
CDataExchange(
    CWnd* pDlgWnd,
    BOOL bSaveAndValidate);
```

### <a name="parameters"></a>parameters

*pDlgWnd*<br/>
指向包含控件的父窗口的指针。 通常，这是一个 [CDialog](../../mfc/reference/cdialog-class.md)派生的对象。

*bSaveAndValidate*<br/>
如果为 TRUE，则此对象验证数据，然后将控件中的数据写入成员。 如果为 FALSE，则此对象将数据从成员移到控件。

### <a name="remarks"></a>备注

自行构造 `CDataExchange` 对象，以存储要传递给窗口 CWnd 的数据交换对象中的额外信息 [：:D odataexchange](../../mfc/reference/cwnd-class.md#dodataexchange) 成员函数。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCControlLadenDialog#70](../../mfc/codesnippet/cpp/cdataexchange-class_1.cpp)]

## <a name="cdataexchangefail"></a><a name="fail"></a> CDataExchange：： Fail

当对话框数据验证 (DDV) 操作失败时，框架将调用此成员函数。

```cpp
void Fail();
```

### <a name="remarks"></a>备注

`Fail` 如果有可用于还原) 的控件，则将焦点和选择还原到验证失败的控件 (。 `Fail` 然后，引发 [CUserException](../../mfc/reference/cuserexception-class.md) 类型的异常以停止验证过程。 异常将导致显示错误的消息框。 DDV 验证失败后，用户可以在有问题的控件中重新输入数据。

当验证失败时，自定义 DDV 例程的实现者可以 `Fail` 从其例程调用。

有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框主题](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangem_bsaveandvalidate"></a><a name="m_bsaveandvalidate"></a> CDataExchange：： m_bSaveAndValidate

此标志指示对话框数据交换 (DDX) 操作的方向。

```
BOOL m_bSaveAndValidate;
```

### <a name="remarks"></a>备注

如果在 `CDataExchange` 用户编辑控件后使用对象将数据从对话框控件移动到对话框类数据成员，则标志为非零。 如果正在使用对象从对话框类数据成员初始化对话框控件，则标志为零。

在 DDV) 的对话框数据 (验证过程中，标志也是非零值。

有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框主题](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangem_pdlgwnd"></a><a name="m_pdlgwnd"></a> CDataExchange：： m_pDlgWnd

包含一个指向 [CWnd](../../mfc/reference/cwnd-class.md) 对象的指针，对话框数据交换 (DDX) 或验证 (DDV) 正在进行。

```
CWnd* m_pDlgWnd;
```

### <a name="remarks"></a>备注

此对象通常是一个 [CDialog](../../mfc/reference/cdialog-class.md) 对象。 自定义 DDX 或 DDV 例程的实现者可以使用此指针获取对包含其所操作控件的对话框窗口的访问权限。

有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框主题](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangepreparectrl"></a><a name="preparectrl"></a> CDataExchange：:P repareCtrl

框架调用此成员函数以为对话框数据交换 (DDX) 和验证 (DDV) 准备指定的控件。

```
HWND PrepareCtrl(int nIDC);
```

### <a name="parameters"></a>parameters

*nIDC*<br/>
要为 DDX 或 DDV 准备的控件的 ID。

### <a name="return-value"></a>返回值

正在为 DDX 或 DDV 准备的控件的 HWND。

### <a name="remarks"></a>备注

使用 [PrepareEditCtrl](#prepareeditctrl) 而不是编辑控件;将此成员函数用于所有其他控件。

准备工作包括在类中存储控件的 HWND `CDataExchange` 。 此框架使用此句柄，在发生 DDX 或 DDV 失败时将焦点还原到以前焦点的控件。

自定义 DDX 或 DDV 例程的实现者应 `PrepareCtrl` 为所有非编辑控件调用，这些控件通过 DDX 或通过 DDV 验证数据来交换数据。

有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框主题](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangeprepareeditctrl"></a><a name="prepareeditctrl"></a> CDataExchange：:P repareEditCtrl

框架调用此成员函数以为对话框数据交换 (DDX) 和验证 (DDV) 准备指定的编辑控件。

```
HWND PrepareEditCtrl(int nIDC);
```

### <a name="parameters"></a>parameters

*nIDC*<br/>
要为 DDX 或 DDV 准备的编辑控件的 ID。

### <a name="return-value"></a>返回值

为 DDX 或 DDV 准备的编辑控件的 HWND。

### <a name="remarks"></a>备注

使用 [PrepareCtrl](#preparectrl) 而不是所有非编辑控件。

准备工作包括两项。 首先， `PrepareEditCtrl` 将控件的 HWND 存储在 `CDataExchange` 类中。 此框架使用此句柄，在发生 DDX 或 DDV 失败时将焦点还原到以前焦点的控件。 其次， `PrepareEditCtrl` 在类中设置标志， `CDataExchange` 以指示要交换或验证其数据的控件是编辑控件。

自定义 DDX 或 DDV 例程的实现者应 `PrepareEditCtrl` 为所有编辑控件调用，这些控件通过 DDX 或通过 DDV 验证数据来交换数据。

有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框主题](../../mfc/dialog-boxes.md)。

## <a name="cdataexchangeprepareolectrl"></a><a name="prepareolectrl"></a> CDataExchange：:P repareOleCtrl

框架调用此成员函数为对话框数据交换准备指定的 OLE 控件 (DDX) 和验证 (DDV) 。

```
COleControlSite* PrepareOleCtrl(int nIDC);
```

### <a name="parameters"></a>parameters

*nIDC*<br/>
要为 DDX 或 DDV 准备的 OLE 控件的 ID。

### <a name="return-value"></a>返回值

指向 OLE 控件站点的指针。

### <a name="remarks"></a>备注

对于所有其他非 OLE 控件，请使用 [PrepareEditCtrl](#prepareeditctrl) 而不是编辑控件或 [PrepareCtrl](#preparectrl) 。

自定义 DDX 或 DDV 例程的实现者应调用其 `PrepareOleCtrl` 通过 DDX 或通过 DDV 验证数据的所有 OLE 控件。

有关编写自己的 DDX 和 DDV 例程的详细信息，请参阅 [技术说明 26](../../mfc/tn026-ddx-and-ddv-routines.md)。 有关 DDX 和 DDV 的概述，请参阅 [对话框数据交换和验证](../../mfc/dialog-data-exchange-and-validation.md) 和 [对话框主题](../../mfc/dialog-boxes.md)。

## <a name="see-also"></a>请参阅

[MFC 示例 VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CWnd：:D oDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange)<br/>
[CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata)

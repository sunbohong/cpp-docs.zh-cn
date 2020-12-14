---
description: 了解详细信息： CWinFormsDialog 类
title: CWinFormsDialog 类
ms.date: 03/27/2019
f1_keywords:
- CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::CWinFormsDialog
- AFXWINFORMS/CWinFormsDialog::GetControl
- AFXWINFORMS/CWinFormsDialog::GetControlHandle
- AFXWINFORMS/CWinFormsDialog::OnInitDialog
helpviewer_keywords:
- CWinFormsDialog [MFC], CWinFormsDialog
- CWinFormsDialog [MFC], GetControl
- CWinFormsDialog [MFC], GetControlHandle
- CWinFormsDialog [MFC], OnInitDialog
ms.assetid: e3cec000-a578-448e-b06a-8af256312f61
ms.openlocfilehash: 501f9c354bd6f0b7a628aabb93f4680155f74a69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342616"
---
# <a name="cwinformsdialog-class"></a>CWinFormsDialog 类

承载 Windows 窗体用户控件的 MFC 对话框类的包装器。

## <a name="syntax"></a>语法

```
template <typename TManagedControl>
class CWinFormsDialog :
    public CDialog
```

#### <a name="parameters"></a>parameters

*TManagedControl*<br/>
要在 MFC 应用程序中显示的 .NET Framework 用户控件。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CWinFormsDialog：： CWinFormsDialog](#cwinformsdialog)|构造 `CWinFormsDialog` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CWinFormsDialog：： GetControl](#getcontrol)|检索对 Windows 窗体用户控件的引用。|
|[CWinFormsDialog：： GetControlHandle](#getcontrolhandle)|检索 Windows 窗体用户控件的窗口句柄。|
|[CWinFormsDialog：： OnInitDialog](#oninitdialog)|通过在其上创建并承载 Windows 窗体用户控件来初始化 MFC 对话框。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-|
|[CWinFormsDialog：： operator-&gt;](#operator_-_gt)|替换表达式中的 [CWinFormsDialog：： GetControl](#getcontrol) 。|
|[CWinFormsDialog：： operator TManagedControl ^](#operator-tmanagedcontrol-hat)|将类型强制转换为对 Windows 窗体用户控件的引用。|

## <a name="remarks"></a>备注

`CWinFormsDialog` 是 MFC 对话框类的包装器 ( 承载 Windows 窗体用户控件的 [CDialog](../../mfc/reference/cdialog-class.md)) 。 这允许在模式或无模式 MFC 对话框中显示 .NET Framework 控件。

有关使用 Windows 窗体的详细信息，请参阅 [在 mfc 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md) 和将 [Windows 窗体用户控件承载为 mfc 对话框](../../dotnet/hosting-a-windows-form-user-control-as-an-mfc-dialog-box.md)。

## <a name="requirements"></a>要求

**标头：** afxwinforms

## <a name="cwinformsdialogcwinformsdialog"></a><a name="cwinformsdialog"></a> CWinFormsDialog：： CWinFormsDialog

构造 `CWinFormsDialog` 对象。

```
CWinFormsDialog(UINT nIDTemplate = IDD);
```

### <a name="parameters"></a>parameters

*nIDTemplate*<br/>
包含对话框模板资源的 ID。 使用对话框编辑器创建对话框模板并将其存储在应用程序的资源脚本文件中。 有关对话框模板的详细信息，请参阅 [CDialog 类](../../mfc/reference/cdialog-class.md)。

## <a name="cwinformsdialoggetcontrol"></a><a name="getcontrol"></a> CWinFormsDialog：： GetControl

检索对 Windows 窗体用户控件的引用。

```
inline TManagedControl^ GetControl() const;
```

### <a name="return-value"></a>返回值

返回对 "MFC" 对话框中 Windows 窗体控件的引用。

## <a name="cwinformsdialoggetcontrolhandle"></a><a name="getcontrolhandle"></a> CWinFormsDialog：： GetControlHandle

检索 Windows 窗体用户控件的窗口句柄。

```
inline HWND GetControlHandle() const throw();
```

### <a name="return-value"></a>返回值

返回 Windows 窗体用户控件的窗口句柄。

## <a name="cwinformsdialogoninitdialog"></a><a name="oninitdialog"></a> CWinFormsDialog：： OnInitDialog

通过在其上创建并承载 Windows 窗体用户控件来初始化 MFC 对话框。

```
virtual BOOL OnInitDialog();
```

### <a name="return-value"></a>返回值

一个布尔值，指定应用程序是否已将输入焦点设置到对话框中的某个控件。 如果 `OnInitDialog` 返回非零值，则 Windows 将输入焦点设置到对话框中的第一个控件。 仅当应用程序已将输入焦点显式设置到对话框中的某个控件时，此方法才会返回0。

### <a name="remarks"></a>备注

当使用从[CDialog](../../mfc/reference/cdialog-class.md)) 继承的[Create](../../mfc/reference/cdialog-class.md#create)、 [CreateIndirect](../../mfc/reference/cdialog-class.md#createindirect)或[DoModal](../../mfc/reference/cdialog-class.md#domodal)方法 (创建 "MFC" 对话框时，将发送 WM_INITDIALOG 消息并调用此方法。 它在对话框上创建 Windows 窗体控件的实例，并调整对话框的大小以适应用户控件的大小。 然后，它将在 "MFC" 对话框中承载新的控件。

如果在初始化对话框时需要执行特殊处理，请重写此成员函数。 有关使用此方法的详细信息，请参阅 [CDialog：： OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)。

## <a name="cwinformsdialogoperator--gt"></a><a name="operator_-_gt"></a> CWinFormsDialog：： operator-&gt;

替换表达式中的 [CWinFormsDialog：： GetControl](#getcontrol) 。

```
inline TManagedControl^  operator->() const throw();
```

### <a name="remarks"></a>备注

此运算符提供了一个方便的语法，可 `GetControl` 在表达式中进行替换。

有关使用 Windows 窗体的信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

## <a name="cwinformsdialogoperator-tmanagedcontrol"></a><a name="operator-tmanagedcontrol-hat"></a> CWinFormsDialog：： operator TManagedControl ^

将类型强制转换为对 Windows 窗体用户控件的引用。

```
inline operator TManagedControl^() const throw();
```

### <a name="remarks"></a>备注

此运算符将类型转换为对 Windows 窗体控件的引用。 它用于将一个对话框传递 `CWinFormsDialog<TManagedControl>` 到接受指向 Windows 窗体用户控件对象的指针的函数。

## <a name="see-also"></a>请参阅

[CWnd 类](../../mfc/reference/cwnd-class.md)<br/>
[CWinFormsView 类](../../mfc/reference/cwinformsview-class.md)<br/>
[CDialog 类](../../mfc/reference/cdialog-class.md)

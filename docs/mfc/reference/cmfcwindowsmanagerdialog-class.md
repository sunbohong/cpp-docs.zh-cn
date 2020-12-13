---
description: 了解详细信息： CMFCWindowsManagerDialog 类
title: CMFCWindowsManagerDialog 类
ms.date: 11/04/2016
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
ms.openlocfilehash: 526cf731e049ffd267382b0c3895b5d29792dcb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331621"
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog 类

`CMFCWindowsManagerDialog`对象使用户能够在 mdi 应用程序中管理 mdi 子窗口。

## <a name="syntax"></a>语法

```
class CMFCWindowsManagerDialog : public CDialog
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|构造 `CMFCWindowsManagerDialog` 对象。|

## <a name="remarks"></a>备注

`CMFCWindowsManagerDialog`包含当前在应用程序中打开的 MDI 子窗口的列表。 用户可以使用此对话框手动控制 MDI 子窗口的状态。

`CMFCWindowsManagerDialog` 嵌入在 [CMDIFrameWndEx 类](../../mfc/reference/cmdiframewndex-class.md)中。 不是 `CMFCWindowsManagerDialog` 应手动创建的类。 改为调用函数 [CMDIFrameWndEx：： ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)，它将创建并显示 `CMFCWindowsManagerDialog` 对象。

## <a name="example"></a>示例

下面的示例演示如何 `CMFCWindowsManagerDialog` 通过调用构造对象 `CMDIFrameWndEx::ShowWindowsDialog` 。 此代码片段是 [Visual Studio 演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)

## <a name="requirements"></a>要求

**标头：** afxWindowsManagerDialog

## <a name="cmfcwindowsmanagerdialogcmfcwindowsmanagerdialog"></a><a name="cmfcwindowsmanagerdialog"></a> CMFCWindowsManagerDialog::CMFCWindowsManagerDialog

构造 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md) 对象。

```
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,
    BOOL bHelpButton = FALSE);
```

### <a name="parameters"></a>parameters

*pMDIFrame*<br/>
中指向父窗口或所有者窗口的指针。

*bHelpButton*<br/>
中一个布尔参数，指定框架是否显示 " **帮助** " 按钮。

### <a name="remarks"></a>备注

有关视觉对象管理器的详细信息，请参阅 [可视化管理器](../../mfc/visualization-manager.md)。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMDIFrameWndEx 类](../../mfc/reference/cmdiframewndex-class.md)

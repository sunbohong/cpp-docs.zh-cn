---
description: 了解详细信息： CSimpleDialog 类
title: CSimpleDialog 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleDialog
- ATLWIN/ATL::CSimpleDialog
- ATLWIN/ATL::CSimpleDialog::DoModal
helpviewer_keywords:
- CSimpleDialog class
- CSimpleDialog class, modal dialog boxes in ATL
- dialog boxes, modal
- modal dialog boxes, ATL
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
ms.openlocfilehash: 50889c4387515c85cd3c6e53bf12e7c0494504ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140642"
---
# <a name="csimpledialog-class"></a>CSimpleDialog 类

此类实现基本模式对话框。

## <a name="syntax"></a>语法

```
template <WORD t_wDlgTemplateID, BOOL t_bCenter = TRUE>
class CSimpleDialog : public CDialogImplBase
```

#### <a name="parameters"></a>parameters

*t_wDlgTemplateID*

对话框模板资源的资源 ID。

*t_bCenter*<br/>
如果对话框对象在所有者窗口中居中，则为 TRUE;否则为 FALSE。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleDialog：:D oModal](#domodal)|创建模式对话框。|

## <a name="remarks"></a>备注

实现带有基本功能的模式对话框。 `CSimpleDialog` 仅提供对 Windows 公共控件的支持。 若要创建和显示模式对话框，请创建此类的实例，同时提供该对话框的现有资源模板的名称。 当用户单击带有预定义值 (（如 IDOK 或 IDCANCEL) ）的任何控件时，对话框对象将关闭。

`CSimpleDialog` 允许您仅创建模式对话框。 `CSimpleDialog` 提供对话框过程，该过程使用默认消息映射将消息定向到适当的处理程序。

有关详细信息，请参阅 [实现对话框](../../atl/implementing-a-dialog-box.md) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CDialogImplBase`

`CSimpleDialog`

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="csimpledialogdomodal"></a><a name="domodal"></a> CSimpleDialog：:D oModal

调用模式对话框并在完成后返回对话框结果。

```
INT_PTR DoModal(HWND hWndParent = ::GetActiveWindow());
```

### <a name="parameters"></a>parameters

*hWndParent*<br/>
对话框父级的句柄。 如果未提供任何值，则将父级设置为当前的活动窗口。

### <a name="return-value"></a>返回值

如果成功，则返回值为关闭对话框的控件的资源 ID。

如果函数失败，则返回值为-1。 若要获得扩展的错误信息，请调用 `GetLastError`。

### <a name="remarks"></a>备注

当对话框处于活动状态时，此方法将处理与用户的所有交互。 这就是使对话框模式的：也就是说，在关闭该对话框之前，用户无法与其他窗口交互。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)

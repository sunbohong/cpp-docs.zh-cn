---
description: 了解详细信息： COleDialog 类
title: COleDialog 类
ms.date: 11/04/2016
f1_keywords:
- COleDialog
- AFXODLGS/COleDialog
- AFXODLGS/COleDialog::GetLastError
helpviewer_keywords:
- COleDialog [MFC], GetLastError
ms.assetid: b1ed0aca-3914-4b00-af34-4a4fb491aec7
ms.openlocfilehash: 9bdb532d58136ac2aac622fa88f674e60ec7221e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227294"
---
# <a name="coledialog-class"></a>COleDialog 类

提供 OLE 对话框共有的功能。

## <a name="syntax"></a>语法

```
class COleDialog : public CCommonDialog
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[COleDialog：： GetLastError](#getlasterror)|获取对话框返回的错误代码。|

## <a name="remarks"></a>备注

Microsoft 基础类库提供了多个派生自的类 `COleDialog` ：

- [COleInsertDialog](../../mfc/reference/coleinsertdialog-class.md)

- [COleConvertDialog](../../mfc/reference/coleconvertdialog-class.md)

- [COleChangeIconDialog](../../mfc/reference/colechangeicondialog-class.md)

- [COleLinksDialog](../../mfc/reference/colelinksdialog-class.md)

- [COleBusyDialog](../../mfc/reference/colebusydialog-class.md)

- [COleUpdateDialog](../../mfc/reference/coleupdatedialog-class.md)

- [COlePasteSpecialDialog](../../mfc/reference/colepastespecialdialog-class.md)

- [COlePropertiesDialog](../../mfc/reference/colepropertiesdialog-class.md)

- [COleChangeSourceDialog](../../mfc/reference/colechangesourcedialog-class.md)

有关特定于 OLE 的对话框的详细信息，请参阅 [ole 中](../../mfc/dialog-boxes-in-ole.md)的文章对话框。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CCommonDialog](../../mfc/reference/ccommondialog-class.md)

`COleDialog`

## <a name="requirements"></a>要求

**标头：** afxodlgs

## <a name="coledialoggetlasterror"></a><a name="getlasterror"></a> COleDialog：： GetLastError

`GetLastError`在返回 IDABORT 时调用成员函数以获取其他错误信息 `DoModal` 。

```
UINT GetLastError() const;
```

### <a name="return-value"></a>返回值

返回的错误代码 `GetLastError` 取决于所显示的特定对话框。

### <a name="remarks"></a>备注

有关 `DoModal` 特定错误消息的信息，请参见派生类中的成员函数。

## <a name="see-also"></a>请参阅

[CCommonDialog 类](../../mfc/reference/ccommondialog-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)

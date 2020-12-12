---
description: 了解详细信息： CMFCRibbonCustomizeDialog 类
title: CMFCRibbonCustomizeDialog 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog
helpviewer_keywords:
- CMFCRibbonCustomizeDialog [MFC], CMFCRibbonCustomizeDialog
ms.assetid: ce67de7f-5eaa-4c75-9b94-f290f36df073
ms.openlocfilehash: 9420ebdf32a1c26cba6efee17467fd3dfe202574
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293607"
---
# <a name="cmfcribboncustomizedialog-class"></a>CMFCRibbonCustomizeDialog 类

显示功能区 **自定义** 页。

## <a name="syntax"></a>语法

```
class CMFCRibbonCustomizeDialog : public CMFCPropertySheet
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog](#cmfcribboncustomizedialog)|构造 `CMFCRibbonCustomizeDialog` 对象。|
|`CMFCRibbonCustomizeDialog::~CMFCRibbonCustomizeDialog`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|`CMFCRibbonCustomizeDialog::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|

## <a name="remarks"></a>备注

如果未处理 AFX_WM_ON_RIBBON_CUSTOMIZE 消息，或从消息处理程序返回0，MFC 会自动实例化此类。

如果要在应用程序中使用此类来显示 "功能区 **自定义** " 对话框，只需对其进行实例化并调用 `DoModal` 方法。

由于此类派生自 [CMFCPropertySheet 类](../../mfc/reference/cmfcpropertysheet-class.md)，因此你可以使用 API 来添加自定义页 `CMFCPropertySheet` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CPropertySheet](../../mfc/reference/cpropertysheet-class.md)

[CMFCPropertySheet](../../mfc/reference/cmfcpropertysheet-class.md)

[CMFCRibbonCustomizeDialog](../../mfc/reference/cmfcribboncustomizedialog-class.md)

## <a name="requirements"></a>要求

**标头：** afxribboncustomizedialog

## <a name="cmfcribboncustomizedialogcmfcribboncustomizedialog"></a><a name="cmfcribboncustomizedialog"></a> CMFCRibbonCustomizeDialog::CMFCRibbonCustomizeDialog

构造 `CMFCRibbonCustomizeDialog` 对象。

```
CMFCRibbonCustomizeDialog(
    CWnd* pWndParent,
    CMFCRibbonBar* pRibbon);
```

### <a name="parameters"></a>parameters

*pWndParent*<br/>
中指向父窗口的指针 (通常是主帧) 。

*pRibbon*<br/>
中指向 `CMFCRibbonBar` 要自定义的的指针。

### <a name="example"></a>示例

下面的示例演示如何构造 `CMFCRibbonCustomizeDialog` 对象。

[!code-cpp[NVC_MFC_RibbonApp#18](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizedialog-class_1.cpp)]

### <a name="remarks"></a>备注

构造函数实例化一个 [CMFCRibbonCustomizePropertyPage 类](../../mfc/reference/cmfcribboncustomizepropertypage-class.md) 对象，并将其添加到属性表页的集合中。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)

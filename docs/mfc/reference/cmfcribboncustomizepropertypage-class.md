---
description: 了解详细信息： CMFCRibbonCustomizePropertyPage 类
title: CMFCRibbonCustomizePropertyPage 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::AddCustomCategory
- AFXRIBBONCUSTOMIZEDIALOG/CMFCRibbonCustomizePropertyPage::OnOK
helpviewer_keywords:
- CMFCRibbonCustomizePropertyPage [MFC], CMFCRibbonCustomizePropertyPage
- CMFCRibbonCustomizePropertyPage [MFC], AddCustomCategory
- CMFCRibbonCustomizePropertyPage [MFC], OnOK
ms.assetid: ea32a99a-dfbe-401e-8975-aa191552532f
ms.openlocfilehash: 93792858cec9d07a73bfec56a282b8d672249cf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293594"
---
# <a name="cmfcribboncustomizepropertypage-class"></a>CMFCRibbonCustomizePropertyPage 类

在基于功能区的应用程序中为 " **自定义** " 对话框实现自定义页。

## <a name="syntax"></a>语法

```
class CMFCRibbonCustomizePropertyPage: public CMFCPropertyPage
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|-|-|
|[CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage](#cmfcribboncustomizepropertypage)|构造 `CMFCRibbonCustomizePropertyPage` 对象。|
|`CMFCRibbonCustomizePropertyPage::~CMFCRibbonCustomizePropertyPage`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|-|-|
|[CMFCRibbonCustomizePropertyPage::AddCustomCategory](#addcustomcategory)|将自定义类别添加到 " **命令** " 组合框。|
|`CMFCRibbonCustomizePropertyPage::CreateObject`|由框架用于创建此类类型的动态实例。|
|`CMFCRibbonCustomizePropertyPage::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|
|[CMFCRibbonCustomizePropertyPage：： OnOK](#onok)|当用户在 "**自定义**" 对话框中单击 **"确定"** 时由系统调用。|

## <a name="remarks"></a>备注

如果要将自定义命令添加到 " **自定义** " 对话框，则必须处理 AFX_WM_ON_RIBBON_CUSTOMIZE 消息。 在消息处理程序中，实例化 `CMFCRibbonCustomizePropertyPage` 堆栈上的对象。 创建自定义命令列表，然后调用 `AddCustomCategory` 以将新页面添加到 " **自定义** " 对话框。

## <a name="example"></a>示例

下面的示例演示如何构造 `CMFCRibbonCustomizePropertyPage` 对象并添加自定义类别。

[!code-cpp[NVC_MFC_RibbonApp#22](../../mfc/reference/codesnippet/cpp/cmfcribboncustomizepropertypage-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CDialog](../../mfc/reference/cdialog-class.md)

[CPropertyPage](../../mfc/reference/cpropertypage-class.md)

[CMFCPropertyPage](../../mfc/reference/cmfcpropertypage-class.md)

[CMFCRibbonCustomizePropertyPage](../../mfc/reference/cmfcribboncustomizepropertypage-class.md)

## <a name="requirements"></a>要求

**标头：** afxribboncustomizedialog

## <a name="cmfcribboncustomizepropertypageaddcustomcategory"></a><a name="addcustomcategory"></a> CMFCRibbonCustomizePropertyPage::AddCustomCategory

将自定义类别添加到 " **命令** " 组合框。

```cpp
void AddCustomCategory(
    LPCTSTR lpszName,
    const CList<UINT, UINT>& lstIDS);
```

### <a name="parameters"></a>parameters

*lpszName*\
中指定自定义类别名称。

*lstIDS*\
中包含要在自定义类别中显示的功能区命令 Id。

### <a name="remarks"></a>备注

此方法将名为 *lpszName* 的类别添加到 " **命令** " 组合框中。 当用户选择类别时， *lstIDS* 中指定的命令将显示在命令列表中。

## <a name="cmfcribboncustomizepropertypagecmfcribboncustomizepropertypage"></a><a name="cmfcribboncustomizepropertypage"></a> CMFCRibbonCustomizePropertyPage::CMFCRibbonCustomizePropertyPage

构造 `CMFCRibbonCustomizePropertyPage` 对象。

```
CMFCRibbonCustomizePropertyPage(CMFCRibbonBar* pRibbonBar = NULL);
```

### <a name="parameters"></a>parameters

*pRibbonBar*<br/>
中一个指针，指向要为其自定义的选项的功能区控件。

## <a name="cmfcribboncustomizepropertypageonok"></a><a name="onok"></a> CMFCRibbonCustomizePropertyPage：： OnOK

当用户在 "**自定义**" 对话框中单击 **"确定"** 时 Calleld 系统。

```
virtual void OnOK();
```

### <a name="remarks"></a>备注

默认实现将在 " **自定义** " 对话框中选择的选项应用于快速访问工具栏。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)

---
description: 了解详细信息： CFormView 类
title: CFormView 类
ms.date: 11/04/2016
f1_keywords:
- CFormView
- AFXEXT/CFormView
- AFXEXT/CFormView::CFormView
- AFXEXT/CFormView::IsInitDlgCompleted
helpviewer_keywords:
- CFormView [MFC], CFormView
- CFormView [MFC], IsInitDlgCompleted
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
ms.openlocfilehash: ec37a3819f299830fef96bfdf93c0170b2969c66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184304"
---
# <a name="cformview-class"></a>CFormView 类

用于窗体视图的基类。

## <a name="syntax"></a>语法

```
class CFormView : public CScrollView
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CFormView::CFormView](#cformview)|构造 `CFormView` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CFormView::IsInitDlgCompleted](#isinitdlgcompleted)|用于在初始化期间同步。|

## <a name="remarks"></a>备注

窗体视图是实质上是一个包含控件的视图。 这些控件基于对话框模板资源进行布局。 如果你想要你的应用程序具有窗体，请使用 `CFormView`。 这些视图支持使用 [CScrollView](../../mfc/reference/cscrollview-class.md) 功能按需滚动。

[创建 Forms-Based 应用程序](../../mfc/reference/creating-a-forms-based-mfc-application.md)时，可以将其视图类基于 `CFormView` ，使其成为基于窗体的应用程序。

您还可以将新的 [窗体主题](../../mfc/form-views-mfc.md) 插入基于文档视图的应用程序中。 即使你的应用程序最初不支持窗体，当你插入一个新窗体时 Visual C++ 将添加这一支持。

MFC 应用程序向导和“添加类”命令是创建基于窗体的应用程序的首选的方法。 如果需要创建基于窗体的应用程序而不使用这些方法，请参阅 [创建 Forms-Based 应用程序](../../mfc/reference/creating-a-forms-based-mfc-application.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

`CFormView`

## <a name="requirements"></a>要求

**标头：** afxext。h

## <a name="cformviewcformview"></a><a name="cformview"></a> CFormView：： CFormView

构造 `CFormView` 对象。

```
CFormView(LPCTSTR lpszTemplateName);
CFormView(UINT nIDTemplate);
```

### <a name="parameters"></a>parameters

*lpszTemplateName*<br/>
包含以 null 结尾的字符串，它是对话框模板资源的名称。

*nIDTemplate*<br/>
包含对话框模板资源的 ID 号。

### <a name="remarks"></a>备注

当你创建派生自的类型的对象时 `CFormView` ，将调用其中一个构造函数来创建视图对象，并确定该视图所基于的对话框资源。 可以按名称标识资源 (将字符串作为参数传递给构造函数) 或通过其 ID (传递无符号整数作为参数) 。

在调用之前，不会创建窗体视图窗口和子控件 `CWnd::Create` 。 `CWnd::Create` 由框架在文档和视图创建过程（由文档模板驱动）中调用。

> [!NOTE]
> 派生类 *必须* 提供其自己的构造函数。 在构造函数中，调用构造函数， `CFormView::CFormView` 并将资源名称或 ID 作为参数，如前面的类概述中所示。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#90](../../mfc/codesnippet/cpp/cformview-class_1.h)]

[!code-cpp[NVC_MFCDocView#91](../../mfc/codesnippet/cpp/cformview-class_2.cpp)]

## <a name="cformviewisinitdlgcompleted"></a><a name="isinitdlgcompleted"></a> CFormView：： IsInitDlgCompleted

由 MFC 用于确保初始化完成后才会执行其他操作。

```
BOOL IsInitDlgCompleted() const;
```

### <a name="return-value"></a>返回值

如果已完成了此对话框的初始化函数，则为 true。

## <a name="see-also"></a>请参阅

[MFC 示例 SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 示例 VIEWEX](../../overview/visual-cpp-samples.md)<br/>
[CScrollView 类](../../mfc/reference/cscrollview-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDialog 类](../../mfc/reference/cdialog-class.md)<br/>
[CScrollView 类](../../mfc/reference/cscrollview-class.md)

---
description: 了解详细信息： CHtmlEditView 类
title: CHtmlEditView 类
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 9ab998ca16a26fd4ef7a23e4dc58c6542ec330b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261315"
---
# <a name="chtmleditview-class"></a>CHtmlEditView 类

提供 MFC 文档/视图体系结构上下文中的 Web 浏览器编辑平台功能。

## <a name="syntax"></a>语法

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHtmlEditView：： CHtmlEditView](#chtmleditview)|构造 `CHtmlEditView` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CHtmlEditView：： Create](#create)|创建新的窗口对象。|
|[CHtmlEditView：： GetDHtmlDocument](#getdhtmldocument)|返回 `IHTMLDocument2` 当前文档上的接口。|
|[CHtmlEditView：： GetStartDocument](#getstartdocument)|检索此视图的默认文档的名称。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>要求

**标头：** afxhtml.h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a> CHtmlEditView：： CHtmlEditView

构造 `CHtmlEditView` 对象。

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a> CHtmlEditView：： Create

创建新的窗口对象。

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>parameters

*lpszClassName*<br/>
指向以 null 结尾的字符串，该字符串对 Windows 类进行命名。 类名称可以是任何注册到 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) global 函数或 Windows 函数的名称 `RegisterClass` 。 如果为 NULL，则使用预定义的默认 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 属性。

*lpszWindowName*<br/>
指向以 null 结尾的字符串，该字符串表示窗口名称。

*dwStyle*<br/>
指定窗口样式特性。 默认情况下，将设置 WS_VISIBLE 和 WS_CHILD Windows 样式。

*rect*<br/>
对 [矩形](/windows/win32/api/windef/ns-windef-rect) 结构的引用，该结构指定窗口的大小和位置。 *RectDefault* 值允许 Windows 指定新窗口的大小和位置。

*pParentWnd*<br/>
指向控件的父窗口的指针。

*nID*<br/>
视图的 ID 号。 默认情况下，设置为 AFX_IDW_PANE_FIRST。

*pContext*<br/>
指向 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md)的指针。 默认值为 NULL。

### <a name="remarks"></a>备注

此方法还将调用包含的 WebBrowser 的 `Navigate` 方法来加载默认文档 (参见 [CHtmlEditView：： GetStartDocument](#getstartdocument)) 。

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditView：： GetDHtmlDocument

返回 `IHTMLDocument2` 当前文档上的接口。

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>parameters

*ppDocument*<br/>
[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))接口。

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditView：： GetStartDocument

检索此视图的默认文档的名称。

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>请参阅

[HTMLEdit 示例](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)

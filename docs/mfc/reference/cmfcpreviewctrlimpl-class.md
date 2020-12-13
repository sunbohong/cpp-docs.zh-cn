---
description: 了解详细信息： CMFCPreviewCtrlImpl 类
title: CMFCPreviewCtrlImpl 类
ms.date: 11/04/2016
f1_keywords:
- CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::CMFCPreviewCtrlImpl
- AFXWIN/CMFCPreviewCtrlImpl::Create
- AFXWIN/CMFCPreviewCtrlImpl::Destroy
- AFXWIN/CMFCPreviewCtrlImpl::Focus
- AFXWIN/CMFCPreviewCtrlImpl::GetDocument
- AFXWIN/CMFCPreviewCtrlImpl::Redraw
- AFXWIN/CMFCPreviewCtrlImpl::SetDocument
- AFXWIN/CMFCPreviewCtrlImpl::SetHost
- AFXWIN/CMFCPreviewCtrlImpl::SetPreviewVisuals
- AFXWIN/CMFCPreviewCtrlImpl::SetRect
- AFXWIN/CMFCPreviewCtrlImpl::DoPaint
- AFXWIN/CMFCPreviewCtrlImpl::m_clrBackColor
- AFXWIN/CMFCPreviewCtrlImpl::m_clrTextColor
- AFXWIN/CMFCPreviewCtrlImpl::m_font
- AFXWIN/CMFCPreviewCtrlImpl::m_pDocument
helpviewer_keywords:
- CMFCPreviewCtrlImpl [MFC], CMFCPreviewCtrlImpl
- CMFCPreviewCtrlImpl [MFC], Create
- CMFCPreviewCtrlImpl [MFC], Destroy
- CMFCPreviewCtrlImpl [MFC], Focus
- CMFCPreviewCtrlImpl [MFC], GetDocument
- CMFCPreviewCtrlImpl [MFC], Redraw
- CMFCPreviewCtrlImpl [MFC], SetDocument
- CMFCPreviewCtrlImpl [MFC], SetHost
- CMFCPreviewCtrlImpl [MFC], SetPreviewVisuals
- CMFCPreviewCtrlImpl [MFC], SetRect
- CMFCPreviewCtrlImpl [MFC], DoPaint
- CMFCPreviewCtrlImpl [MFC], m_clrBackColor
- CMFCPreviewCtrlImpl [MFC], m_clrTextColor
- CMFCPreviewCtrlImpl [MFC], m_font
- CMFCPreviewCtrlImpl [MFC], m_pDocument
ms.assetid: 06257fa0-54c9-478d-9d68-c9698c3f93ed
ms.openlocfilehash: 09e4b8e023a55110986aafccfd2646d8e7775c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334727"
---
# <a name="cmfcpreviewctrlimpl-class"></a>CMFCPreviewCtrlImpl 类

此类实现放置在 Shell 提供的宿主窗口上用于丰富预览的窗口。

## <a name="syntax"></a>语法

```
class CMFCPreviewCtrlImpl : public CWnd;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCPreviewCtrlImpl：： ~ CMFCPreviewCtrlImpl](#dtor)|Destructs 预览控件对象。|
|[CMFCPreviewCtrlImpl：： CMFCPreviewCtrlImpl](#cmfcpreviewctrlimpl)|构造预览控件对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCPreviewCtrlImpl：： Create](#create)|已重载。 由丰富的预览处理程序调用以创建 Windows 窗口。|
|[CMFCPreviewCtrlImpl：:D estroy](#destroy)|当需要销毁此控件时，由丰富的预览处理程序调用。|
|[CMFCPreviewCtrlImpl：： Focus](#focus)|为此控件设置输入焦点。|
|[CMFCPreviewCtrlImpl：： GetDocument](#getdocument)|返回连接到此预览控件的文档。|
|[CMFCPreviewCtrlImpl：：重绘](#redraw)|通知此控件重绘。|
|[CMFCPreviewCtrlImpl：： SetDocument](#setdocument)|由预览处理程序调用，以创建文档实现和预览控件之间的关系。|
|[CMFCPreviewCtrlImpl：： SetHost](#sethost)|为此控件设置新父代。|
|[CMFCPreviewCtrlImpl：： SetPreviewVisuals](#setpreviewvisuals)|当需要设置丰富预览内容的视觉对象时，由丰富的预览处理程序调用。|
|[CMFCPreviewCtrlImpl：： SetRect](#setrect)|为此控件设置新的边框。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCPreviewCtrlImpl：:D oPaint](#dopaint)|由框架调用以呈现预览。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CMFCPreviewCtrlImpl：： m_clrBackColor](#m_clrbackcolor)|预览窗口的背景色。|
|[CMFCPreviewCtrlImpl：： m_clrTextColor](#m_clrtextcolor)|预览窗口的文本颜色。|
|[CMFCPreviewCtrlImpl：： m_font](#m_font)|用于在预览窗口中显示文本的字体。|
|[CMFCPreviewCtrlImpl：： m_pDocument](#m_pdocument)|指向其内容在控件中预览的文档的指针。|

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPreviewCtrlImpl](../../mfc/reference/cmfcpreviewctrlimpl-class.md)

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="cmfcpreviewctrlimpl"></a> CMFCPreviewCtrlImpl：： CMFCPreviewCtrlImpl

构造预览控件对象。

### <a name="syntax"></a>语法

CMFCPreviewCtrlImpl ( # A1;

## <a name="cmfcpreviewctrlimplcreate"></a><a name="create"></a> CMFCPreviewCtrlImpl：： Create

已重载。 由丰富的预览处理程序调用以创建 Windows 窗口。

### <a name="syntax"></a>语法

```
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc
);
virtual BOOL Create(
   HWND hWndParent,
   const RECT* prc,
   CCreateContext* pContext
);
```

### <a name="parameters"></a>parameters

*hWndParent*<br/>
Shell 为丰富预览提供的宿主窗口的句柄。

*中国*<br/>
指定窗口的初始大小和位置。

*pContext*<br/>
指向创建上下文的指针。

### <a name="return-value"></a>返回值

如果创建成功，则为 TRUE；否则为 FALSE。

## <a name="cmfcpreviewctrlimpldestroy"></a><a name="destroy"></a> CMFCPreviewCtrlImpl：:D estroy

当需要销毁此控件时，由丰富的预览处理程序调用。

### <a name="syntax"></a>语法

```
virtual void Destroy();
```

## <a name="cmfcpreviewctrlimpldopaint"></a><a name="dopaint"></a> CMFCPreviewCtrlImpl：:D oPaint

由框架调用以呈现预览。

### <a name="syntax"></a>语法

```
virtual void DoPaint(
   CPaintDC* pDC
);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
一个指针，指向用于绘制的设备上下文。

## <a name="cmfcpreviewctrlimplfocus"></a><a name="focus"></a> CMFCPreviewCtrlImpl：： Focus

为此控件设置输入焦点。

### <a name="syntax"></a>语法

```
virtual void Focus();
```

## <a name="cmfcpreviewctrlimplgetdocument"></a><a name="getdocument"></a> CMFCPreviewCtrlImpl：： GetDocument

返回连接到此预览控件的文档。

### <a name="syntax"></a>语法

```
ATL::IDocument* GetDocument();
```

### <a name="return-value"></a>返回值

指向文档的指针，该文档的内容将在控件中预览。

## <a name="cmfcpreviewctrlimplm_clrbackcolor"></a><a name="m_clrbackcolor"></a> CMFCPreviewCtrlImpl：： m_clrBackColor

预览窗口的背景色。

### <a name="syntax"></a>语法

```
COLORREF m_clrBackColor;
```

## <a name="cmfcpreviewctrlimplm_clrtextcolor"></a><a name="m_clrtextcolor"></a> CMFCPreviewCtrlImpl：： m_clrTextColor

预览窗口的文本颜色。

### <a name="syntax"></a>语法

```
COLORREF m_clrTextColor;
```

## <a name="cmfcpreviewctrlimplm_font--font-used-to-display-text-in-the-preview-window"></a><a name="m_font"></a> CMFCPreviewCtrlImpl：： m_font 用于在预览窗口中显示文本的字体。

### <a name="syntax"></a>语法

```
CFont m_font;
```

## <a name="cmfcpreviewctrlimplm_pdocument"></a><a name="m_pdocument"></a> CMFCPreviewCtrlImpl：： m_pDocument

指向其内容在控件中预览的文档的指针。

### <a name="syntax"></a>语法

```
ATL::IDocument* m_pDocument;
```

## <a name="cmfcpreviewctrlimplredraw"></a><a name="redraw"></a> CMFCPreviewCtrlImpl：：重绘

通知此控件重绘。

### <a name="syntax"></a>语法

```
virtual void Redraw();
```

## <a name="cmfcpreviewctrlimplsetdocument"></a><a name="setdocument"></a> CMFCPreviewCtrlImpl：： SetDocument

由预览处理程序调用，以创建文档实现和预览控件之间的关系。

### <a name="syntax"></a>语法

```cpp
void SetDocument(
   IDocument* pDocument
);
```

### <a name="parameters"></a>parameters

*pDocument*<br/>
指向文档实现的指针。

## <a name="cmfcpreviewctrlimplsethost"></a><a name="sethost"></a> CMFCPreviewCtrlImpl：： SetHost

为此控件设置新父代。

### <a name="syntax"></a>语法

```
virtual void SetHost(
   HWND hWndParent
);
```

### <a name="parameters"></a>parameters

*hWndParent*<br/>
新的父窗口的句柄。

## <a name="cmfcpreviewctrlimplsetpreviewvisuals"></a><a name="setpreviewvisuals"></a> CMFCPreviewCtrlImpl：： SetPreviewVisuals

当需要设置丰富预览内容的视觉对象时，由丰富的预览处理程序调用。

### <a name="syntax"></a>语法

```
virtual void SetPreviewVisuals(
   COLORREF clrBack,
   COLORREF clrText,
   const LOGFONTW *plf
);
```

### <a name="parameters"></a>parameters

*clrBack*<br/>
预览窗口的背景色。

*clrText*<br/>
预览窗口的文本颜色。

*plf*<br/>
用于在预览窗口中显示文本的字体。

## <a name="cmfcpreviewctrlimplsetrect"></a><a name="setrect"></a> CMFCPreviewCtrlImpl：： SetRect

为此控件设置新的边框。

### <a name="syntax"></a>语法

```
virtual void SetRect(
   const RECT* prc,
   BOOL bRedraw
);
```

### <a name="parameters"></a>parameters

*中国*<br/>
指定预览控件的新大小和位置。

*bRedraw*<br/>
指定是否应重绘控件。

### <a name="remarks"></a>备注

通常，当调整主机控件的大小时，会设置新的边框。

## <a name="cmfcpreviewctrlimplcmfcpreviewctrlimpl"></a><a name="dtor"></a> CMFCPreviewCtrlImpl：： ~ CMFCPreviewCtrlImpl

Destructs 预览控件对象。

### <a name="syntax"></a>语法

```
virtual ~CMFCPreviewCtrlImpl();
```

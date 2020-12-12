---
description: 了解详细信息： CSingleDocTemplate 类
title: CSingleDocTemplate 类
ms.date: 11/04/2016
f1_keywords:
- CSingleDocTemplate
- AFXWIN/CSingleDocTemplate
- AFXWIN/CSingleDocTemplate::CSingleDocTemplate
helpviewer_keywords:
- CSingleDocTemplate [MFC], CSingleDocTemplate
ms.assetid: 4f3a8212-81ee-48a0-ad22-e0ed7c36a391
ms.openlocfilehash: 611cada1c90fa776bafb78f0856658cd1bd0a8e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264617"
---
# <a name="csingledoctemplate-class"></a>CSingleDocTemplate 类

定义实现单文档界面 (SDI) 的文档模板。

## <a name="syntax"></a>语法

```
class CSingleDocTemplate : public CDocTemplate
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSingleDocTemplate::CSingleDocTemplate](#csingledoctemplate)|构造 `CSingleDocTemplate` 对象。|

## <a name="remarks"></a>备注

SDI 应用程序使用主框架窗口显示文档;一次只能打开一个文档。

文档模板定义了三种类型的类之间的关系：

- 一个派生自的文档类 `CDocument` 。

- 视图类，用于显示上面列出的文档类中的数据。 可以从 `CView` 、、或派生此 `CScrollView` 类 `CFormView` `CEditView` 。  (你也可以 `CEditView` 直接使用。 ) 

- 包含视图的框架窗口类。 对于 SDI 文档模板，你可以从派生此类 `CFrameWnd` ; 如果不需要自定义主框架窗口的行为，则可以 `CFrameWnd` 直接使用而无需派生你自己的类。

SDI 应用程序通常支持一种类型的文档，因此它只有一个 `CSingleDocTemplate` 对象。 一次只能打开一个文档。

不需要调用 `CSingleDocTemplate` 除构造函数之外的任何成员函数。 框架 `CSingleDocTemplate` 在内部处理对象。

有关使用的详细信息 `CSingleDocTemplate` ，请参阅 [文档模板和文档/视图创建过程](../../mfc/document-templates-and-the-document-view-creation-process.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocTemplate](../../mfc/reference/cdoctemplate-class.md)

`CSingleDocTemplate`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="csingledoctemplatecsingledoctemplate"></a><a name="csingledoctemplate"></a> CSingleDocTemplate::CSingleDocTemplate

构造 `CSingleDocTemplate` 对象。

```
CSingleDocTemplate(
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>parameters

*nIDResource*<br/>
指定用于文档类型的资源的 ID。 这可能包括菜单、图标、快捷键对应表和字符串资源。

String 资源包含由 "\n" 字符分隔的最多七个子字符串 ("\n" 字符作为占位符（如果不包括子字符串）。但是，不需要后缀 "\n" 字符) ;这些子字符串说明了文档类型。 有关子字符串的信息，请参阅 [CDocTemplate：： GetDocString](../../mfc/reference/cdoctemplate-class.md#getdocstring)。 此字符串资源位于应用程序的资源文件中。 例如：

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_MAINFRAME "MyCalc Windows Application\nSheet\nWorksheet\n Worksheets (*.myc)\n.myc\nMyCalcSheet\n MyCalc Worksheet"
END
```

您可以使用字符串编辑器来编辑此字符串;整个字符串在字符串编辑器中显示为一个条目，而不是作为7个单独的条目。

有关这些资源类型的详细信息，请参阅 [字符串编辑器](../../windows/string-editor.md)。

*pDocClass*<br/>
指向 `CRuntimeClass` document 类的对象。 此类是一个 `CDocument` 派生类，可以定义它来表示文档。

*pFrameClass*<br/>
指向 `CRuntimeClass` 框架窗口类的对象。 此类可以是 `CFrameWnd` 派生类，也可以是其自身（ `CFrameWnd` 如果你希望在主框架窗口中使用默认行为）。

*pViewClass*<br/>
指向 `CRuntimeClass` 视图类的对象。 此类是一个 `CView` 派生类，可以定义它以显示文档。

### <a name="remarks"></a>备注

动态分配 `CSingleDocTemplate` 对象，并 `CWinApp::AddDocTemplate` 从 `InitInstance` 应用程序类的成员函数将其传递到。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocViewSDI#13](../../mfc/codesnippet/cpp/csingledoctemplate-class_1.cpp)]

[!code-cpp[NVC_MFCDocViewSDI#14](../../mfc/codesnippet/cpp/csingledoctemplate-class_2.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例 DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CDocTemplate 类](../../mfc/reference/cdoctemplate-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate 类](../../mfc/reference/cdoctemplate-class.md)<br/>
[CDocument 类](../../mfc/reference/cdocument-class.md)<br/>
[CFrameWnd 类](../../mfc/reference/cframewnd-class.md)<br/>
[CMultiDocTemplate 类](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CView 类](../../mfc/reference/cview-class.md)<br/>
[CWinApp 类](../../mfc/reference/cwinapp-class.md)

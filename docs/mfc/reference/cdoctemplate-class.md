---
description: 了解详细信息： CDocTemplate 类
title: CDocTemplate 类
ms.date: 11/04/2016
f1_keywords:
- CDocTemplate
- AFXWIN/CDocTemplate
- AFXWIN/CDocTemplate::CDocTemplate
- AFXWIN/CDocTemplate::AddDocument
- AFXWIN/CDocTemplate::CloseAllDocuments
- AFXWIN/CDocTemplate::CreateNewDocument
- AFXWIN/CDocTemplate::CreateNewFrame
- AFXWIN/CDocTemplate::CreateOleFrame
- AFXWIN/CDocTemplate::CreatePreviewFrame
- AFXWIN/CDocTemplate::GetDocString
- AFXWIN/CDocTemplate::GetFirstDocPosition
- AFXWIN/CDocTemplate::GetNextDoc
- AFXWIN/CDocTemplate::InitialUpdateFrame
- AFXWIN/CDocTemplate::LoadTemplate
- AFXWIN/CDocTemplate::MatchDocType
- AFXWIN/CDocTemplate::OpenDocumentFile
- AFXWIN/CDocTemplate::RemoveDocument
- AFXWIN/CDocTemplate::SaveAllModified
- AFXWIN/CDocTemplate::SetContainerInfo
- AFXWIN/CDocTemplate::SetDefaultTitle
- AFXWIN/CDocTemplate::SetPreviewInfo
- AFXWIN/CDocTemplate::SetServerInfo
helpviewer_keywords:
- CDocTemplate [MFC], CDocTemplate
- CDocTemplate [MFC], AddDocument
- CDocTemplate [MFC], CloseAllDocuments
- CDocTemplate [MFC], CreateNewDocument
- CDocTemplate [MFC], CreateNewFrame
- CDocTemplate [MFC], CreateOleFrame
- CDocTemplate [MFC], CreatePreviewFrame
- CDocTemplate [MFC], GetDocString
- CDocTemplate [MFC], GetFirstDocPosition
- CDocTemplate [MFC], GetNextDoc
- CDocTemplate [MFC], InitialUpdateFrame
- CDocTemplate [MFC], LoadTemplate
- CDocTemplate [MFC], MatchDocType
- CDocTemplate [MFC], OpenDocumentFile
- CDocTemplate [MFC], RemoveDocument
- CDocTemplate [MFC], SaveAllModified
- CDocTemplate [MFC], SetContainerInfo
- CDocTemplate [MFC], SetDefaultTitle
- CDocTemplate [MFC], SetPreviewInfo
- CDocTemplate [MFC], SetServerInfo
ms.assetid: 14b41a1f-bf9d-4eac-b6a8-4c54ffcc77f6
ms.openlocfilehash: e97e2d00f5ad847555ae951433c327cc861917b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184889"
---
# <a name="cdoctemplate-class"></a>CDocTemplate 类

定义文档模板基本功能的抽象基类。

## <a name="syntax"></a>语法

```
class CDocTemplate : public CCmdTarget
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CDocTemplate：： CDocTemplate](#cdoctemplate)|构造 `CDocTemplate` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDocTemplate：： AddDocument](#adddocument)|将文档添加到模板。|
|[CDocTemplate：： CloseAllDocuments](#closealldocuments)|关闭与此模板关联的所有文档。|
|[CDocTemplate：： CreateNewDocument](#createnewdocument)|创建新文档。|
|[CDocTemplate：： CreateNewFrame](#createnewframe)|创建新的框架窗口，其中包含文档和视图。|
|[CDocTemplate：： CreateOleFrame](#createoleframe)|创建启用 OLE 的框架窗口。|
|[CDocTemplate：： CreatePreviewFrame](#createpreviewframe)|创建用于丰富预览的子框架。|
|[CDocTemplate：： GetDocString](#getdocstring)|检索与文档类型关联的字符串。|
|[CDocTemplate：： GetFirstDocPosition](#getfirstdocposition)|检索与此模板关联的第一个文档的位置。|
|[CDocTemplate：： GetNextDoc](#getnextdoc)|检索文档和下一个文档的位置。|
|[CDocTemplate：： InitialUpdateFrame](#initialupdateframe)|初始化框架窗口，并选择性地使其可见。|
|[CDocTemplate：： LoadTemplate](#loadtemplate)|加载给定 `CDocTemplate` 类或派生类的资源。|
|[CDocTemplate：： MatchDocType](#matchdoctype)|确定文档类型与此模板之间的匹配程度。|
|[CDocTemplate：： OpenDocumentFile](#opendocumentfile)|打开由路径名指定的文件。|
|[CDocTemplate：： RemoveDocument](#removedocument)|从模板中删除文档。|
|[CDocTemplate：： SaveAllModified](#saveallmodified)|保存与此模板关联的所有已修改的文档。|
|[CDocTemplate：： SetContainerInfo](#setcontainerinfo)|确定编辑就地 OLE 项时 OLE 容器的资源。|
|[CDocTemplate：： SetDefaultTitle](#setdefaulttitle)|显示文档窗口标题栏中的默认标题。|
|[CDocTemplate：： SetPreviewInfo](#setpreviewinfo)|从进程预览处理程序中进行的设置。|
|[CDocTemplate：： SetServerInfo](#setserverinfo)|确定在就地嵌入或编辑服务器文档时的资源和类。|

## <a name="remarks"></a>备注

通常会在实现应用程序的函数时创建一个或多个文档模板 `InitInstance` 。 文档模板定义了三种类型的类之间的关系：

- 一个派生自的文档类 `CDocument` 。

- 视图类，用于显示上面列出的文档类中的数据。 可以从 `CView` 、、或派生此 `CScrollView` 类 `CFormView` `CEditView` 。  (你也可以 `CEditView` 直接使用。 ) 

- 包含视图的框架窗口类。 对于 (SDI) 应用程序的单文档界面，从派生此类 `CFrameWnd` 。 对于多文档界面 (MDI) 应用程序中，从派生此类 `CMDIChildWnd` 。 如果不需要自定义框架窗口的行为，则可以使用 `CFrameWnd` 或 `CMDIChildWnd` 直接使用而无需派生你自己的类。

应用程序为其支持的每种类型的文档提供一个文档模板。 例如，如果您的应用程序同时支持电子表格和文本文档，则该应用程序有两个文档模板对象。 每个文档模板负责创建和管理其类型的所有文档。

文档模板存储指向 `CRuntimeClass` 文档、视图和框架窗口类的对象的指针。 这些 `CRuntimeClass` 对象是在构造文档模板时指定的。

文档模板包含用于文档类型的资源的 ID (例如菜单、图标或快捷键对应表资源) 。 文档模板还包含包含有关文档类型的其他信息的字符串。 其中包括文档类型的名称 (例如，"工作表" ) 和文件扩展名 (例如 ".xls" ) 。 此外，它还可以包含应用程序的用户界面、Windows 文件管理器以及对象链接和嵌入 (OLE) 支持所使用的其他字符串。

如果你的应用程序是 OLE 容器和/或服务器，则文档模板还会定义就地激活过程中使用的菜单的 ID。 如果你的应用程序是 OLE 服务器，文档模板会定义在就地激活过程中使用的工具栏和菜单的 ID。 可以通过调用和来指定这些其他 OLE 资源 `SetContainerInfo` `SetServerInfo` 。

由于 `CDocTemplate` 是抽象类，因此不能直接使用该类。 典型的应用程序使用 Microsoft 基础类库所提供的两个 `CDocTemplate` 派生类之一： `CSingleDocTemplate` ，实现 SDI，并 `CMultiDocTemplate` 实现 MDI。 有关使用文档模板的详细信息，请参阅这些类。

如果你的应用程序需要与 SDI 或 MDI 本质上不同的用户界面模式，则可以从派生你自己的类 `CDocTemplate` 。

有关的详细信息 `CDocTemplate` ，请参阅 [文档模板和文档/视图创建过程](../../mfc/document-templates-and-the-document-view-creation-process.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocTemplate`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cdoctemplateadddocument"></a><a name="adddocument"></a> CDocTemplate：： AddDocument

使用此函数可将文档添加到模板。

```
virtual void AddDocument(CDocument* pDoc);
```

### <a name="parameters"></a>parameters

*pDoc*<br/>
指向要添加的文档的指针。

### <a name="remarks"></a>备注

派生类 [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) 和 [CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) 将重写此函数。 如果从派生您自己的文档模板类 `CDocTemplate` ，则派生类必须重写此函数。

## <a name="cdoctemplatecdoctemplate"></a><a name="cdoctemplate"></a> CDocTemplate：： CDocTemplate

构造 `CDocTemplate` 对象。

```
CDocTemplate (
    UINT nIDResource,
    CRuntimeClass* pDocClass,
    CRuntimeClass* pFrameClass,
    CRuntimeClass* pViewClass);
```

### <a name="parameters"></a>parameters

*nIDResource*<br/>
指定用于文档类型的资源的 ID。 这可能包括菜单、图标、快捷键对应表和字符串资源。

String 资源包含由 "\n" 字符分隔的最多七个子字符串 (如果不包含子字符串，则需要使用 "\n" 字符作为占位符：但是，不需要后缀 "\n" 字符) ;这些子字符串说明了文档类型。 有关子字符串的信息，请参阅 [GetDocString](#getdocstring)。 此字符串资源位于应用程序的资源文件中。 例如：

```RC
// MYCALC.RC
STRINGTABLE PRELOAD DISCARDABLE
BEGIN
  IDR_SHEETTYPE "\nSheet\nWorksheet\nWorksheets (*.myc)\n.myc\n MyCalcSheet\nMyCalc Worksheet"
END
```

请注意，字符串以 "\n" 字符开头;这是因为第一个子字符串不用于 MDI 应用程序，因此不包括在内。 您可以使用字符串编辑器来编辑此字符串;整个字符串在字符串编辑器中显示为一个条目，而不是作为7个单独的条目。

*pDocClass*<br/>
指向 `CRuntimeClass` document 类的对象。 此类是一个 `CDocument` 派生类，可以定义它来表示文档。

*pFrameClass*<br/>
指向 `CRuntimeClass` 框架窗口类的对象。 此类可以是 `CFrameWnd` 派生类，也可以是其自身（ `CFrameWnd` 如果你希望在主框架窗口中使用默认行为）。

*pViewClass*<br/>
指向 `CRuntimeClass` 视图类的对象。 此类是一个 `CView` 派生类，可以定义它以显示文档。

### <a name="remarks"></a>备注

使用此成员函数构造 `CDocTemplate` 对象。 动态分配一个 `CDocTemplate` 对象，并将其从应用程序类的成员函数传递到 [CWinApp：： AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) `InitInstance` 。

## <a name="cdoctemplateclosealldocuments"></a><a name="closealldocuments"></a> CDocTemplate：： CloseAllDocuments

调用此成员函数以关闭所有打开的文档。

```
virtual void CloseAllDocuments(BOOL bEndSession);
```

### <a name="parameters"></a>parameters

*bEndSession*<br/>
未使用。

### <a name="remarks"></a>备注

此成员函数通常用作 File Exit 命令的一部分。 此函数的默认实现调用 [CDocument：:D eletecontents](../../mfc/reference/cdocument-class.md#deletecontents) 成员函数删除文档的数据，然后关闭附加到该文档的所有视图的框架窗口。

如果希望在关闭文档之前要求用户执行特殊的清理处理，请重写此函数。 例如，如果文档表示数据库中的记录，则可能需要重写此函数以关闭数据库。

## <a name="cdoctemplatecreatenewdocument"></a><a name="createnewdocument"></a> CDocTemplate：： CreateNewDocument

调用此成员函数以创建与此文档模板关联的类型的新文档。

```
virtual CDocument* CreateNewDocument();
```

### <a name="return-value"></a>返回值

指向新创建的文档的指针; 如果发生错误，则为 NULL。

## <a name="cdoctemplatecreatenewframe"></a><a name="createnewframe"></a> CDocTemplate：： CreateNewFrame

创建新的框架窗口，其中包含文档和视图。

```
virtual CFrameWnd* CreateNewFrame(
    CDocument* pDoc,
    CFrameWnd* pOther);
```

### <a name="parameters"></a>parameters

*pDoc*<br/>
新框架窗口应引用的文档。 可以为 NULL。

*pOther*<br/>
新框架窗口要基于的框架窗口。 可以为 NULL。

### <a name="return-value"></a>返回值

指向新创建的框架窗口的指针; 如果发生错误，则为 NULL。

### <a name="remarks"></a>备注

`CreateNewFrame` 使用 `CRuntimeClass` 传递给构造函数的对象创建新的框架窗口，并附加视图和文档。 如果 *pDoc* 参数为 NULL，则框架将输出跟踪消息。

*POther* 参数用于实现 Window New 命令。 它提供了一个框架窗口，用于对新框架窗口进行建模。 新框架窗口通常创建为不可见。 调用此函数可在文件新建和文件打开的标准框架实现之外创建框架窗口。

## <a name="cdoctemplatecreateoleframe"></a><a name="createoleframe"></a> CDocTemplate：： CreateOleFrame

创建 OLE 框架窗口。

```
CFrameWnd* CreateOleFrame(
    CWnd* pParentWnd,
    CDocument* pDoc,
    BOOL bCreateView);
```

### <a name="parameters"></a>parameters

*pParentWnd*<br/>
指向框架的父窗口的指针。

*pDoc*<br/>
指向新的 OLE 框架窗口应引用的文档的指针。

*bCreateView*<br/>
确定与框架一起创建的视图。

### <a name="return-value"></a>返回值

如果成功，则为指向帧窗口的指针;否则为 NULL。

### <a name="remarks"></a>备注

如果 *bCreateView* 为零，则将创建一个空的帧。

## <a name="cdoctemplategetdocstring"></a><a name="getdocstring"></a> CDocTemplate：： GetDocString

检索与文档类型关联的字符串。

```
virtual BOOL GetDocString(
    CString& rString,
    enum DocStringIndex index) const;
```

### <a name="parameters"></a>parameters

*rString*<br/>
对在 `CString` 函数返回时将包含字符串的对象的引用。

*索引*<br/>
从描述文档类型的字符串中检索的子字符串的索引。 此参数可以具有下列值之一：

- `CDocTemplate::windowTitle` 显示在应用程序窗口的标题栏中的名称 (例如 "Microsoft Excel" ) 。 仅存在于 SDI 应用程序的文档模板中。

- `CDocTemplate::docName` 默认文档名称的根 (例如，"Sheet" ) 。 当用户从 "文件" 菜单中选择新命令时，此根和一个数字将用于此类型的新文档的默认名称 (例如，"Sheet1" 或 "Sheet2" ) 。 如果未指定，则使用 "无标题" 作为默认值。

- `CDocTemplate::fileNewName` 此文档类型的名称。 如果应用程序支持多种类型的文档，则此字符串显示在 "文件新建" 对话框中 (例如，"工作表" ) 。 如果未指定，则使用 "新建文件" 命令无法访问文档类型。

- `CDocTemplate::filterName` 文档类型的说明和匹配此类型的文档的通配符筛选器。 此字符串显示在 "文件打开" 对话框中的 "列表文件类型" 下拉列表中 (例如，"工作表 ( * .xls) " ) 。 如果未指定，则使用 "文件打开" 命令无法访问文档类型。

- `CDocTemplate::filterExt` 此类型的文档的扩展 (例如，".xls" ) 。 如果未指定，则使用 "文件打开" 命令无法访问文档类型。

- `CDocTemplate::regFileTypeId` 要存储在 Windows 维护的注册数据库中的文档类型的标识符。 此字符串仅供内部使用 (例如，"ExcelWorksheet" ) 。 如果未指定，则不能向 Windows 文件管理器注册文档类型。

- `CDocTemplate::regFileTypeName` 要存储在注册数据库中的文档类型的名称。 此字符串可能会显示在访问注册数据库的应用程序的对话框中 (例如，"Microsoft Excel 工作表" ) 。

### <a name="return-value"></a>返回值

如果找到指定的子字符串，则为非零值;否则为0。

### <a name="remarks"></a>备注

调用此函数可检索描述文档类型的特定子字符串。 包含这些子字符串的字符串存储在文档模板中，并从应用程序的资源文件中的字符串派生。 框架调用此函数以获取应用程序的用户界面所需的字符串。 如果已指定应用程序文档的文件扩展名，则该框架还会在向 Windows 注册数据库添加条目时调用此函数;这样，便可以从 Windows 文件管理器打开文档。

仅当从派生您自己的类时，才调用此函数 `CDocTemplate` 。

## <a name="cdoctemplategetfirstdocposition"></a><a name="getfirstdocposition"></a> CDocTemplate：： GetFirstDocPosition

检索与此模板关联的第一个文档的位置。

```
virtual POSITION GetFirstDocPosition() const = 0;
```

### <a name="return-value"></a>返回值

一个位置值，可用于循环访问与此文档模板关联的文档的列表;如果列表为空，则为 NULL。

### <a name="remarks"></a>备注

使用此函数可获取与此模板关联的文档列表中第一个文档的位置。 使用位置值作为 [CDocTemplate：： GetNextDoc](#getnextdoc) 的参数来循环访问与模板关联的文档的列表。

[CSingleDocTemplate](../../mfc/reference/csingledoctemplate-class.md) 和 [CMultiDocTemplate](../../mfc/reference/cmultidoctemplate-class.md) 都覆盖此纯虚函数。 派生自的任何类 `CDocTemplate` 还必须重写此函数。

## <a name="cdoctemplategetnextdoc"></a><a name="getnextdoc"></a> CDocTemplate：： GetNextDoc

检索由 *rpo* 标识的列表元素，然后将 " *rpo* " 设置为列表中下一项的 "位置" 值。

```
virtual CDocument* GetNextDoc(POSITION& rPos) const = 0;
```

### <a name="return-value"></a>返回值

指向与此模板关联的文档列表中的下一个文档的指针。

### <a name="parameters"></a>parameters

*恢复*<br/>
对对 [GetFirstDocPosition](#getfirstdocposition) 或的先前调用所返回的位置值的引用 `GetNextDoc` 。

### <a name="remarks"></a>备注

如果检索到的元素是列表中的最后一个，则 " *rpo* " 的新值将设置为 NULL。

`GetNextDoc`如果使用对[GetFirstDocPosition](#getfirstdocposition)的调用建立初始位置，则可以在向前迭代循环中使用。

您必须确保您的位置值表示列表中的有效位置。 如果无效，则 Microsoft 基础类库断言的调试版本。

## <a name="cdoctemplateinitialupdateframe"></a><a name="initialupdateframe"></a> CDocTemplate：： InitialUpdateFrame

初始化框架窗口，并选择性地使其可见。

```
virtual void InitialUpdateFrame(
    CFrameWnd* pFrame,
    CDocument* pDoc,
    BOOL bMakeVisible = TRUE);
```

### <a name="parameters"></a>parameters

*pFrame*<br/>
需要初始更新的框架窗口。

*pDoc*<br/>
该帧关联到的文档。 可以为 NULL。

*bMakeVisible*<br/>
指示帧是否应变为可见并处于活动状态。

### <a name="remarks"></a>备注

`IntitialUpdateFrame`使用创建新帧后调用 `CreateNewFrame` 。 调用此函数会导致该框架窗口中的视图接收 `OnInitialUpdate` 调用。 而且，如果以前没有活动的视图，框架窗口的主视图将变为活动状态;主视图是 AFX_IDW_PANE_FIRST 的子 ID 为的视图。 最后，如果 *bMakeVisible* 为非零，则使框架窗口可见。 如果 *bMakeVisible* 为零，则当前焦点和框架窗口的可见状态将保持不变。

使用框架的文件新和打开文件的实现时，不需要调用此函数。

## <a name="cdoctemplateloadtemplate"></a><a name="loadtemplate"></a> CDocTemplate：： LoadTemplate

加载给定 `CDocTemplate` 类或派生类的资源。

```
virtual void LoadTemplate();
```

### <a name="remarks"></a>备注

框架调用此成员函数以加载给定 `CDocTemplate` 或派生类的资源。 通常在构造过程中调用它，但在全局构造该模板时除外。 在这种情况下，对的调用 `LoadTemplate` 将延迟，直到调用 [CWinApp：： AddDocTemplate](../../mfc/reference/cwinapp-class.md#adddoctemplate) 。

## <a name="cdoctemplatematchdoctype"></a><a name="matchdoctype"></a> CDocTemplate：： MatchDocType

确定文档类型与此模板之间的匹配程度。

```
virtual Confidence MatchDocType(
    LPCTSTR lpszPathName,
    CDocument*& rpDocMatch);
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
要确定其类型的文件的路径名。

*rpDocMatch*<br/>
如果 *lpszPathName* 指定的文件已打开，则为指向分配了匹配文档的文档的指针。

### <a name="return-value"></a>返回值

**置信度** 枚举中的一个值，定义如下：

```
enum Confidence
    {
    noAttempt,
    maybeAttemptForeign,
    maybeAttemptNative,
    yesAttemptForeign,
    yesAttemptNative,
    yesAlreadyOpen
    };
```

### <a name="remarks"></a>备注

使用此函数可确定用于打开文件的文档模板的类型。 例如，如果你的应用程序支持多个文件类型，则可以使用此函数来确定哪些可用的文档模板适用于给定文件，方法是 `MatchDocType` 依次对每个模板调用，并根据返回的置信度值选择模板。

如果 *lpszPathName* 指定的文件已打开，则此函数将返回 `CDocTemplate::yesAlreadyOpen` 文件的对象并将其复制 `CDocument` 到 *rpDocMatch* 中的对象。

如果文件未打开，但 *lpszPathName* 中的扩展与指定的扩展相匹配 `CDocTemplate::filterExt` ，则此函数将返回， `CDocTemplate::yesAttemptNative` 并将 *rpDocMatch* 设置为 NULL。 有关的详细信息 `CDocTemplate::filterExt` ，请参阅 [CDocTemplate：： GetDocString](#getdocstring)。

如果这两个事例均不为 true，则函数返回 `CDocTemplate::yesAttemptForeign` 。

默认实现不返回 `CDocTemplate::maybeAttemptForeign` 或 `CDocTemplate::maybeAttemptNative` 。 重写此函数以实现适用于你的应用程序的类型匹配逻辑，可能会从 **置信度** 枚举中使用这两个值。

## <a name="cdoctemplateopendocumentfile"></a><a name="opendocumentfile"></a> CDocTemplate：： OpenDocumentFile

打开路径指定的文件。

```
virtual CDocument* OpenDocumentFile(LPCTSTR lpszPathName) = 0;

virtual CDocument* OpenDocumentFile(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU) = 0;
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
中一个指针，指向包含要打开的文档的文件的路径。

*bAddToMRU*<br/>
中如果为 TRUE，则表示文档是最新的文件之一;FALSE 表示文档不是最新的文件之一。

### <a name="return-value"></a>返回值

指向其文件由 *lpszPathName* 命名的文档的指针;如果不成功，则为 NULL。

### <a name="remarks"></a>备注

打开 *lpszPathName* 指定其路径的文件。 如果 *lpszPathName* 为 NULL，则将创建一个新文件，其中包含与此模板关联的类型的文档。

## <a name="cdoctemplateremovedocument"></a><a name="removedocument"></a> CDocTemplate：： RemoveDocument

从与此模板关联的文档的列表中删除 *pDoc* 指向的文档。

```
virtual void RemoveDocument(CDocument* pDoc);
```

### <a name="parameters"></a>parameters

*pDoc*<br/>
指向要删除的文档的指针。

### <a name="remarks"></a>备注

派生类 `CMultiDocTemplate` ，并重 `CSingleDocTemplate` 写此函数。 如果从派生您自己的文档模板类 `CDocTemplate` ，则派生类必须重写此函数。

## <a name="cdoctemplatesaveallmodified"></a><a name="saveallmodified"></a> CDocTemplate：： SaveAllModified

保存所有已修改的文档。

```
virtual BOOL SaveAllModified();
```

### <a name="return-value"></a>返回值

如果成功，则为非零;否则为0。

## <a name="cdoctemplatesetcontainerinfo"></a><a name="setcontainerinfo"></a> CDocTemplate：： SetContainerInfo

确定编辑就地 OLE 项时 OLE 容器的资源。

```cpp
void SetContainerInfo(UINT nIDOleInPlaceContainer);
```

### <a name="parameters"></a>parameters

*nIDOleInPlaceContainer*<br/>
激活嵌入对象时使用的资源的 ID。

### <a name="remarks"></a>备注

调用此函数可设置 OLE 对象就地激活时要使用的资源。 这些资源可能包括菜单和快捷键对应表。 此函数通常在应用程序的 [CWinApp：： InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 函数中调用。

与 *nIDOleInPlaceContainer* 关联的菜单包含允许已激活的就地项菜单与容器应用程序的菜单合并的分隔符。 有关合并服务器和容器菜单的详细信息，请参阅文章 [ (OLE) 的菜单和资源 ](../../mfc/menus-and-resources-ole.md)。

## <a name="cdoctemplatesetdefaulttitle"></a><a name="setdefaulttitle"></a> CDocTemplate：： SetDefaultTitle

调用此函数可加载文档的默认标题，并将其显示在文档的标题栏中。

```
virtual void SetDefaultTitle(CDocument* pDocument) = 0;
```

### <a name="parameters"></a>parameters

*pDocument*<br/>
指向要设置其标题的文档的指针。

### <a name="remarks"></a>备注

有关默认标题的信息，请参阅 `CDocTemplate::docName` [CDocTemplate：： GetDocString](#getdocstring)中的说明。

## <a name="cdoctemplatesetserverinfo"></a><a name="setserverinfo"></a> CDocTemplate：： SetServerInfo

确定在就地嵌入或编辑服务器文档时的资源和类。

```cpp
void SetServerInfo(
    UINT nIDOleEmbedding,
    UINT nIDOleInPlaceServer = 0,
    CRuntimeClass* pOleFrameClass = NULL,
    CRuntimeClass* pOleViewClass = NULL);
```

### <a name="parameters"></a>parameters

*nIDOleEmbedding*<br/>
在单独的窗口中打开嵌入对象时使用的资源的 ID。

*nIDOleInPlaceServer*<br/>
就地激活嵌入对象时使用的资源的 ID。

*pOleFrameClass*<br/>
指向 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 结构的指针，该结构包含发生就地激活时创建的框架窗口对象的类信息。

*pOleViewClass*<br/>
指向一个结构的指针， `CRuntimeClass` 该结构包含在进行就地激活时创建的视图对象的类信息。

### <a name="remarks"></a>备注

调用此成员函数可标识在用户请求激活嵌入对象时服务器应用程序将使用的资源。 这些资源包括菜单和快捷键对应表。 此函数通常在应用程序的中调用 `InitInstance` 。

与 *nIDOleInPlaceServer* 关联的菜单包含允许服务器菜单与容器的菜单合并的分隔符。 有关合并服务器和容器菜单的详细信息，请参阅文章 [ (OLE) 的菜单和资源 ](../../mfc/menus-and-resources-ole.md)。

## <a name="cdoctemplatecreatepreviewframe"></a><a name="createpreviewframe"></a> CDocTemplate：： CreatePreviewFrame

创建用于丰富预览的子框架。

```
CFrameWnd* CreatePreviewFrame(
    CWnd* pParentWnd,
    CDocument* pDoc);
```

### <a name="parameters"></a>parameters

*pParentWnd*<br/>
指向父窗口的指针 (通常由 Shell) 提供。

*pDoc*<br/>
指向文档对象的指针，将在其中预览内容。

### <a name="return-value"></a>返回值

指向对象的有效指针 `CFrameWnd` ，如果创建失败，则为 NULL。

### <a name="remarks"></a>备注

## <a name="cdoctemplatesetpreviewinfo"></a><a name="setpreviewinfo"></a> CDocTemplate：： SetPreviewInfo

设置进程外预览处理程序。

```cpp
void SetPreviewInfo(
    UINT nIDPreviewFrame,
    CRuntimeClass* pPreviewFrameClass = NULL,
    CRuntimeClass* pPreviewViewClass = NULL);
```

### <a name="parameters"></a>parameters

*nIDPreviewFrame*<br/>
指定预览帧的资源 ID。

*pPreviewFrameClass*<br/>
指定指向预览框架的运行时类信息结构的指针。

*pPreviewViewClass*<br/>
指定指向预览视图的运行时类信息结构的指针。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CSingleDocTemplate 类](../../mfc/reference/csingledoctemplate-class.md)<br/>
[CMultiDocTemplate 类](../../mfc/reference/cmultidoctemplate-class.md)<br/>
[CDocument 类](../../mfc/reference/cdocument-class.md)<br/>
[CView 类](../../mfc/reference/cview-class.md)<br/>
[CScrollView 类](../../mfc/reference/cscrollview-class.md)<br/>
[CEditView 类](../../mfc/reference/ceditview-class.md)<br/>
[CFormView 类](../../mfc/reference/cformview-class.md)<br/>
[CFrameWnd 类](../../mfc/reference/cframewnd-class.md)<br/>
[CMDIChildWnd 类](../../mfc/reference/cmdichildwnd-class.md)

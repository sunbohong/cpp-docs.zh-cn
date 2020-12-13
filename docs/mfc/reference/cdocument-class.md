---
description: 了解详细信息： CDocument 类
title: CDocument 类
ms.date: 11/04/2016
f1_keywords:
- CDocument
- AFXWIN/CDocument
- AFXWIN/CDocument::CDocument
- AFXWIN/CDocument::AddView
- AFXWIN/CDocument::BeginReadChunks
- AFXWIN/CDocument::CanCloseFrame
- AFXWIN/CDocument::ClearChunkList
- AFXWIN/CDocument::ClearPathName
- AFXWIN/CDocument::DeleteContents
- AFXWIN/CDocument::FindChunk
- AFXWIN/CDocument::GetAdapter
- AFXWIN/CDocument::GetDocTemplate
- AFXWIN/CDocument::GetFile
- AFXWIN/CDocument::GetFirstViewPosition
- AFXWIN/CDocument::GetNextView
- AFXWIN/CDocument::GetPathName
- AFXWIN/CDocument::GetThumbnail
- AFXWIN/CDocument::GetTitle
- AFXWIN/CDocument::InitializeSearchContent
- AFXWIN/CDocument::IsModified
- AFXWIN/CDocument::IsSearchAndOrganizeHandler
- AFXWIN/CDocument::LoadDocumentFromStream
- AFXWIN/CDocument::OnBeforeRichPreviewFontChanged
- AFXWIN/CDocument::OnChangedViewList
- AFXWIN/CDocument::OnCloseDocument
- AFXWIN/CDocument::OnCreatePreviewFrame
- AFXWIN/CDocument::OnDocumentEvent
- AFXWIN/CDocument::OnDrawThumbnail
- AFXWIN/CDocument::OnLoadDocumentFromStream
- AFXWIN/CDocument::OnNewDocument
- AFXWIN/CDocument::OnOpenDocument
- AFXWIN/CDocument::OnPreviewHandlerQueryFocus
- AFXWIN/CDocument::OnPreviewHandlerTranslateAccelerator
- AFXWIN/CDocument::OnRichPreviewBackColorChanged
- AFXWIN/CDocument::OnRichPreviewFontChanged
- AFXWIN/CDocument::OnRichPreviewSiteChanged
- AFXWIN/CDocument::OnRichPreviewTextColorChanged
- AFXWIN/CDocument::OnSaveDocument
- AFXWIN/CDocument::OnUnloadHandler
- AFXWIN/CDocument::PreCloseFrame
- AFXWIN/CDocument::ReadNextChunkValue
- AFXWIN/CDocument::ReleaseFile
- AFXWIN/CDocument::RemoveChunk
- AFXWIN/CDocument::RemoveView
- AFXWIN/CDocument::ReportSaveLoadException
- AFXWIN/CDocument::SaveModified
- AFXWIN/CDocument::SetChunkValue
- AFXWIN/CDocument::SetModifiedFlag
- AFXWIN/CDocument::SetPathName
- AFXWIN/CDocument::SetTitle
- AFXWIN/CDocument::UpdateAllViews
- AFXWIN/CDocument::OnFileSendMail
- AFXWIN/CDocument::OnUpdateFileSendMail
- AFXWIN/CDocument::m_bGetThumbnailMode
- AFXWIN/CDocument::m_bPreviewHandlerMode
- AFXWIN/CDocument::m_bSearchMode
- AFXWIN/CDocument::m_clrRichPreviewBackColor
- AFXWIN/CDocument::m_clrRichPreviewTextColor
- AFXWIN/CDocument::m_lfRichPreviewFont
helpviewer_keywords:
- CDocument [MFC], CDocument
- CDocument [MFC], AddView
- CDocument [MFC], BeginReadChunks
- CDocument [MFC], CanCloseFrame
- CDocument [MFC], ClearChunkList
- CDocument [MFC], ClearPathName
- CDocument [MFC], DeleteContents
- CDocument [MFC], FindChunk
- CDocument [MFC], GetAdapter
- CDocument [MFC], GetDocTemplate
- CDocument [MFC], GetFile
- CDocument [MFC], GetFirstViewPosition
- CDocument [MFC], GetNextView
- CDocument [MFC], GetPathName
- CDocument [MFC], GetThumbnail
- CDocument [MFC], GetTitle
- CDocument [MFC], InitializeSearchContent
- CDocument [MFC], IsModified
- CDocument [MFC], IsSearchAndOrganizeHandler
- CDocument [MFC], LoadDocumentFromStream
- CDocument [MFC], OnBeforeRichPreviewFontChanged
- CDocument [MFC], OnChangedViewList
- CDocument [MFC], OnCloseDocument
- CDocument [MFC], OnCreatePreviewFrame
- CDocument [MFC], OnDocumentEvent
- CDocument [MFC], OnDrawThumbnail
- CDocument [MFC], OnLoadDocumentFromStream
- CDocument [MFC], OnNewDocument
- CDocument [MFC], OnOpenDocument
- CDocument [MFC], OnPreviewHandlerQueryFocus
- CDocument [MFC], OnPreviewHandlerTranslateAccelerator
- CDocument [MFC], OnRichPreviewBackColorChanged
- CDocument [MFC], OnRichPreviewFontChanged
- CDocument [MFC], OnRichPreviewSiteChanged
- CDocument [MFC], OnRichPreviewTextColorChanged
- CDocument [MFC], OnSaveDocument
- CDocument [MFC], OnUnloadHandler
- CDocument [MFC], PreCloseFrame
- CDocument [MFC], ReadNextChunkValue
- CDocument [MFC], ReleaseFile
- CDocument [MFC], RemoveChunk
- CDocument [MFC], RemoveView
- CDocument [MFC], ReportSaveLoadException
- CDocument [MFC], SaveModified
- CDocument [MFC], SetChunkValue
- CDocument [MFC], SetModifiedFlag
- CDocument [MFC], SetPathName
- CDocument [MFC], SetTitle
- CDocument [MFC], UpdateAllViews
- CDocument [MFC], OnFileSendMail
- CDocument [MFC], OnUpdateFileSendMail
- CDocument [MFC], m_bGetThumbnailMode
- CDocument [MFC], m_bPreviewHandlerMode
- CDocument [MFC], m_bSearchMode
- CDocument [MFC], m_clrRichPreviewBackColor
- CDocument [MFC], m_clrRichPreviewTextColor
- CDocument [MFC], m_lfRichPreviewFont
ms.assetid: e5a2891d-e1e1-4599-8c7e-afa9b4945446
ms.openlocfilehash: e821b82e849420fe82a7e40b7515bbb78e3284d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184798"
---
# <a name="cdocument-class"></a>CDocument 类

提供用户定义文档类的基本功能。

## <a name="syntax"></a>语法

```
class CDocument : public CCmdTarget
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDocument：： CDocument](#cdocument)|构造 `CDocument` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDocument：： AddView](#addview)|将视图附加到文档。|
|[CDocument：： BeginReadChunks](#beginreadchunks)|初始化区块读取。|
|[CDocument：： CanCloseFrame](#cancloseframe)|高级可重写;在关闭查看此文档的框架窗口之前调用。|
|[CDocument：： ClearChunkList](#clearchunklist)|清除区块列表。|
|[CDocument：： ClearPathName](#clearpathname)|清除文档对象的路径。|
|[CDocument：:D eleteContents](#deletecontents)|调用以执行文档清理。|
|[CDocument：： FindChunk](#findchunk)|查找具有指定 GUID 的区块。|
|[CDocument：： GetAdapter](#getadapter)|返回一个指向对象实现接口的指针 `IDocument` 。|
|[CDocument：： GetDocTemplate](#getdoctemplate)|返回指向说明文档类型的文档模板的指针。|
|[CDocument：： GetFile](#getfile)|返回一个指向所需对象的指针 `CFile` 。|
|[CDocument：： GetFirstViewPosition](#getfirstviewposition)|返回视图列表中第一个的位置;用于开始迭代。|
|[CDocument：： GetNextView](#getnextview)|循环访问与文档关联的视图列表。|
|[CDocument：： GetPathName](#getpathname)|返回文档的数据文件的路径。|
|[CDocument：： GetThumbnail](#getthumbnail)|调用以创建缩略图提供程序用来显示缩略图的位图。|
|[CDocument：： GetTitle](#gettitle)|返回文档的标题。|
|[CDocument：： InitializeSearchContent](#initializesearchcontent)|调用以初始化搜索处理程序的搜索内容。|
|[CDocument：： IsModified](#ismodified)|指示文档自上次保存后是否已被修改。|
|[CDocument：： IsSearchAndOrganizeHandler](#issearchandorganizehandler)|指示是否 `CDocument` 为搜索 & 组织处理程序创建了此对象实例。|
|[CDocument：： LoadDocumentFromStream](#loaddocumentfromstream)|调用以从流加载文档数据。|
|[CDocument：： OnBeforeRichPreviewFontChanged](#onbeforerichpreviewfontchanged)|在更改富预览字体前调用。|
|[CDocument：： OnChangedViewList](#onchangedviewlist)|在将视图添加到文档或将其从文档中移除后调用。|
|[CDocument：： OnCloseDocument](#onclosedocument)|调用以关闭文档。|
|[CDocument：： OnCreatePreviewFrame](#oncreatepreviewframe)|当需要创建丰富预览的预览帧时，由框架调用。|
|[CDocument：： OnDocumentEvent](#ondocumentevent)|由框架在响应文档事件时调用。|
|[CDocument：： OnDrawThumbnail](#ondrawthumbnail)|在派生类中重写此方法，以绘制缩略图的内容。|
|[CDocument：： OnLoadDocumentFromStream](#onloaddocumentfromstream)|当需要从流加载文档数据时，由框架调用。|
|[CDocument：： OnNewDocument](#onnewdocument)|调用以创建新文档。|
|[CDocument：： OnOpenDocument](#onopendocument)|调用以打开现有文档。|
|[CDocument：： OnPreviewHandlerQueryFocus](#onpreviewhandlerqueryfocus)|指示预览处理程序从调用 GetFocus 函数返回 HWND。|
|[CDocument：： OnPreviewHandlerTranslateAccelerator](#onpreviewhandlertranslateaccelerator)|指示预览处理程序处理从正在运行预览处理程序的进程的消息泵向上传递的击键。|
|[CDocument：： OnRichPreviewBackColorChanged](#onrichpreviewbackcolorchanged)|当丰富的预览背景色已更改时调用。|
|[CDocument：： OnRichPreviewFontChanged](#onrichpreviewfontchanged)|当丰富的预览字体已更改时调用。|
|[CDocument：： OnRichPreviewSiteChanged](#onrichpreviewsitechanged)|当丰富预览网站发生更改时调用。|
|[CDocument：： OnRichPreviewTextColorChanged](#onrichpreviewtextcolorchanged)|当丰富预览文本颜色已更改时调用。|
|[CDocument：： Onopendocument](#onsavedocument)|调用以将文档保存到磁盘。|
|[CDocument：： OnUnloadHandler](#onunloadhandler)|当正在卸载预览处理程序时由框架调用。|
|[CDocument：:P reCloseFrame](#precloseframe)|在框架窗口关闭前调用。|
|[CDocument：： ReadNextChunkValue](#readnextchunkvalue)|读取下一个块值。|
|[CDocument：： ReleaseFile](#releasefile)|释放文件以使其可供其他应用程序使用。|
|[CDocument：： RemoveChunk](#removechunk)|删除具有指定 GUID 的区块。|
|[CDocument：： RemoveView](#removeview)|将视图与文档分离。|
|[CDocument：： ReportSaveLoadException](#reportsaveloadexception)|高级可重写;当由于异常而无法完成打开或保存操作时调用。|
|[CDocument：： SaveModified](#savemodified)|高级可重写;调用以询问用户是否应保存文档。|
|[CDocument：： SetChunkValue](#setchunkvalue)|设置区块值。|
|[CDocument：： SetModifiedFlag](#setmodifiedflag)|设置一个标志，该标志指示自上次保存后已修改文档。|
|[CDocument：： SetPathName](#setpathname)|设置文档使用的数据文件的路径。|
|[CDocument：： SetTitle](#settitle)|设置文档的标题。|
|[CDocument：： UpdateAllViews](#updateallviews)|通知已修改文档的所有视图。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CDocument：： OnFileSendMail](#onfilesendmail)|发送附加了文档的邮件。|
|[CDocument：： OnUpdateFileSendMail](#onupdatefilesendmail)|启用 "发送邮件" 命令（如果存在邮件支持）。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CDocument：： m_bGetThumbnailMode](#m_bgetthumbnailmode)|指定 `CDocument` 对象是由 dllhost.exe 为缩略图创建的。 应签入 `CView::OnDraw` 。|
|[CDocument：： m_bPreviewHandlerMode](#m_bpreviewhandlermode)|指定 `CDocument` prevhost 为创建的对象 `Rich Preview` 。 应签入 `CView::OnDraw` 。|
|[CDocument：： m_bSearchMode](#m_bsearchmode)|指定 `CDocument` 对象是由索引器或其他搜索应用程序创建的。|
|[CDocument：： m_clrRichPreviewBackColor](#m_clrrichpreviewbackcolor)|指定富预览窗口的背景色。 此颜色由主机设置。|
|[CDocument：： m_clrRichPreviewTextColor](#m_clrrichpreviewtextcolor)|指定富预览窗口的前景色。 此颜色由主机设置。|
|[CDocument：： m_lfRichPreviewFont](#m_lfrichpreviewfont)|指定富预览窗口的文本字体。 此字体信息由主机设置。|

## <a name="remarks"></a>备注

文档表示用户通常使用 "打开文件" 命令打开的数据单元，并使用 "文件保存" 命令保存。

`CDocument` 支持标准操作，例如创建、加载和保存文档。 框架使用定义的接口操作文档 `CDocument` 。

应用程序可以支持多种类型的文档;例如，应用程序可能支持电子表格和文本文档。 每种类型的文档都有一个关联的文档模板;文档模板指定 (的资源（例如菜单、图标或快捷键对应表) 用于该类型的文档）。 每个文档都包含一个指向其关联对象的指针 `CDocTemplate` 。

用户通过 [CView](../../mfc/reference/cview-class.md) 对象与文档进行交互， (s) 与其关联。 视图在框架窗口中呈现文档的图像，并将用户输入解释为文档上的操作。 一个文档可以有多个与之关联的视图。 当用户打开文档上的窗口时，框架会创建一个视图并将其附加到文档。 文档模板指定用于显示每种文档类型的视图和框架窗口的类型。

文档是框架的标准命令路由的一部分，因此从标准用户界面组件接收命令 (如 "文件保存" 菜单项) 。 文档接收活动视图转发的命令。 如果文档未处理给定的命令，则会将命令转发到管理它的文档模板。

修改文档的数据时，其每个视图都必须反映这些修改。 `CDocument` 提供 [UpdateAllViews](#updateallviews) 成员函数以便通知此类更改的视图，以便这些视图可以在必要时重新绘制自身。 框架还会提示用户先保存修改后的文件，然后再将其关闭。

若要在典型的应用程序中实现文档，您必须执行以下操作：

- `CDocument`为每种类型的文档从派生一个类。

- 添加成员变量以存储每个文档的数据。

- 实现成员函数以读取和修改文档的数据。 文档视图是这些成员函数中最重要的用户。

- 在 document 类中重写 [CObject：：串行化](../../mfc/reference/cobject-class.md#serialize) 成员函数，以在磁盘中写入和读取文档的数据。

`CDocument` 如果邮件支持 (MAPI) 存在，则支持通过邮件发送文档。 请参阅文章 MFC 中的 [mapi](../../mfc/mapi.md) 和 [mapi 支持](../../mfc/mapi-support-in-mfc.md)。

有关的详细信息 `CDocument` ，请参阅 [序列化](../../mfc/serialization-in-mfc.md)、 [文档/视图体系结构主题](../../mfc/document-view-architecture.md)和 [文档/视图创建](../../mfc/document-view-creation.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDocument`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cdocumentaddview"></a><a name="addview"></a> CDocument：： AddView

调用此函数可将视图附加到文档。

```cpp
void AddView(CView* pView);
```

### <a name="parameters"></a>parameters

*pView*<br/>
指向正在添加的视图。

### <a name="remarks"></a>备注

此函数将指定的视图添加到文档关联的视图列表中;函数还将视图的文档指针设置为此文档。 将新创建的视图对象附加到文档时，框架会调用此函数;这会在响应文件新建、文件打开或新建窗口命令或拆分拆分窗口时出现。

只有在手动创建并附加视图时，才调用此函数。 通常情况下，通过定义 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 对象来关联文档类、视图类和框架窗口类，使框架连接文档和视图。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocViewSDI#12](../../mfc/codesnippet/cpp/cdocument-class_1.cpp)]

## <a name="cdocumentbeginreadchunks"></a><a name="beginreadchunks"></a> CDocument：： BeginReadChunks

初始化区块读取。

```
virtual void BeginReadChunks ();
```

### <a name="remarks"></a>备注

## <a name="cdocumentcancloseframe"></a><a name="cancloseframe"></a> CDocument：： CanCloseFrame

在关闭显示文档的框架窗口之前由框架调用。

```
virtual BOOL CanCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>parameters

*pFrame*<br/>
指向附加到文档的视图的框架窗口。

### <a name="return-value"></a>返回值

如果可以安全关闭框架窗口，则为非零值;否则为0。

### <a name="remarks"></a>备注

默认实现检查是否有其他框架窗口显示文档。 如果指定的框架窗口是显示文档的最后一个窗口，则函数会提示用户保存文档（如果文档已修改）。 如果要在关闭框架窗口时执行特殊处理，请重写此函数。 这是一种高级的可重写。

## <a name="cdocumentcdocument"></a><a name="cdocument"></a> CDocument：： CDocument

构造 `CDocument` 对象。

```
CDocument();
```

### <a name="remarks"></a>备注

框架将为您处理文档创建。 重写 [OnNewDocument](#onnewdocument) 成员函数，以便基于每个文档执行初始化;这在 (SDI) 应用程序的单文档界面中尤其重要。

## <a name="cdocumentclearchunklist"></a><a name="clearchunklist"></a> CDocument：： ClearChunkList

清除区块列表。

```
virtual void ClearChunkList ();
```

### <a name="remarks"></a>备注

## <a name="cdocumentclearpathname"></a><a name="clearpathname"></a> CDocument：： ClearPathName

清除文档对象的路径。

```
virtual void ClearPathName();
```

### <a name="remarks"></a>备注

清除对象的路径将 `CDocument` 导致应用程序在下一次保存文档时提示用户。 这使得 **save** 命令的行为类似于 " **另存为** " 命令。

## <a name="cdocumentdeletecontents"></a><a name="deletecontents"></a> CDocument：:D eleteContents

由框架调用以删除文档的数据，而不销毁 `CDocument` 对象本身。

```
virtual void DeleteContents();
```

### <a name="remarks"></a>备注

它在文档被销毁之前被调用。 它还称为，以确保文档在重复使用之前为空。 这对于只使用一个文档的 SDI 应用程序尤为重要;每当用户创建或打开其他文档时，就会重复使用该文档。 调用此函数可实现 "全部清除" 或类似的命令，该命令可删除文档的所有数据。 此函数的默认实现不执行任何操作。 重写此函数可删除文档中的数据。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#57](../../mfc/codesnippet/cpp/cdocument-class_2.cpp)]

## <a name="cdocumentfindchunk"></a><a name="findchunk"></a> CDocument：： FindChunk

查找具有指定 GUID 的块区。

```
virtual POSITION FindChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>parameters

*guid*<br/>
指定要查找的区块的 GUID。

pid<br/>
指定要查找的块区的 PID。

### <a name="return-value"></a>返回值

如果成功，则为内部块区列表中的位置。 否则为 NULL。

### <a name="remarks"></a>备注

## <a name="cdocumentgetadapter"></a><a name="getadapter"></a> CDocument：： GetAdapter

返回一个指向实现接口的对象的指针 `IDocument` 。

```
virtual ATL::IDocument* GetAdapter();
```

### <a name="return-value"></a>返回值

指向实现接口的对象的指针 `IDocument` 。

### <a name="remarks"></a>备注

## <a name="cdocumentgetdoctemplate"></a><a name="getdoctemplate"></a> CDocument：： GetDocTemplate

调用此函数可获取指向此文档类型的文档模板的指针。

```
CDocTemplate* GetDocTemplate() const;
```

### <a name="return-value"></a>返回值

指向此文档类型的文档模板的指针; 如果文档不由文档模板管理，则为 NULL。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#58](../../mfc/codesnippet/cpp/cdocument-class_3.cpp)]

## <a name="cdocumentgetfile"></a><a name="getfile"></a> CDocument：： GetFile

调用此成员函数以获取指向对象的指针 `CFile` 。

```
virtual CFile* GetFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CFileException* pError);
```

### <a name="parameters"></a>parameters

*lpszFileName*<br/>
作为所需文件的路径的字符串。 路径可以是相对路径或绝对路径。

*pError*<br/>
指向现有文件异常对象的指针，该对象指示操作的完成状态。

*nOpenFlags*<br/>
共享和访问模式。 指定打开文件时要执行的操作。 您可以使用按位 OR ( # A0) 运算符组合 CFile 构造函数 [CFile：： CFile](../../mfc/reference/cfile-class.md#cfile) 中列出的选项。 需要一个访问权限和一个共享选项; `modeCreate` 和 `modeNoInherit` 模式是可选的。

### <a name="return-value"></a>返回值

一个指向 `CFile` 对象的指针。

## <a name="cdocumentgetfirstviewposition"></a><a name="getfirstviewposition"></a> CDocument：： GetFirstViewPosition

调用此函数可获取与文档关联的视图列表中第一个视图的位置。

```
virtual POSITION GetFirstViewPosition() const;
```

### <a name="return-value"></a>返回值

可用于通过 [GetNextView](#getnextview) 成员函数进行迭代的位置值。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetnextview"></a><a name="getnextview"></a> CDocument：： GetNextView

调用此函数可循环访问文档的所有视图。

```
virtual CView* GetNextView(POSITION& rPosition) const;
```

### <a name="parameters"></a>parameters

*rPosition*<br/>
对通过前一次调用 `GetNextView` 或 [GetFirstViewPosition](#getfirstviewposition) 成员函数返回的位置值的引用。 此值不得为 NULL。

### <a name="return-value"></a>返回值

指向由 *rPosition* 标识的视图的指针。

### <a name="remarks"></a>备注

函数返回由 *rPosition* 标识的视图，然后将 *rPosition* 设置为列表中下一个视图的位置值。 如果检索的视图是列表中的最后一个，则将 *rPosition* 设置为 NULL。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#59](../../mfc/codesnippet/cpp/cdocument-class_4.cpp)]

## <a name="cdocumentgetpathname"></a><a name="getpathname"></a> CDocument：： GetPathName

调用此函数可获取文档的磁盘文件的完全限定路径。

```
const CString& GetPathName() const;
```

### <a name="return-value"></a>返回值

文档的完全限定路径。 如果文档尚未保存或没有与之关联的磁盘文件，则此字符串为空。

## <a name="cdocumentgetthumbnail"></a><a name="getthumbnail"></a> CDocument：： GetThumbnail

创建缩略图提供程序用来显示缩略图的位图。

```
virtual BOOL GetThumbnail(
    UINT cx,
    HBITMAP* phbmp,
    DWORD* pdwAlpha);
```

### <a name="parameters"></a>parameters

*cx*<br/>
指定位图的宽度和高度。

*phbmp*<br/>
当函数成功返回时，包含位图的句柄。

*pdwAlpha*<br/>
当函数成功返回时，包含一个指定 alpha 通道值的 DWORD 值。

### <a name="return-value"></a>返回值

如果成功创建缩略图的位图，则返回 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cdocumentgettitle"></a><a name="gettitle"></a> CDocument：： GetTitle

调用此函数可获取文档的标题，该标题通常派生自文档的文件名。

```
const CString& GetTitle() const;
```

### <a name="return-value"></a>返回值

文档的标题。

## <a name="cdocumentinitializesearchcontent"></a><a name="initializesearchcontent"></a> CDocument：： InitializeSearchContent

调用以初始化搜索处理程序的搜索内容。

```
virtual void InitializeSearchContent ();
```

### <a name="remarks"></a>备注

在派生类中重写此方法以初始化搜索内容。 内容应为带有 ";" 分隔部分的字符串。 例如，"point;矩形ole 项 "。

## <a name="cdocumentismodified"></a><a name="ismodified"></a> CDocument：： IsModified

调用此函数可确定文档自上次保存后是否已被修改。

```
virtual BOOL IsModified();
```

### <a name="return-value"></a>返回值

如果文档自上次保存后已被修改，则为非零值;否则为0。

## <a name="cdocumentissearchandorganizehandler"></a><a name="issearchandorganizehandler"></a> CDocument：： IsSearchAndOrganizeHandler

指示是否 `CDocument` 为搜索 & 组织处理程序创建了此实例。

```
BOOL IsSearchAndOrganizeHandler() const;
```

### <a name="return-value"></a>返回值

如果为 `CDocument` 搜索 & 组织处理程序创建了的此实例，则返回 TRUE。

### <a name="remarks"></a>备注

目前，此函数仅对在进程外服务器中实现的丰富预览处理程序返回 TRUE。 可以在应用程序级别设置适当的标志 (m_bPreviewHandlerMode，m_bSearchMode m_bGetThumbnailMode) ，使此函数返回 TRUE。

## <a name="cdocumentloaddocumentfromstream"></a><a name="loaddocumentfromstream"></a> CDocument：： LoadDocumentFromStream

调用以从流加载文档数据。

```
virtual HRESULT LoadDocumentFromStream(
    IStream* pStream,
    DWORD dwGrfMode);
```

### <a name="parameters"></a>parameters

*pStream*<br/>
指向流的指针。 此流由 Shell 提供。

*dwGrfMode*<br/>
流的访问模式。

### <a name="return-value"></a>返回值

S_OK 如果加载操作成功，则为; 否则为 HRESULT，并返回错误代码。

### <a name="remarks"></a>备注

可以在派生类中重写此方法，以自定义如何从流中加载数据。

## <a name="cdocumentm_bgetthumbnailmode"></a><a name="m_bgetthumbnailmode"></a> CDocument：： m_bGetThumbnailMode

指定 `CDocument` 对象是由 dllhost.exe 为缩略图创建的。 应签入 `CView::OnDraw` 。

```
BOOL m_bGetThumbnailMode;
```

### <a name="remarks"></a>备注

`TRUE` 指示已由 dllhost.exe 为缩略图创建了文档。

## <a name="cdocumentm_bpreviewhandlermode"></a><a name="m_bpreviewhandlermode"></a> CDocument：： m_bPreviewHandlerMode

指定 `CDocument` 对象是由 prevhost 创建的，用于丰富的预览。 应签入 `CView::OnDraw` 。

```
BOOL m_bPreviewHandlerMode;
```

### <a name="remarks"></a>备注

如果为 TRUE，则表示文档是由 prevhost 创建的，用于丰富的预览。

## <a name="cdocumentm_bsearchmode"></a><a name="m_bsearchmode"></a> CDocument：： m_bSearchMode

指定 `CDocument` 对象由索引器或其他搜索应用程序创建。

```
BOOL m_bSearchMode;
```

### <a name="remarks"></a>备注

`TRUE` 指示文档由索引器或其他搜索应用程序创建。

## <a name="cdocumentm_clrrichpreviewbackcolor"></a><a name="m_clrrichpreviewbackcolor"></a> CDocument：： m_clrRichPreviewBackColor

指定富预览窗口的背景色。 此颜色由主机设置。

```
COLORREF m_clrRichPreviewBackColor;
```

### <a name="remarks"></a>备注

## <a name="cdocumentm_clrrichpreviewtextcolor"></a><a name="m_clrrichpreviewtextcolor"></a> CDocument：： m_clrRichPreviewTextColor

指定富预览窗口的前景色。 此颜色由主机设置。

```
COLORREF m_clrRichPreviewTextColor;
```

### <a name="remarks"></a>备注

## <a name="cdocumentm_lfrichpreviewfont"></a><a name="m_lfrichpreviewfont"></a> CDocument：： m_lfRichPreviewFont

指定富预览窗口的文本字体。 此字体信息由主机设置。

```
CFont m_lfRichPreviewFont;
```

### <a name="remarks"></a>备注

## <a name="cdocumentonbeforerichpreviewfontchanged"></a><a name="onbeforerichpreviewfontchanged"></a> CDocument：： OnBeforeRichPreviewFontChanged

在丰富预览字体更改之前调用。

```
virtual void OnBeforeRichPreviewFontChanged();
```

### <a name="remarks"></a>备注

## <a name="cdocumentonchangedviewlist"></a><a name="onchangedviewlist"></a> CDocument：： OnChangedViewList

在将视图添加到文档或从文档移除视图之后，由框架调用。

```
virtual void OnChangedViewList();
```

### <a name="remarks"></a>备注

此函数的默认实现将检查是否正在删除最后一个视图，如果是，则删除该文档。 如果要在框架添加或删除视图时执行特殊处理，请重写此函数。 例如，如果希望文档即使没有附加的视图也仍处于打开状态，则重写此函数。

## <a name="cdocumentonclosedocument"></a><a name="onclosedocument"></a> CDocument：： OnCloseDocument

当文档关闭时由框架调用，通常作为文件关闭命令的一部分。

```
virtual void OnCloseDocument();
```

### <a name="remarks"></a>备注

此函数的默认实现会销毁用于查看文档的所有框架，关闭视图，清除文档内容，然后调用 [DeleteContents](#deletecontents) 成员函数以删除文档的数据。

如果要在框架关闭文档时执行特殊的清理处理，请重写此函数。 例如，如果文档表示数据库中的记录，则可能需要重写此函数以关闭数据库。 应从重写中调用此函数的基类版本。

## <a name="cdocumentoncreatepreviewframe"></a><a name="oncreatepreviewframe"></a> CDocument：： OnCreatePreviewFrame

当需要创建丰富预览的预览帧时，由框架调用。

```
virtual BOOL OnCreatePreviewFrame();
```

### <a name="return-value"></a>返回值

如果成功创建帧，则返回 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

## <a name="cdocumentondocumentevent"></a><a name="ondocumentevent"></a> CDocument：： OnDocumentEvent

由框架在响应文档事件时调用。

```
virtual void OnDocumentEvent(DocumentEvent deEvent);
```

### <a name="parameters"></a>parameters

*deEvent*<br/>
中描述事件类型的枚举数据类型。

### <a name="remarks"></a>备注

文档事件可能会影响多个类。 此方法负责处理影响 [CDocument 类](../../mfc/reference/cdocument-class.md)之外的类的文档事件。 目前，必须响应文档事件的唯一类是 [CDataRecoveryHandler 类](../../mfc/reference/cdatarecoveryhandler-class.md)。 `CDocument`类具有其他可替代方法，这些方法负责处理对的影响 `CDocument` 。

下表列出了 *deEvent* 的可能值以及它们对应的事件。

|值|对应的事件|
|-----------|-------------------------|
|`onAfterNewDocument`|已创建新文档。|
|`onAfterOpenDocument`|新文档已打开。|
|`onAfterSaveDocument`|文档已保存。|
|`onAfterCloseDocument`|文档被关闭。|

## <a name="cdocumentondrawthumbnail"></a><a name="ondrawthumbnail"></a> CDocument：： OnDrawThumbnail

在派生类中重写此方法以绘制缩略图。

```
virtual void OnDrawThumbnail(
    CDC& dc,
    LPRECT lprcBounds);
```

### <a name="parameters"></a>parameters

*dc*<br/>
对设备上下文的引用。

*lprcBounds*<br/>
指定应在其中绘制缩略图的区域的边框。

### <a name="remarks"></a>备注

## <a name="cdocumentonfilesendmail"></a><a name="onfilesendmail"></a> CDocument：： OnFileSendMail

如果与文档的任何) 为附件，则通过居民邮件主机发送消息 (。

```cpp
void OnFileSendMail();
```

### <a name="remarks"></a>备注

`OnFileSendMail` 调用 ([onopendocument](#onsavedocument) 将) 无标题和已修改的文档保存到临时文件，然后通过电子邮件发送该文件。 如果未修改文档，则不需要临时文件;发送原始。 `OnFileSendMail` 加载 MAPI32.DLL （如果尚未加载）。

的的特殊实现 `OnFileSendMail` [COleDocument](../../mfc/reference/coledocument-class.md) 正确处理复合文件。

`CDocument` 如果邮件支持 (MAPI) 存在，则支持通过邮件发送文档。 请参阅文章 MFC 中的 [Mapi 主题](../../mfc/mapi.md) 和 [mapi 支持](../../mfc/mapi-support-in-mfc.md)。

## <a name="cdocumentonloaddocumentfromstream"></a><a name="onloaddocumentfromstream"></a> CDocument：： OnLoadDocumentFromStream

当需要从流加载文档数据时，由框架调用。

```
virtual HRESULT OnLoadDocumentFromStream(
    IStream* pStream,
    DWORD grfMode);
```

### <a name="parameters"></a>parameters

*pStream*<br/>
指向传入流的指针。

*grfMode*<br/>
流的访问模式。

### <a name="return-value"></a>返回值

如果加载成功，则 S_OK;否则为错误代码。

### <a name="remarks"></a>备注

## <a name="cdocumentonnewdocument"></a><a name="onnewdocument"></a> CDocument：： OnNewDocument

由框架作为 "新建文件" 命令的一部分调用。

```
virtual BOOL OnNewDocument();
```

### <a name="return-value"></a>返回值

如果文档已成功初始化，则为非零值;否则为0。

### <a name="remarks"></a>备注

此函数的默认实现将调用 [DeleteContents](#deletecontents) 成员函数，以确保文档为空，然后将新文档标记为干净。 重写此函数可以初始化新文档的数据结构。 应从重写中调用此函数的基类版本。

如果用户在 SDI 应用程序中选择 "文件" "新建" 命令，框架将使用此函数重新初始化现有文档，而不是创建一个新文档。 如果用户在多文档界面中选择 "文件" "新建" (MDI) 应用程序，则该框架每次都会创建一个新文档，然后调用此函数对其进行初始化。 您必须将您的初始化代码放在此函数中，而不是放置在用于在 SDI 应用程序中有效的 File New 命令的构造函数中。

请注意，在某些情况下， `OnNewDocument` 调用了两次。 当文档嵌入为 ActiveX 文档服务器时，会发生这种情况。 函数第一 `CreateInstance` 次由派生类 (公开的方法调用 `COleObjectFactory`) 并由 `InitNew` 派生类) 公开的方法 (第二次调用 `COleServerDoc` 。

### <a name="example"></a>示例

下面的示例演示了初始化文档对象的替代方法。

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

## <a name="cdocumentonopendocument"></a><a name="onopendocument"></a> CDocument：： OnOpenDocument

由框架作为 "文件打开" 命令的一部分调用。

```
virtual BOOL OnOpenDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
指向要打开的文档的路径。

### <a name="return-value"></a>返回值

如果成功加载文档，则为非零值;否则为0。

### <a name="remarks"></a>备注

此函数的默认实现将打开指定的文件，调用 [DeleteContents](#deletecontents) 成员函数以确保文档为空，调用 [CObject：：串行化](../../mfc/reference/cobject-class.md#serialize) 以读取文件的内容，然后将文档标记为干净。 如果要使用存档机制或文件机制以外的其他内容，请重写此函数。 例如，你可以编写一个应用程序，其中的文档表示数据库中的记录，而不是单独的文件。

如果用户在 SDI 应用程序中选择 "打开文件" 命令，框架将使用此函数重新初始化现有 `CDocument` 对象，而不是创建新对象。 如果用户在 MDI 应用程序中选择 "打开文件"，框架将每次构造一个新的 `CDocument` 对象，然后调用此函数对其进行初始化。 必须将初始化代码放在此函数中，而不是放在构造函数中，以便在 SDI 应用程序中有效地执行 "文件打开" 命令。

### <a name="example"></a>示例

下面的示例演示了初始化文档对象的替代方法。

[!code-cpp[NVC_MFCDocView#60](../../mfc/codesnippet/cpp/cdocument-class_5.cpp)]

[!code-cpp[NVC_MFCDocView#61](../../mfc/codesnippet/cpp/cdocument-class_6.cpp)]

[!code-cpp[NVC_MFCDocView#62](../../mfc/codesnippet/cpp/cdocument-class_7.cpp)]

[!code-cpp[NVC_MFCDocView#63](../../mfc/codesnippet/cpp/cdocument-class_8.cpp)]

## <a name="cdocumentonpreviewhandlerqueryfocus"></a><a name="onpreviewhandlerqueryfocus"></a> CDocument：： OnPreviewHandlerQueryFocus

指示预览处理程序返回通过调用函数检索到的 HWND `GetFocus` 。

```
virtual HRESULT OnPreviewHandlerQueryFocus(HWND* phwnd);
```

### <a name="parameters"></a>parameters

*phwnd*<br/>
弄此方法返回时，包含一个指向从 `GetFocus` 预览处理程序的前台线程调用函数返回的 HWND 的指针。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK;否则为错误值。

### <a name="remarks"></a>备注

## <a name="cdocumentonpreviewhandlertranslateaccelerator"></a><a name="onpreviewhandlertranslateaccelerator"></a> CDocument：： OnPreviewHandlerTranslateAccelerator

指示预览处理程序处理从正在运行预览处理程序的进程的消息泵向上传递的击键。

```
virtual HRESULT OnPreviewHandlerTranslateAccelerator(MSG* pmsg);
```

### <a name="parameters"></a>parameters

*pmsg*<br/>
中指向窗口消息的指针。

### <a name="return-value"></a>返回值

如果可以通过预览处理程序处理击键消息，则处理程序将处理该消息并返回 S_OK。 如果预览处理程序无法处理击键消息，它会通过将其提供给主机 `IPreviewHandlerFrame::TranslateAccelerator` 。 如果主机处理消息，则此方法返回 S_OK。 如果主机未处理消息，则此方法返回 S_FALSE。

### <a name="remarks"></a>备注

## <a name="cdocumentonrichpreviewbackcolorchanged"></a><a name="onrichpreviewbackcolorchanged"></a> CDocument：： OnRichPreviewBackColorChanged

当丰富的预览背景色已更改时调用。

```
virtual void OnRichPreviewBackColorChanged();
```

### <a name="remarks"></a>备注

## <a name="cdocumentonrichpreviewfontchanged"></a><a name="onrichpreviewfontchanged"></a> CDocument：： OnRichPreviewFontChanged

在丰富的预览字体已更改时调用。

```
virtual void OnRichPreviewFontChanged();
```

### <a name="remarks"></a>备注

## <a name="cdocumentonrichpreviewsitechanged"></a><a name="onrichpreviewsitechanged"></a> CDocument：： OnRichPreviewSiteChanged

在丰富预览网站发生更改时调用。

```
virtual void OnRichPreviewSiteChanged();
```

### <a name="remarks"></a>备注

## <a name="cdocumentonrichpreviewtextcolorchanged"></a><a name="onrichpreviewtextcolorchanged"></a> CDocument：： OnRichPreviewTextColorChanged

在丰富的预览文本颜色已更改时调用。

```
virtual void OnRichPreviewTextColorChanged();
```

### <a name="remarks"></a>备注

## <a name="cdocumentonsavedocument"></a><a name="onsavedocument"></a> CDocument：： Onopendocument

由框架作为 "文件保存" 或 "文件另存为" 命令的一部分调用。

```
virtual BOOL OnSaveDocument(LPCTSTR lpszPathName);
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
指向文件应保存到的完全限定路径。

### <a name="return-value"></a>返回值

如果成功保存文档，则为非零值;否则为0。

### <a name="remarks"></a>备注

此函数的默认实现将打开指定的文件，调用 [CObject：：串行化](../../mfc/reference/cobject-class.md#serialize) ，将文档的数据写入该文件，然后将该文档标记为干净。 如果要在框架保存文档时执行特殊处理，请重写此函数。 例如，你可以编写一个应用程序，其中的文档表示数据库中的记录，而不是单独的文件。

## <a name="cdocumentonunloadhandler"></a><a name="onunloadhandler"></a> CDocument：： OnUnloadHandler

在卸载预览处理程序时由框架调用。

```
virtual void OnUnloadHandler();
```

### <a name="remarks"></a>备注

## <a name="cdocumentonupdatefilesendmail"></a><a name="onupdatefilesendmail"></a> CDocument：： OnUpdateFileSendMail

如果存在邮件支持 (MAPI) ，则启用 ID_FILE_SEND_MAIL 命令。

```cpp
void OnUpdateFileSendMail(CCmdUI* pCmdUI);
```

### <a name="parameters"></a>parameters

*pCmdUI*<br/>
指向与 ID_FILE_SEND_MAIL 命令相关联的 [CCmdUI](../../mfc/reference/ccmdui-class.md) 对象的指针。

### <a name="remarks"></a>备注

否则，函数将从菜单中删除 ID_FILE_SEND_MAIL 命令，包括相应的菜单项上方或下方的分隔符。 如果 MAPI32.DLL 存在于路径中，且在 WIN.INI 文件的 [Mail] 部分中，则会启用 MAPI = 1。 大多数应用程序将此命令放在 "文件" 菜单上。

`CDocument` 如果邮件支持 (MAPI) 存在，则支持通过邮件发送文档。 请参阅文章 MFC 中的 [Mapi 主题](../../mfc/mapi.md) 和 [mapi 支持](../../mfc/mapi-support-in-mfc.md)。

## <a name="cdocumentprecloseframe"></a><a name="precloseframe"></a> CDocument：:P reCloseFrame

此成员函数在框架窗口销毁之前由框架调用。

```
virtual void PreCloseFrame(CFrameWnd* pFrame);
```

### <a name="parameters"></a>parameters

*pFrame*<br/>
指向保存关联对象的 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 的指针 `CDocument` 。

### <a name="remarks"></a>备注

可以重写此方法以提供自定义清理，但还要确保调用基类。

的默认值 `PreCloseFrame` 不执行任何操作 `CDocument` 。 `CDocument`派生类[COleDocument](../../mfc/reference/coledocument-class.md)和[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)使用此成员函数。

## <a name="cdocumentreadnextchunkvalue"></a><a name="readnextchunkvalue"></a> CDocument：： ReadNextChunkValue

读取下一个块区值。

```
virtual BOOL ReadNextChunkValue(IFilterChunkValue** ppValue);
```

### <a name="parameters"></a>parameters

*ppValue*<br/>
弄当函数返回时， *ppValue* 包含读取的值。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

## <a name="cdocumentreleasefile"></a><a name="releasefile"></a> CDocument：： ReleaseFile

框架调用此成员函数以释放文件，使其可供其他应用程序使用。

```
virtual void ReleaseFile(
    CFile* pFile,
    BOOL bAbort);
```

### <a name="parameters"></a>parameters

*.Pfile*<br/>
指向要释放的 CFile 对象的指针。

*bAbort*<br/>
指定是否使用或释放文件 `CFile::Close` `CFile::Abort` 。 如果使用 [CFile：： Close](../../mfc/reference/cfile-class.md#close)释放文件，则为 FALSE;如果使用 [CFile：： Abort](../../mfc/reference/cfile-class.md#abort)释放文件，则为 TRUE。

### <a name="remarks"></a>备注

如果 *bAbort* 为 TRUE，则 `ReleaseFile` 调用 `CFile::Abort` ，并释放文件。 `CFile::Abort` 不会引发异常。

如果 *bAbort* 为 FALSE， `ReleaseFile` `CFile::Close` 则调用并释放文件。

重写此成员函数以在文件发布之前要求用户执行操作。

## <a name="cdocumentremovechunk"></a><a name="removechunk"></a> CDocument：： RemoveChunk

删除具有指定 GUID 的块区。

```
virtual void RemoveChunk(
    REFCLSID guid,
    DWORD pid);
```

### <a name="parameters"></a>parameters

*Guid.empty*<br/>
指定要删除的区块的 GUID。

*P&id*<br/>
指定要删除的块区的 PID。

### <a name="remarks"></a>备注

## <a name="cdocumentremoveview"></a><a name="removeview"></a> CDocument：： RemoveView

调用此函数可从文档中分离视图。

```cpp
void RemoveView(CView* pView);
```

### <a name="parameters"></a>parameters

*pView*<br/>
指向要删除的视图。

### <a name="remarks"></a>备注

此函数从与文档关联的视图列表中删除指定的视图;它还将视图的文档指针设置为 NULL。 框架窗口关闭或拆分器窗口的窗格关闭时，框架会调用此函数。

仅当手动分离视图时才调用此函数。 通常情况下，通过定义 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md) 对象以关联文档类、视图类和框架窗口类，使框架分离文档和视图。

有关示例实现，请参阅 [AddView](#addview) 中的示例。

## <a name="cdocumentreportsaveloadexception"></a><a name="reportsaveloadexception"></a> CDocument：： ReportSaveLoadException

如果引发异常，则调用 (通常为 [CFileException](../../mfc/reference/cfileexception-class.md) 或 [CArchiveException](../../mfc/reference/carchiveexception-class.md)) 在保存或加载文档时。

```
virtual void ReportSaveLoadException(
    LPCTSTR lpszPathName,
    CException* e,
    BOOL bSaving,
    UINT nIDPDefault);
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
指向要保存或加载的文档的名称。

*e*<br/>
指向引发的异常。 可以为 NULL。

*bSaving*<br/>
指示正在进行的操作的标志;如果保存文档，则为非零值，如果正在加载文档，则为0。

*nIDPDefault*<br/>
如果函数未指定更具体的错误消息的标识符，则为要显示的错误消息的标识符。

### <a name="remarks"></a>备注

默认实现将检查异常对象，并查找具体描述原因的错误消息。 如果未找到特定消息或 *e* 为 NULL，则使用由 *nIDPDefault* 参数指定的常规消息。 然后，该函数会显示一个包含错误消息的消息框。 如果要提供其他自定义的失败消息，请重写此函数。 这是一种高级的可重写。

## <a name="cdocumentsavemodified"></a><a name="savemodified"></a> CDocument：： SaveModified

在修改后的文档被关闭之前由框架调用。

```
virtual BOOL SaveModified();
```

### <a name="return-value"></a>返回值

如果继续并关闭文档，则为非零值;如果文档不应关闭，则为0。

### <a name="remarks"></a>备注

此函数的默认实现将显示一个消息框，询问用户是否保存对文档所做的更改（如果已进行了更改）。 如果程序需要不同的提示过程，请重写此函数。 这是一种高级的可重写。

## <a name="cdocumentsetchunkvalue"></a><a name="setchunkvalue"></a> CDocument：： SetChunkValue

设置区块值。

```
virtual BOOL SetChunkValue (IFilterChunkValue* pValue);
```

### <a name="parameters"></a>parameters

*pValue*<br/>
指定要设置的区块值。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

## <a name="cdocumentsetmodifiedflag"></a><a name="setmodifiedflag"></a> CDocument：： SetModifiedFlag

对文档进行任何修改后，调用此函数。

```
virtual void SetModifiedFlag(BOOL bModified = TRUE);
```

### <a name="parameters"></a>parameters

*bModified*<br/>
指示文档是否已修改的标志。

### <a name="remarks"></a>备注

通过一致地调用此函数，可以确保框架在关闭文档之前提示用户保存更改。 通常，对于 *bModified* 参数，应使用默认值 TRUE。 若要将文档标记为 clean (未修改的) ，请使用值 FALSE 调用此函数。

## <a name="cdocumentsetpathname"></a><a name="setpathname"></a> CDocument：： SetPathName

调用此函数可指定文档的磁盘文件的完全限定路径。

```
virtual void SetPathName(
    LPCTSTR lpszPathName,
    BOOL bAddToMRU = TRUE);
```

### <a name="parameters"></a>parameters

*lpszPathName*<br/>
指向要用作文档路径的字符串。

*bAddToMRU*<br/>
确定是否将文件名添加到最近使用的 (MRU) 文件列表中。 如果为 TRUE，则添加文件名;如果为 FALSE，则不添加它。

### <a name="remarks"></a>备注

根据 *bAddToMRU* 的值，会将路径添加或不会添加到应用程序维护的 MRU 列表。 请注意，某些文档与磁盘文件无关。 仅当要重写用于打开和保存框架使用的文件的默认实现时，才调用此函数。

## <a name="cdocumentsettitle"></a><a name="settitle"></a> CDocument：： SetTitle

调用此函数可指定文档的标题 (框架窗口的标题栏中显示的字符串) 。

```
virtual void SetTitle(LPCTSTR lpszTitle);
```

### <a name="parameters"></a>parameters

*lpszTitle*<br/>
指向要用作文档标题的字符串。

### <a name="remarks"></a>备注

调用此函数将更新显示文档的所有框架窗口的标题。

## <a name="cdocumentupdateallviews"></a><a name="updateallviews"></a> CDocument：： UpdateAllViews

修改文档后调用此函数。

```cpp
void UpdateAllViews(
    CView* pSender,
    LPARAM lHint = 0L,
    CObject* pHint = NULL);
```

### <a name="parameters"></a>parameters

*pSender*<br/>
指向修改文档的视图，如果要更新所有视图，则为 NULL。

*lHint*<br/>
包含有关修改的信息。

*pHint*<br/>
指向存储有关修改信息的对象。

### <a name="remarks"></a>备注

调用 [SetModifiedFlag](#setmodifiedflag) 成员函数后，应调用此函数。 此函数通知附加到文档的每个视图，文档已修改的 *pSender* 指定的视图除外。 通常，在用户通过视图更改文档后，从视图类调用此函数。

此函数为文档的每个视图调用 [CView：： OnUpdate](../../mfc/reference/cview-class.md#onupdate) 成员函数，发送视图除外，传递 *pHint* 和 *lHint*。 使用这些参数将信息传递到有关对文档所做的修改的视图。 您可以使用 *lHint* 和/或定义用于存储有关修改信息的 [CObject](../../mfc/reference/cobject-class.md)派生类，并使用 *pHint* 传递该类的对象。 重写由 `CView::OnUpdate` [CView](../../mfc/reference/cview-class.md)派生的类中的成员函数，以根据传递的信息优化视图显示的更新。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#64](../../mfc/codesnippet/cpp/cdocument-class_9.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例 MDIDOCVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 示例 SNAPVW](../../overview/visual-cpp-samples.md)<br/>
[MFC 示例 NPP](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CCmdTarget 类](../../mfc/reference/ccmdtarget-class.md)<br/>
[CView 类](../../mfc/reference/cview-class.md)<br/>
[CDocTemplate 类](../../mfc/reference/cdoctemplate-class.md)

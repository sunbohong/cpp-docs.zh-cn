---
title: CDataRecoveryHandler 类
ms.date: 03/27/2019
f1_keywords:
- CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::CDataRecoveryHandler
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveAllDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::AutosaveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::CreateDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAllAutosavedFiles
- AFXDATARECOVERY/CDataRecoveryHandler::DeleteAutosavedFile
- AFXDATARECOVERY/CDataRecoveryHandler::GenerateAutosaveFileName
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::GetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::GetDocumentListName
- AFXDATARECOVERY/CDataRecoveryHandler::GetNormalDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRecoveredDocumentTitle
- AFXDATARECOVERY/CDataRecoveryHandler::GetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::GetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::Initialize
- AFXDATARECOVERY/CDataRecoveryHandler::QueryRestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::ReadOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::RemoveDocumentInfo
- AFXDATARECOVERY/CDataRecoveryHandler::ReopenPreviousDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::RestoreAutosavedDocuments
- AFXDATARECOVERY/CDataRecoveryHandler::SaveOpenDocumentList
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosaveInterval
- AFXDATARECOVERY/CDataRecoveryHandler::SetAutosavePath
- AFXDATARECOVERY/CDataRecoveryHandler::SetRestartIdentifier
- AFXDATARECOVERY/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle
- AFXDATARECOVERY/CDataRecoveryHandler::SetShutdownByRestartManager
- AFXDATARECOVERY/CDataRecoveryHandler::UpdateDocumentInfo
helpviewer_keywords:
- CDataRecoveryHandler [MFC], CDataRecoveryHandler
- CDataRecoveryHandler [MFC], AutosaveAllDocumentInfo
- CDataRecoveryHandler [MFC], AutosaveDocumentInfo
- CDataRecoveryHandler [MFC], CreateDocumentInfo
- CDataRecoveryHandler [MFC], DeleteAllAutosavedFiles
- CDataRecoveryHandler [MFC], DeleteAutosavedFile
- CDataRecoveryHandler [MFC], GenerateAutosaveFileName
- CDataRecoveryHandler [MFC], GetAutosaveInterval
- CDataRecoveryHandler [MFC], GetAutosavePath
- CDataRecoveryHandler [MFC], GetDocumentListName
- CDataRecoveryHandler [MFC], GetNormalDocumentTitle
- CDataRecoveryHandler [MFC], GetRecoveredDocumentTitle
- CDataRecoveryHandler [MFC], GetRestartIdentifier
- CDataRecoveryHandler [MFC], GetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], GetShutdownByRestartManager
- CDataRecoveryHandler [MFC], Initialize
- CDataRecoveryHandler [MFC], QueryRestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], ReadOpenDocumentList
- CDataRecoveryHandler [MFC], RemoveDocumentInfo
- CDataRecoveryHandler [MFC], ReopenPreviousDocuments
- CDataRecoveryHandler [MFC], RestoreAutosavedDocuments
- CDataRecoveryHandler [MFC], SaveOpenDocumentList
- CDataRecoveryHandler [MFC], SetAutosaveInterval
- CDataRecoveryHandler [MFC], SetAutosavePath
- CDataRecoveryHandler [MFC], SetRestartIdentifier
- CDataRecoveryHandler [MFC], SetSaveDocumentInfoOnIdle
- CDataRecoveryHandler [MFC], SetShutdownByRestartManager
- CDataRecoveryHandler [MFC], UpdateDocumentInfo
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
ms.openlocfilehash: c796f24ad37b3bae11314e2885bf25e25f85aba6
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561968"
---
# <a name="cdatarecoveryhandler-class"></a>CDataRecoveryHandler 类

`CDataRecoveryHandler`如果应用程序意外退出，则自动保存文档并对其进行还原。

## <a name="syntax"></a>语法

```
class CDataRecoveryHandler : public CObject
```

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|||
|-|-|
|[CDataRecoveryHandler::CDataRecoveryHandler](#cdatarecoveryhandler)|构造 `CDataRecoveryHandler` 对象。|

### <a name="methods"></a>方法

|||
|-|-|
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](#autosavealldocumentinfo)|自动保存向类注册的每个文件 `CDataRecoveryHandler` 。|
|[CDataRecoveryHandler::AutosaveDocumentInfo](#autosavedocumentinfo)|自动保存指定的文档。|
|[CDataRecoveryHandler::CreateDocumentInfo](#createdocumentinfo)|将文档添加到打开的文档的列表。|
|[CDataRecoveryHandler：:D eleteAllAutosavedFiles](#deleteallautosavedfiles)|删除所有当前自动保存的文件。|
|[CDataRecoveryHandler：:D eleteAutosavedFile](#deleteautosavedfile)|删除指定的自动保存文件。|
|[CDataRecoveryHandler::GenerateAutosaveFileName](#generateautosavefilename)|生成与提供的文档文件名关联的自动保存文件的名称。|
|[CDataRecoveryHandler::GetAutosaveInterval](#getautosaveinterval)|返回自动保存尝试之间的间隔。|
|[CDataRecoveryHandler::GetAutosavePath](#getautosavepath)|返回自动保存的文件的路径。|
|[CDataRecoveryHandler::GetDocumentListName](#getdocumentlistname)|从对象中检索文档名称 `CDocument` 。|
|[CDataRecoveryHandler::GetNormalDocumentTitle](#getnormaldocumenttitle)|检索指定文档的普通标题。|
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](#getrecovereddocumenttitle)|创建并返回已恢复文档的标题。|
|[CDataRecoveryHandler::GetRestartIdentifier](#getrestartidentifier)|检索应用程序的唯一重新启动标识符。|
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](#getsavedocumentinfoonidle)|指示是否在 `CDataRecoveryHandler` 当前空闲循环中执行自动保存。|
|[CDataRecoveryHandler::GetShutdownByRestartManager](#getshutdownbyrestartmanager)|指示重新启动管理器是否导致应用程序退出。|
|[CDataRecoveryHandler：： Initialize](#initialize)|初始化 `CDataRecoveryHandler`。|
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments)|向用户显示自动保存的每个文档的对话框 `CDataRecoveryHandler` 。 此对话框确定用户是否要还原自动保存的文档。|
|[CDataRecoveryHandler::ReadOpenDocumentList](#readopendocumentlist)|从注册表加载打开的文档列表。|
|[CDataRecoveryHandler::RemoveDocumentInfo](#removedocumentinfo)|从打开的文档列表中删除提供的文档。|
|[CDataRecoveryHandler::ReopenPreviousDocuments](#reopenpreviousdocuments)|打开以前打开的文档。|
|[CDataRecoveryHandler::RestoreAutosavedDocuments](#restoreautosaveddocuments)|基于用户输入还原自动保存的文档。|
|[CDataRecoveryHandler::SaveOpenDocumentList](#saveopendocumentlist)|将当前打开的文档的列表保存到 Windows 注册表中。|
|[CDataRecoveryHandler::SetAutosaveInterval](#setautosaveinterval)|设置自动保存循环之间的时间（以毫秒为单位）。|
|[CDataRecoveryHandler::SetAutosavePath](#setautosavepath)|设置保存自动保存的文件的目录。|
|[CDataRecoveryHandler::SetRestartIdentifier](#setrestartidentifier)|设置此实例的唯一重新启动标识符 `CDataRecoveryHandler` 。|
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle)|设置是否在 `CDataRecoveryHandler` 当前空闲周期期间将打开的文档信息保存到 Windows 注册表中。|
|[CDataRecoveryHandler::SetShutdownByRestartManager](#setshutdownbyrestartmanager)|设置应用程序的上一次退出是否是由重新启动管理器导致的。|
|[CDataRecoveryHandler::UpdateDocumentInfo](#updatedocumentinfo)|更新文档的信息，因为用户保存了该文档。|

### <a name="data-members"></a>数据成员

|||
|-|-|
|m_bRestoringPreviousOpenDocs|指示数据恢复处理程序是否重新打开以前打开的文档。|
|m_bSaveDocumentInfoOnIdle|指示数据恢复处理程序是否在下一个空闲循环上自动保存文档。|
|m_bShutdownByRestartManager|指示重新启动管理器是否导致应用程序退出。|
|m_dwRestartManagerSupportFlags|标志，指示重新启动管理器为应用程序提供的支持。|
|m_lstAutosavesToDelete|在关闭原始文档时未删除的自动保存的文件的列表。 当应用程序退出时，重新启动管理器将重试删除文件。|
|m_mapDocNameToAutosaveName|文档名称到自动保存的文件名的地图。|
|m_mapDocNameToDocumentPtr|文档名称到 [CDocument](../../mfc/reference/cdocument-class.md) 指针的映射。|
|m_mapDocNameToRestoreBool|文档名称到布尔值参数的映射，该参数指示是否还原自动保存的文档。|
|m_mapDocumentPtrToDocName|`CDocument`指向文档名称的指针的映射。|
|m_mapDocumentPtrToDocTitle|`CDocument`指向文档标题的指针的映射。 这些标题用于保存文件。|
|m_nAutosaveInterval|自动保存之间的时间（以毫秒为单位）。|
|m_nTimerID|自动保存计时器的标识符。|
|m_strAutosavePath|存储自动保存的文档的位置。|
|m_strRestartIdentifier|重新启动管理器的 GUID 的字符串表示形式。|

## <a name="remarks"></a>备注

重新启动管理器使用 `CDataRecoveryHandler` 类跟踪所有打开的文档，并根据需要自动保存它们。 若要启用自动保存，请使用 [CDataRecoveryHandler：： SetSaveDocumentInfoOnIdle](#setsavedocumentinfoonidle) 方法。 此方法指示在 `CDataRecoveryHandler` 下一个空闲循环中执行自动保存。 `SetSaveDocumentInfoOnIdle`当应执行自动保存时，重新启动管理器 `CDataRecoveryHandler` 会调用。

类的所有方法 `CDataRecoveryHandler` 都是虚拟的。 重写此类中的方法以创建自己的自定义数据恢复处理程序。 除非您创建自己的数据恢复处理程序或重新启动管理器，否则请不要实例化 CDataRecoveryHandler。 [CWinApp 类](../../mfc/reference/cwinapp-class.md) `CDataRecoveryHandler` 根据需要创建对象。

`CDataRecoveryHandler`必须先调用[CDataRecoveryHandler：： Initialize](#initialize)，然后才能使用对象。

因为 `CDataRecoveryHandler` 类与重新启动管理器密切连接，所以 `CDataRecoveryHandler` 依赖于全局参数 `m_dwRestartManagerSupportFlags` 。 此参数确定重新启动管理器具有哪些权限，以及它如何与应用程序交互。 若要将重新启动管理器合并到现有应用程序中，你必须 `m_dwRestartManagerSupportFlags` 在主应用程序的构造函数中分配相应的值。 有关如何使用重新启动管理器的详细信息，请参阅 [如何：添加重新启动管理器支持](../../mfc/how-to-add-restart-manager-support.md)。

## <a name="requirements"></a>要求

**标头：** afxdatarecovery

## <a name="cdatarecoveryhandlerautosavealldocumentinfo"></a><a name="autosavealldocumentinfo"></a> CDataRecoveryHandler::AutosaveAllDocumentInfo

自动保存向类注册的每个文件 `CDataRecoveryHandler` 。

```
virtual BOOL AutosaveAllDocumentInfo();
```

### <a name="return-value"></a>返回值

如果 `CDataRecoveryHandler` 保存了所有文档，则为 TRUE;如果未保存任何文档，则为 FALSE。

### <a name="remarks"></a>备注

如果没有必须保存的文档，则此方法返回 TRUE。 如果检索 `CWinApp` 或 `CDocManager` 的应用程序生成错误，它也会返回 TRUE，而不保存任何文档。

若要使用此方法，必须在中设置 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 或 AFX_RESTART_MANAGER_AUTOSAVE_AT_INTERVAL `m_dwRestartManagerSupportFlags` 。 有关详细信息，请参阅 [如何：添加重新启动管理器支持](../../mfc/how-to-add-restart-manager-support.md)。

## <a name="cdatarecoveryhandlerautosavedocumentinfo"></a><a name="autosavedocumentinfo"></a> CDataRecoveryHandler::AutosaveDocumentInfo

自动保存指定的文档。

```
virtual BOOL AutosaveDocumentInfo(
    CDocument* pDocument,
    BOOL bResetModifiedFlag = TRUE);
```

### <a name="parameters"></a>参数

*pDocument*\
中指向要保存的的指针 `CDocument` 。

*bResetModifiedFlag*\
中如果为 TRUE，则表示 `CDataRecoveryHandler` 考虑修改 *pDocument* ;FALSE 指示框架将 *pDocument* 视为不修改。 有关此标志效果的详细信息，请参阅 "备注" 部分。

### <a name="return-value"></a>返回值

如果设置了适当的标志，并且 *pDocument* 是有效的对象，则为 TRUE `CDocument` 。

### <a name="remarks"></a>备注

每个 `CDocument` 对象都有一个标志，用于指示该对象自上次保存后是否已更改。 使用 [CDocument：： IsModified](../../mfc/reference/cdocument-class.md#ismodified) 确定此标志的状态。 如果 `CDocument` 自上次保存后未发生更改，则将 `AutosaveDocumentInfo` 删除该文档的任何自动保存的文件。 如果文档自上次保存后已发生更改，则关闭它会提示用户先保存文档再关闭。

> [!NOTE]
> 使用 *bResetModifiedFlag* 将文档状态更改为 "未修改" 可能导致用户丢失未保存的数据。 如果框架将文档视为未修改，则关闭它不会提示用户保存。

如果*pDocument*不是有效的对象，则此方法将引发带有[ASSERT](diagnostic-services.md#assert)宏的异常 `CDocument` 。

若要使用此方法，必须在 *m_dwRestartManagerSupportFlags*中设置 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 或 AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL。

## <a name="cdatarecoveryhandlercdatarecoveryhandler"></a><a name="cdatarecoveryhandler"></a> CDataRecoveryHandler::CDataRecoveryHandler

构造 `CDataRecoveryHandler` 对象。

```
CDataRecoveryHandler(
    DWORD dwRestartManagerSupportFlags,
    int nAutosaveInterval);
```

### <a name="parameters"></a>参数

*dwRestartManagerSupportFlags*\
中指示支持重新启动管理器的哪些选项。

*nAutosaveInterval*\
中自动保存之间的时间。 此参数以毫秒为单位。

### <a name="remarks"></a>备注

`CDataRecoveryHandler`使用 "**新建项目**" 向导时，MFC 框架会自动为应用程序创建对象。 除非你要自定义数据恢复行为或重新启动管理器，否则不应创建 `CDataRecoveryHandler` 对象。

## <a name="cdatarecoveryhandlercreatedocumentinfo"></a><a name="createdocumentinfo"></a> CDataRecoveryHandler::CreateDocumentInfo

将文档添加到打开的文档的列表。

```
virtual BOOL CreateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>参数

*pDocument*\
中指向的指针 `CDocument` 。 此方法为此创建文档信息 `CDocument` 。

### <a name="return-value"></a>返回值

默认实现返回 TRUE。

### <a name="remarks"></a>备注

此方法会检查 *pDocument* 是否已在文档列表中，然后再添加文档。 如果 *pDocument* 已在列表中，则此方法将删除与 *pDocument*关联的自动保存的文件。

若要使用此方法，必须在 *m_dwRestartManagerSupportFlags*中设置 AFX_RESTART_MANAGER_AUTOSAVE_AT_RESTART 或 AFX_RESTARTMANAGER_AUTOSAVE_AT_INTERVAL。

## <a name="cdatarecoveryhandlerdeleteallautosavedfiles"></a><a name="deleteallautosavedfiles"></a> CDataRecoveryHandler：:D eleteAllAutosavedFiles

删除所有当前自动保存的文件。

```
virtual BOOL DeleteAllAutosavedFiles();
```

### <a name="return-value"></a>返回值

默认实现始终返回 TRUE。

## <a name="cdatarecoveryhandlerdeleteautosavedfile"></a><a name="deleteautosavedfile"></a> CDataRecoveryHandler：:D eleteAutosavedFile

删除指定的自动保存文件。

```
virtual BOOL DeleteAutosavedFile(const CString& strAutosavedFile);
```

### <a name="parameters"></a>参数

*strAutosavedFile*\
中一个包含自动保存的文件名的字符串。

### <a name="return-value"></a>返回值

默认实现始终返回 TRUE。

### <a name="remarks"></a>备注

如果此方法无法删除自动保存的文件，它会将文件的名称保存在列表中。 的析构函数 `CDataRecoveryHandler` 尝试删除该列表中指定的每个可保存文件。

## <a name="cdatarecoveryhandlergenerateautosavefilename"></a><a name="generateautosavefilename"></a> CDataRecoveryHandler::GenerateAutosaveFileName

生成与提供的文档文件名关联的自动保存文件的名称。

```
virtual CString GenerateAutosaveFileName(const CString& strDocumentName) const;
```

### <a name="parameters"></a>参数

*strDocumentName*<br/>
中包含文档名称的字符串。 `GenerateAutosaveFileName` 使用此文档名称生成相应的自动保存文件名。

### <a name="return-value"></a>返回值

从 *strDocumentName*生成的自动保存文件名。

### <a name="remarks"></a>备注

每个文档名称都具有与自动保存文件名相同的一对一映射。

## <a name="cdatarecoveryhandlergetautosaveinterval"></a><a name="getautosaveinterval"></a> CDataRecoveryHandler::GetAutosaveInterval

返回自动保存尝试之间的间隔。

```
virtual int GetAutosaveInterval() const;
```

### <a name="return-value"></a>返回值

自动保存尝试之间的间隔（以毫秒为单位）。

## <a name="cdatarecoveryhandlergetautosavepath"></a><a name="getautosavepath"></a> CDataRecoveryHandler::GetAutosavePath

返回自动保存的文件的路径。

```
virtual CString GetAutosavePath() const;
```

### <a name="return-value"></a>返回值

存储自动保存的文档的位置。

## <a name="cdatarecoveryhandlergetdocumentlistname"></a><a name="getdocumentlistname"></a> CDataRecoveryHandler::GetDocumentListName

从对象中检索文档名称 `CDocument` 。

```
virtual CString GetDocumentListName(CDocument* pDocument) const;
```

### <a name="parameters"></a>参数

*pDocument*\
中指向的指针 `CDocument` 。 `GetDocumentListName` 从此中检索文档名称 `CDocument` 。

### <a name="return-value"></a>返回值

*PDocument*中的文档名称。

### <a name="remarks"></a>备注

`CDataRecoveryHandler`使用文档名称作为*m_mapDocNameToAutosaveName*、 *m_mapDocNameToDocumentPtr*和*m_mapDocNameToRestoreBool*中的键。 这些参数使 `CDataRecoveryHandler` 能够监视 `CDocument` 对象、自动保存文件名和自动保存设置。

## <a name="cdatarecoveryhandlergetnormaldocumenttitle"></a><a name="getnormaldocumenttitle"></a> CDataRecoveryHandler::GetNormalDocumentTitle

检索指定文档的普通标题。

```
virtual CString GetNormalDocumentTitle(CDocument* pDocument);
```

### <a name="parameters"></a>参数

*pDocument*\
中指向的指针 `CDocument` 。

### <a name="return-value"></a>返回值

指定文档的普通标题。

### <a name="remarks"></a>备注

文档的普通标题通常是没有路径的文档的文件名。 这是 "**另存为**" 对话框的 "**文件名**" 字段中的标题。

## <a name="cdatarecoveryhandlergetrecovereddocumenttitle"></a><a name="getrecovereddocumenttitle"></a> CDataRecoveryHandler::GetRecoveredDocumentTitle

创建并返回已恢复文档的标题。

```
virtual CString GetRecoveredDocumentTitle(const CString& strDocumentTitle) const;
```

### <a name="parameters"></a>参数

*strDocumentTitle*<br/>
中文档的普通标题。

### <a name="return-value"></a>返回值

已恢复的文档的标题。

### <a name="remarks"></a>备注

默认情况下，文档的已恢复标题是在其后面追加了 **[已恢复]** 的普通标题。 当查询用户还原自动保存的文档时，会向用户显示已恢复的标题 `CDataRecoveryHandler` 。

## <a name="cdatarecoveryhandlergetrestartidentifier"></a><a name="getrestartidentifier"></a> CDataRecoveryHandler::GetRestartIdentifier

检索应用程序的唯一重新启动标识符。

```
virtual CString GetRestartIdentifier() const;
```

### <a name="return-value"></a>返回值

唯一重新启动标识符。

### <a name="remarks"></a>备注

每次执行应用程序时，restart 标识符都是唯一的。

在 `CDataRecoveryHandler` 注册表中存储有关当前打开的文档的信息。 当重新启动管理器退出应用程序并重新启动它时，它会向提供重新启动标识符 `CDataRecoveryHandler` 。 `CDataRecoveryHandler`使用 restart 标识符检索以前打开的文档的列表。 这样，便可以 `CDataRecoveryHandler` 尝试查找和还原自动保存的文件。

## <a name="cdatarecoveryhandlergetsavedocumentinfoonidle"></a><a name="getsavedocumentinfoonidle"></a> CDataRecoveryHandler::GetSaveDocumentInfoOnIdle

指示是否在 `CDataRecoveryHandler` 当前空闲循环中执行自动保存。

```
virtual BOOL GetSaveDocumentInfoOnIdle() const;
```

### <a name="return-value"></a>返回值

如果为 TRUE，则指示 `CDataRecoveryHandler` 当前空闲循环上的自动保存;FALSE 指示它不存在。

## <a name="cdatarecoveryhandlergetshutdownbyrestartmanager"></a><a name="getshutdownbyrestartmanager"></a> CDataRecoveryHandler::GetShutdownByRestartManager

指示重新启动管理器是否导致应用程序退出。

```
virtual BOOL GetShutdownByRestartManager() const;
```

### <a name="return-value"></a>返回值

TRUE 表示重新启动管理器导致应用程序退出;FALSE 表示未指定。

## <a name="cdatarecoveryhandlerinitialize"></a><a name="initialize"></a> CDataRecoveryHandler：： Initialize

初始化 `CDataRecoveryHandler`。

```
virtual BOOL Initialize();
```

### <a name="return-value"></a>返回值

如果初始化成功，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

初始化过程会从注册表加载用于存储自动保存文件的路径。 如果 `Initialize` 方法找不到此目录或路径为空，则将 `Initialize` 失败，并返回 `FALSE` 。

在应用程序初始化后，使用 [CDataRecoveryHandler：： SetAutosavePath](#setautosavepath) 更改自动保存路径 `CDataRecoveryHandler` 。

`Initialize`方法还会启动计时器，以便在下一次自动保存发生时进行监视。 在应用程序初始化后，使用 [CDataRecoveryHandler：： SetAutosaveInterval](#setautosaveinterval) 更改自动保存的时间间隔 `CDataRecoveryHandler` 。

## <a name="cdatarecoveryhandlerqueryrestoreautosaveddocuments"></a><a name="queryrestoreautosaveddocuments"></a> CDataRecoveryHandler::QueryRestoreAutosavedDocuments

向用户显示自动保存的每个文档的对话框 `CDataRecoveryHandler` 。 此对话框确定用户是否要还原自动保存的文档。

```
virtual void QueryRestoreAutosavedDocuments();
```

### <a name="remarks"></a>备注

如果你的应用程序是 Unicode，则此方法将向用户显示 [CTaskDialog](../../mfc/reference/ctaskdialog-class.md) 。 否则，框架使用 [AfxMessageBox](../../mfc/reference/cstring-formatting-and-message-box-display.md#afxmessagebox) 查询用户。

`QueryRestoreAutosavedDocuments`收集来自用户的所有响应后，它会将信息存储在*m_mapDocNameToRestoreBool*的成员变量中。 此方法不会还原自动保存的文档。

## <a name="cdatarecoveryhandlerreadopendocumentlist"></a><a name="readopendocumentlist"></a> CDataRecoveryHandler::ReadOpenDocumentList

从注册表加载打开的文档列表。

```
virtual BOOL ReadOpenDocumentList();
```

### <a name="return-value"></a>返回值

如果为 TRUE，则表示已 `ReadOpenDocumentList` 从注册表加载至少一个文档的信息;FALSE 表示未加载任何文档信息。

### <a name="remarks"></a>备注

此函数从注册表加载打开的文档信息，并将其存储在 *m_mapDocNameToAutosaveName*的成员变量中。

`ReadOpenDocumentList`加载所有数据后，它将从注册表中删除文档信息。

## <a name="cdatarecoveryhandlerremovedocumentinfo"></a><a name="removedocumentinfo"></a> CDataRecoveryHandler::RemoveDocumentInfo

从打开的文档列表中删除提供的文档。

```
virtual BOOL RemoveDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>参数

*pDocument*\
中指向要删除的文档的指针。

### <a name="return-value"></a>返回值

如果从列表中删除 *pDocument* ，则为 TRUE;如果发生错误，则为 FALSE。

### <a name="remarks"></a>备注

用户关闭文档后，框架将使用此方法从打开的文档列表中删除该文档。

如果 `RemoveDocumentInfo` 在打开的文档列表中找不到 *pDocument* ，则不执行任何操作并返回 TRUE。

若要使用此方法，必须在 *m_dwRestartManagerSupportFlags*中设置 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES。

## <a name="cdatarecoveryhandlerreopenpreviousdocuments"></a><a name="reopenpreviousdocuments"></a> CDataRecoveryHandler::ReopenPreviousDocuments

打开以前打开的文档。

```
virtual BOOL ReopenPreviousDocuments();
```

### <a name="return-value"></a>返回值

如果至少打开了一个文档，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

此方法将打开以前打开的文档的最新保存。 如果文档未保存或自动保存，则 `ReopenPreviousDocuments` 会基于该文件类型的模板打开一个空白文档。

若要使用此方法，必须在 *m_dwRestartManagerSupportFlags*中设置 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES。 如果未设置此参数，则 `ReopenPreviousDocuments` 不执行任何操作并返回 FALSE。

如果以前打开的文档列表中没有存储文档，则 `ReopenPreviousDocuments` 不执行任何操作并返回 FALSE。

## <a name="cdatarecoveryhandlerrestoreautosaveddocuments"></a><a name="restoreautosaveddocuments"></a> CDataRecoveryHandler::RestoreAutosavedDocuments

基于用户输入还原自动保存的文档。

```
virtual BOOL RestoreAutosavedDocuments();
```

### <a name="return-value"></a>返回值

如果此方法成功还原文档，则为 TRUE。

### <a name="remarks"></a>备注

此方法调用 [CDataRecoveryHandler：： QueryRestoreAutosavedDocuments](#queryrestoreautosaveddocuments) 来确定用户要还原的文档。 如果用户决定不还原自动保存的文档， `RestoreAutosavedDocuments` 则会删除自动保存文件。 否则， `RestoreAutosavedDocuments` 用自动保存的版本替换打开的文档。

若要使用此方法，必须在中设置 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES 或 AFX_RESTART_MANAGER_RESTORE_AUTOSAVED_FILES `m_dwRestartManagerSupportFlags` 。

## <a name="cdatarecoveryhandlersaveopendocumentlist"></a><a name="saveopendocumentlist"></a> CDataRecoveryHandler::SaveOpenDocumentList

将当前打开的文档的列表保存到 Windows 注册表中。

```
virtual BOOL SaveOpenDocumentList();
```

### <a name="return-value"></a>返回值

如果未打开要保存的文档，则为 TRUE; 否则为。 如果有要保存到注册表中的文档，则为 FALSE; 但由于出现错误而未保存它们。

### <a name="remarks"></a>备注

`SaveOpenDocumentList`当应用程序意外退出，或当应用程序退出进行升级时，重新启动管理器会调用。 当应用程序重新启动时，它将使用 [CDataRecoveryHandler：： ReadOpenDocumentList](#readopendocumentlist) 检索打开的文档的列表。

此方法仅保存打开的文档的列表。 方法 [CDataRecoveryHandler：： AutosaveDocumentInfo](#autosavedocumentinfo) 负责保存文档本身。

## <a name="cdatarecoveryhandlersetautosaveinterval"></a><a name="setautosaveinterval"></a> CDataRecoveryHandler::SetAutosaveInterval

设置自动保存循环之间的时间（以毫秒为单位）。

```
Virtual void SetAutosaveInterval(int nAutosaveInterval);
```

### <a name="parameters"></a>参数

*nAutosaveInterval*<br/>
中新的自动保存间隔（毫秒）。

## <a name="cdatarecoveryhandlersetautosavepath"></a><a name="setautosavepath"></a> CDataRecoveryHandler::SetAutosavePath

设置保存自动保存的文件的目录。

```
virtual void SetAutosavePath(const CString& strAutosavePath);
```

### <a name="parameters"></a>参数

*strAutosavePath*\
中存储自动保存文件的路径。

### <a name="remarks"></a>备注

更改自动保存目录不会移动当前保存的文件。

## <a name="cdatarecoveryhandlersetrestartidentifier"></a><a name="setrestartidentifier"></a> CDataRecoveryHandler::SetRestartIdentifier

设置此实例的唯一重新启动标识符 `CDataRecoveryHandler` 。

```
virtual void SetRestartIdentifier(const CString& strRestartIdentifier);
```

### <a name="parameters"></a>参数

*strRestartIdentifier*\
中重新启动管理器的唯一标识符。

### <a name="remarks"></a>备注

重新启动管理器记录有关注册表中打开的文档的信息。 此信息随密钥的唯一重新启动标识符一起存储。 因为重启标识符对于应用程序的每个实例都是唯一的，所以，应用程序的多个实例可能会意外退出，并且重新启动管理器可以恢复它们。

## <a name="cdatarecoveryhandlersetsavedocumentinfoonidle"></a><a name="setsavedocumentinfoonidle"></a> CDataRecoveryHandler::SetSaveDocumentInfoOnIdle

设置是否在 `CDataRecoveryHandler` 当前空闲周期期间将打开的文档信息保存到 Windows 注册表中。

```
virtual void SetSaveDocumentInfoOnIdle(BOOL bSaveOnIdle);
```

### <a name="parameters"></a>参数

*bSaveOnIdle*\
中如果为 TRUE，则保存当前空闲周期的文档信息;若为 FALSE，则不执行保存。

## <a name="cdatarecoveryhandlersetshutdownbyrestartmanager"></a><a name="setshutdownbyrestartmanager"></a> CDataRecoveryHandler::SetShutdownByRestartManager

设置应用程序的上一次退出是否是由重新启动管理器导致的。

```
virtual void SetShutdownByRestartManager(BOOL bShutdownByRestartManager);
```

### <a name="parameters"></a>参数

*bShutdownByRestartManager*\
中如果指示重新启动管理器导致应用程序退出，则为 TRUE;如果为 FALSE，则指示应用程序因其他原因退出。

### <a name="remarks"></a>备注

框架的行为方式有所不同，具体取决于上一次退出是否是意外退出，或者它是否是由重新启动管理器启动的。

## <a name="cdatarecoveryhandlerupdatedocumentinfo"></a><a name="updatedocumentinfo"></a> CDataRecoveryHandler::UpdateDocumentInfo

更新文档的信息，因为用户保存了该文档。

```
virtual BOOL UpdateDocumentInfo(CDocument* pDocument);
```

### <a name="parameters"></a>参数

*pDocument*\
中指向已保存文档的指针。

### <a name="return-value"></a>返回值

如果此方法删除自动保存的文档并更新文档信息，则为 TRUE;如果发生错误，则为 FALSE。

### <a name="remarks"></a>备注

用户保存文档时，应用程序会删除自动保存的文件，因为不再需要它。 `UpdateDocumentInfo` 通过调用 [CDataRecoveryHandler：： RemoveDocumentInfo](#removedocumentinfo)删除自动保存的文件。 `UpdateDocumentInfo` 然后将 *pDocument* 中的信息添加到当前打开的文档的列表 `RemoveDocumentInfo` ，因为删除该信息，但保存的文档仍处于打开状态。

若要使用此方法，必须在 *m_dwRestartManagerSupportFlags*中设置 AFX_RESTART_MANAGER_REOPEN_PREVIOUS_FILES。

## <a name="see-also"></a>另请参阅

[类](../../mfc/reference/mfc-classes.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[如何：添加重新启动管理器支持](../../mfc/how-to-add-restart-manager-support.md)

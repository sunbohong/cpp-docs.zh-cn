---
description: 了解详细信息： CCommandLineInfo 类
title: CCommandLineInfo 类
ms.date: 11/04/2016
f1_keywords:
- CCommandLineInfo
- AFXWIN/CCommandLineInfo
- AFXWIN/CCommandLineInfo::CCommandLineInfo
- AFXWIN/CCommandLineInfo::ParseParam
- AFXWIN/CCommandLineInfo::m_bRunAutomated
- AFXWIN/CCommandLineInfo::m_bRunEmbedded
- AFXWIN/CCommandLineInfo::m_bShowSplash
- AFXWIN/CCommandLineInfo::m_nShellCommand
- AFXWIN/CCommandLineInfo::m_strDriverName
- AFXWIN/CCommandLineInfo::m_strFileName
- AFXWIN/CCommandLineInfo::m_strPortName
- AFXWIN/CCommandLineInfo::m_strPrinterName
- AFXWIN/CCommandLineInfo::m_strRestartIdentifier
helpviewer_keywords:
- CCommandLineInfo [MFC], CCommandLineInfo
- CCommandLineInfo [MFC], ParseParam
- CCommandLineInfo [MFC], m_bRunAutomated
- CCommandLineInfo [MFC], m_bRunEmbedded
- CCommandLineInfo [MFC], m_bShowSplash
- CCommandLineInfo [MFC], m_nShellCommand
- CCommandLineInfo [MFC], m_strDriverName
- CCommandLineInfo [MFC], m_strFileName
- CCommandLineInfo [MFC], m_strPortName
- CCommandLineInfo [MFC], m_strPrinterName
- CCommandLineInfo [MFC], m_strRestartIdentifier
ms.assetid: 3e313ddb-0a82-4991-87ac-a27feff4668c
ms.openlocfilehash: 4c26ae86608725caa61ad4d1077bed01a3f40385
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227918"
---
# <a name="ccommandlineinfo-class"></a>CCommandLineInfo 类

辅助在应用程序启动时分析命令行。

## <a name="syntax"></a>语法

```
class CCommandLineInfo : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CCommandLineInfo::CCommandLineInfo](#ccommandlineinfo)|构造默认 `CCommandLineInfo` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CCommandLineInfo::ParseParam](#parseparam)|重写此回调以分析各个参数。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CCommandLineInfo：： m_bRunAutomated](#m_brunautomated)|指示已找到命令行 `/Automation` 选项。|
|[CCommandLineInfo：： m_bRunEmbedded](#m_brunembedded)|指示已找到命令行 `/Embedding` 选项。|
|[CCommandLineInfo：： m_bShowSplash](#m_bshowsplash)|指示是否应显示初始屏幕。|
|[CCommandLineInfo：： m_nShellCommand](#m_nshellcommand)|指示要处理的 shell 命令。|
|[CCommandLineInfo：： m_strDriverName](#m_strdrivername)|如果 shell 命令打印到，则指示驱动程序名称;否则为空。|
|[CCommandLineInfo：： m_strFileName](#m_strfilename)|指示要打开或打印的文件的名称;如果 shell 命令为 New 或 DDE，则为空。|
|[CCommandLineInfo：： m_strPortName](#m_strportname)|如果 shell 命令打印到，则指示端口名称;否则为空。|
|[CCommandLineInfo：： m_strPrinterName](#m_strprintername)|如果 shell 命令打印到，则指示打印机名称;否则为空。|
|[CCommandLineInfo：： m_strRestartIdentifier](#m_strrestartidentifier)|指示重新启动管理器重新启动应用程序时重新启动管理器的唯一重新启动标识符。|

## <a name="remarks"></a>备注

MFC 应用程序通常会在其应用程序对象的 [InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) 函数中创建此类的本地实例。 然后，将该对象传递给 [CWinApp：:P arsecommandline](../../mfc/reference/cwinapp-class.md#parsecommandline)，这将重复调用 [ParseParam](#parseparam) 来填充 `CCommandLineInfo` 对象。 然后，将 `CCommandLineInfo` 对象传递给 [CWinApp：:P rocessshellcommand](../../mfc/reference/cwinapp-class.md#processshellcommand) 来处理命令行参数和标志。

您可以使用此对象封装以下命令行选项和参数：

|命令行参数|命令已执行|
|----------------------------|----------------------|
|*app*|新建文件。|
|*应用* 文件名|打开文件。|
|*应用* `/p` 名字|将文件打印到默认打印机。|
|*应用* `/pt` filename 打印机驱动程序端口|将文件打印到指定打印机。|
|*应用*`/dde`|启动并等待 DDE 命令。|
|*应用*`/Automation`|作为 OLE 自动化服务器启动。|
|*应用*`/Embedding`|开始编辑嵌入的 OLE 项。|
|*应用*`/Register`<br /><br /> *应用*`/Regserver`|通知应用程序执行任何注册任务。|
|*应用*`/Unregister`<br /><br /> *应用*`/Unregserver`|通知应用程序执行任何取消注册任务。|

从派生新类 `CCommandLineInfo` 以处理其他标志和参数值。 重写 [ParseParam](#parseparam) 以处理新的标志。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CCommandLineInfo`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="ccommandlineinfoccommandlineinfo"></a><a name="ccommandlineinfo"></a> CCommandLineInfo::CCommandLineInfo

此构造函数将创建一个 `CCommandLineInfo` 具有默认值的对象。

```
CCommandLineInfo();
```

### <a name="remarks"></a>备注

默认为显示初始屏幕 ( `m_bShowSplash=TRUE`) 并在 "文件" 菜单上执行新命令 ( `m_nShellCommand` **= NewFile**) 。

应用程序框架调用 [ParseParam](#parseparam) 来填充此对象的数据成员。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#54](../../mfc/codesnippet/cpp/ccommandlineinfo-class_1.cpp)]

## <a name="ccommandlineinfom_brunautomated"></a><a name="m_brunautomated"></a> CCommandLineInfo：： m_bRunAutomated

指示在 `/Automation` 命令行上找到了标志。

```
BOOL m_bRunAutomated;
```

### <a name="remarks"></a>备注

如果为 TRUE，则表示作为 OLE 自动化服务器启动。

## <a name="ccommandlineinfom_brunembedded"></a><a name="m_brunembedded"></a> CCommandLineInfo：： m_bRunEmbedded

指示在 `/Embedding` 命令行上找到了标志。

```
BOOL m_bRunEmbedded;
```

### <a name="remarks"></a>备注

如果为 TRUE，则表示开始编辑嵌入式 OLE 项。

## <a name="ccommandlineinfom_bshowsplash"></a><a name="m_bshowsplash"></a> CCommandLineInfo：： m_bShowSplash

指示应显示初始屏幕。

```
BOOL m_bShowSplash;
```

### <a name="remarks"></a>备注

如果为 TRUE，则表示启动期间应显示此应用程序的初始屏幕。 如果[m_nShellCommand](#m_nshellcommand)等于，则[ParseParam](#parseparam)的默认实现将此数据成员设置为 TRUE `CCommandLineInfo::FileNew` 。

## <a name="ccommandlineinfom_nshellcommand"></a><a name="m_nshellcommand"></a> CCommandLineInfo：： m_nShellCommand

指示此应用程序实例的 shell 命令。

```
m_nShellCommand;
```

### <a name="remarks"></a>备注

此数据成员的类型是在类中定义的以下枚举类型 `CCommandLineInfo` 。

```
enum {
    FileNew,
    FileOpen,
    FilePrint,
    FilePrintTo,
    FileDDE,
    AppRegister,
    AppUnregister,
    RestartByRestartManager,
    FileNothing = -1
    };
```

有关这些值的简要说明，请参阅下表。

- `CCommandLineInfo::FileNew` 指示在命令行上找不到任何文件名。

- `CCommandLineInfo::FileOpen` 指示在命令行上找到了文件名，但在命令行中未找到以下任何标志： `/p` 、 `/pt` 、 `/dde` 。

- `CCommandLineInfo::FilePrint` 指示在 `/p` 命令行上找到了标志。

- `CCommandLineInfo::FilePrintTo` 指示在 `/pt` 命令行上找到了标志。

- `CCommandLineInfo::FileDDE` 指示在 `/dde` 命令行上找到了标志。

- `CCommandLineInfo::AppRegister` 指示在 `/Register` `/Regserver` 命令行上找到或标志，并要求应用程序进行注册。

- `CCommandLineInfo::AppUnregister` 指示 `/Unregister` `/Unregserver` 要求或应用程序取消注册。

- `CCommandLineInfo::RestartByRestartManager` 指示重新启动管理器重新启动了应用程序。

- `CCommandLineInfo::FileNothing` 启动时关闭新的 MDI 子窗口的显示。 按照设计，应用程序向导生成的 MDI 应用程序会在启动时显示一个新的子窗口。 若要关闭此功能，应用程序可以 `CCommandLineInfo::FileNothing` 在调用 [ProcessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)时使用作为 shell 命令。 `ProcessShellCommand` 由 `InitInstance( )` 所有派生类的调用 `CWinApp` 。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#55](../../mfc/codesnippet/cpp/ccommandlineinfo-class_2.cpp)]

## <a name="ccommandlineinfom_strdrivername"></a><a name="m_strdrivername"></a> CCommandLineInfo：： m_strDriverName

在命令行上存储第三个非标志参数的值。

```
CString m_strDriverName;
```

### <a name="remarks"></a>备注

此参数通常是 "打印到 shell" 命令的打印机驱动程序的名称。 仅当在[](#parseparam) `/pt` 命令行中找到该标志时，ParseParam 的默认实现才会设置此数据成员。

## <a name="ccommandlineinfom_strfilename"></a><a name="m_strfilename"></a> CCommandLineInfo：： m_strFileName

在命令行上存储第一个非标志参数的值。

```
CString m_strFileName;
```

### <a name="remarks"></a>备注

此参数通常是要打开的文件的名称。

## <a name="ccommandlineinfom_strportname"></a><a name="m_strportname"></a> CCommandLineInfo：： m_strPortName

在命令行上存储第四个非标志参数的值。

```
CString m_strPortName;
```

### <a name="remarks"></a>备注

此参数通常是 "打印到 shell" 命令的打印机端口的名称。 仅当在[](#parseparam) `/pt` 命令行中找到该标志时，ParseParam 的默认实现才会设置此数据成员。

## <a name="ccommandlineinfom_strprintername"></a><a name="m_strprintername"></a> CCommandLineInfo：： m_strPrinterName

将第二个非标志参数的值存储在命令行上。

```
CString m_strPrinterName;
```

### <a name="remarks"></a>备注

此参数通常是打印到 shell 命令的打印机的名称。 仅当在[](#parseparam) `/pt` 命令行中找到该标志时，ParseParam 的默认实现才会设置此数据成员。

## <a name="ccommandlineinfom_strrestartidentifier"></a><a name="m_strrestartidentifier"></a> CCommandLineInfo：： m_strRestartIdentifier

命令行上的唯一重新启动标识符。

```
CString m_strRestartIdentifier;
```

### <a name="remarks"></a>备注

重新启动标识符对于应用程序的每个实例都是唯一的。

如果重新启动管理器退出应用程序并将其配置为重新启动该应用程序，则重新启动管理器将使用 restart 标识符作为可选参数从命令行执行应用程序。 当重新启动管理器使用 restart 标识符时，应用程序可以重新打开以前打开的文档并恢复自动保存的文件。

## <a name="ccommandlineinfoparseparam"></a><a name="parseparam"></a> CCommandLineInfo：:P arseParam

框架调用此函数来分析/解释命令行中的各个参数。 第二个版本不同于仅在 Unicode 项目中的第一个版本。

```
virtual void ParseParam(
    const char* pszParam,
    BOOL bFlag,
    BOOL bLast);

virtual void ParseParam(
    const TCHAR* pszParam,
    BOOL bFlag,
    BOOL bLast);
```

### <a name="parameters"></a>parameters

*pszParam*<br/>
参数或标志。

*bFlag*<br/>
指示 *pszParam* 是参数还是标志。

*bLast*<br/>
指示这是否是命令行上的最后一个参数或标志。

### <a name="remarks"></a>备注

[CWinApp：:P arsecommandline](../../mfc/reference/cwinapp-class.md#parsecommandline) 对 `ParseParam` 命令行上的每个参数或标志调用一次，并将参数传递给 *pszParam*。 如果参数的第一个字符是 " **-** " 或 " **/** "，则将其删除，并将 *BFLAG* 设置为 TRUE。 分析最终参数时，" *群发* " 设置为 "TRUE"。

此函数的默认实现可识别以下标志： `/p` 、 `/pt` 、 `/dde` 、 `/Automation` 和 `/Embedding` ，如下表所示：

|命令行参数|命令已执行|
|----------------------------|----------------------|
|*app*|新建文件。|
|*应用* 文件名|打开文件。|
|*应用* `/p` 名字|将文件打印到默认打印机。|
|*应用* `/pt` filename 打印机驱动程序端口|将文件打印到指定打印机。|
|*应用*`/dde`|启动并等待 DDE 命令。|
|*应用*`/Automation`|作为 OLE 自动化服务器启动。|
|*应用*`/Embedding`|开始编辑嵌入的 OLE 项。|
|*应用*`/Register`<br /><br /> *应用*`/Regserver`|通知应用程序执行任何注册任务。|
|*应用*`/Unregister`<br /><br /> *应用*`/Unregserver`|通知应用程序执行任何取消注册任务。|

此信息存储在 [m_bRunAutomated](#m_brunautomated)、 [m_bRunEmbedded](#m_brunembedded)和 [m_nShellCommand](#m_nshellcommand)。 标志由正斜杠 " **/** " 或 "" 连字符标记 **-** 。

默认实现会将第一个非标志参数放入 [m_strFileName](#m_strfilename)。 对于 `/pt` 标志，默认实现会将第二个、第三个和第四个非标志参数分别放入 [m_strPrinterName](#m_strprintername)、 [m_strDriverName](#m_strdrivername)和 [m_strPortName](#m_strportname)。

默认实现还会将 [m_bShowSplash](#m_bshowsplash) 设置为仅在新文件的情况下为 TRUE。 对于新文件，用户已经执行了涉及应用程序本身的操作。 在任何其他情况下，包括使用 shell 打开现有文件时，用户操作将直接涉及文件。 在以文档为中心的角度来看，初始屏幕无需宣布启动应用程序。

在派生类中重写此函数，以处理其他标志和参数值。

## <a name="see-also"></a>请参阅

[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CWinApp：:P arseCommandLine](../../mfc/reference/cwinapp-class.md#parsecommandline)<br/>
[CWinApp：:P rocessShellCommand](../../mfc/reference/cwinapp-class.md#processshellcommand)

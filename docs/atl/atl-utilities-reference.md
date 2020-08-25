---
title: ATL 实用程序参考
ms.date: 11/04/2016
ms.assetid: dd8a2888-34f4-461e-9bf4-834218f9b95b
ms.openlocfilehash: f9e59a2c67d391995d94d77f526613534acb48de
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831870"
---
# <a name="atl-utilities-reference"></a>ATL 实用程序参考

ATL 提供以 [CPathT](../atl/reference/cpatht-class.md) 和 [卷曲](../atl/reference/curl-class.md)形式操作路径和 url 的代码。 可以在应用程序中使用线程池 [CThreadPool](../atl/reference/cthreadpool-class.md)。 可在 atlpath.h 和 atlutil.h 中找到此代码。

## <a name="classes"></a>类

| &nbsp; | &nbsp; |
|--|--|
| [CPathT 类](../atl/reference/cpatht-class.md) | 此类表示一个路径。 |
| [CDebugReportHook 类](../atl/reference/cdebugreporthook-class.md) | 使用此类可将调试报告发送到命名管道。 |
| [CNonStatelessWorker 类](../atl/reference/cnonstatelessworker-class.md) | 接收来自线程池的请求，并将其传递到在每个请求上创建并销毁的辅助角色对象。 |
| [CNoWorkerThread 类](../atl/reference/cnoworkerthread-class.md) | 如果要禁用动态缓存维护，请使用此类作为用于 `MonitorClass` 缓存类的模板参数的参数。 |
| [CThreadPool 类](../atl/reference/cthreadpool-class.md) | 此类提供处理工作项队列的工作线程池。 |
| [CUrl 类](../atl/reference/curl-class.md) | 此类表示一个 URL。 它使您可以独立于其他元素处理 URL 的每个元素，无论是分析现有的 URL 字符串还是从头开始生成字符串。 |
| [CWorkerThread 类](../atl/reference/cworkerthread-class.md) | 此类创建一个或多个工作线程，并使用现有的工作线程，在一个或多个内核对象句柄上等待，并在其中一个句柄发出信号时执行指定的客户端函数。 |

## <a name="typedefs"></a>Typedef

| &emsp; | &emsp; |
|--|--|
| [CPath](../atl/reference/atl-typedefs.md#cpath) | 使用的 [CPathT](../atl/reference/cpatht-class.md) 的专用化 `CString` 。 |
| [CPathA](../atl/reference/atl-typedefs.md#cpatha) | 使用的 [CPathT](../atl/reference/cpatht-class.md) 的专用化 `CStringA` 。 |
| [CPathW](../atl/reference/atl-typedefs.md#cpathw) | 使用的 [CPathT](../atl/reference/cpatht-class.md) 的专用化 `CStringW` 。 |
| [ATL_URL_PORT](../atl/reference/atl-typedefs.md#atl_url_port) | 用于指定端口号的 [卷](../atl/reference/curl-class.md) 的类型。 |

## <a name="enums"></a>枚举

| &emsp; | &emsp; |
|--|--|
| [ATL_URL_SCHEME](../atl/reference/atl-url-scheme-enum.md) | 此枚举的成员为 [曲线](../atl/reference/curl-class.md)理解的方案提供常数。 |

## <a name="functions"></a>函数

| &emsp; | &emsp; |
|--|--|
| [AtlCanonicalizeUrl](../atl/reference/atl-http-utility-functions.md#atlcanonicalizeurl) | 调用此函数可对 URL 进行规范化，包括将不安全的字符和空格转换为转义序列。 |
| [AtlCombineUrl](../atl/reference/atl-http-utility-functions.md#atlcombineurl) | 调用此函数可将基 URL 和相对 URL 合并为单个规范 URL。 |
| [AtlEscapeUrl](../atl/reference/atl-http-utility-functions.md#atlescapeurl) | 调用此函数可将所有不安全字符转换为转义序列。 |
| [AtlGetDefaultUrlPort](../atl/reference/atl-http-utility-functions.md#atlgetdefaulturlport) | 调用此函数可获取与特定 internet 协议或方案关联的默认端口号。 |
| [AtlHexValue](../atl/reference/atl-text-encoding-functions.md#atlhexvalue) | 调用此函数可获取十六进制数字的数值。 |
| [AtlIsUnsafeUrlChar](../atl/reference/atl-http-utility-functions.md#atlisunsafeurlchar) | 调用此函数可了解字符在 URL 中能否安全使用。 |
| [AtlUnescapeUrl](../atl/reference/atl-http-utility-functions.md#atlunescapeurl) | 调用此函数可将转义字符转换为其原始值。 |
| [SystemTimeToHttpDate](../atl/reference/atl-http-utility-functions.md#systemtimetohttpdate) | 调用此函数可将系统时间转换为采用适合在 HTTP 标头中使用的格式的字符串。 |
| [ATLPath::AddBackslash](../atl/reference/atl-path-functions.md#addbackslash) | 此函数是 [PathAddBackslash] 的重载包装器 (/windows/desktop/api/shlwapi/nf-shlwapi-pathaddbackslasha |
| ). |
| [ATLPath::AddExtension](../atl/reference/atl-path-functions.md#addextension) | 此函数是 [PathAddExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathaddextensionw)的重载包装。 |
| [ATLPath::Append](../atl/reference/atl-path-functions.md#append) | 此函数是 [PathAppend](/windows/win32/api/shlwapi/nf-shlwapi-pathappendw)的重载包装。 |
| [ATLPath::BuildRoot](../atl/reference/atl-path-functions.md#buildroot) | 此函数是 [PathBuildRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathbuildrootw)的重载包装。 |
| [ATLPath::Canonicalize](../atl/reference/atl-path-functions.md#canonicalize) | 此函数是 [PathCanonicalize](/windows/win32/api/shlwapi/nf-shlwapi-pathcanonicalizew)的重载包装。 |
| [ATLPath::Combine](../atl/reference/atl-path-functions.md#combine) | 此函数是 [PathCombine](/windows/win32/api/shlwapi/nf-shlwapi-pathcombinew)的重载包装。 |
| [ATLPath::CommonPrefix](../atl/reference/atl-path-functions.md#commonprefix) | 此函数是 [PathCommonPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathcommonprefixw)的重载包装。 |
| [ATLPath::CompactPath](../atl/reference/atl-path-functions.md#compactpath) | 此函数是 [PathCompactPath](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathw)的重载包装。 |
| [ATLPath::CompactPathEx](../atl/reference/atl-path-functions.md#compactpathex) | 此函数是 [PathCompactPathEx](/windows/win32/api/shlwapi/nf-shlwapi-pathcompactpathexw)的重载包装。 |
| [ATLPath::FileExists](../atl/reference/atl-path-functions.md#fileexists) | 此函数是 [PathFileExists](/windows/win32/api/shlwapi/nf-shlwapi-pathfileexistsw)的重载包装。 |
| [ATLPath::FindExtension](../atl/reference/atl-path-functions.md#findextension) | 此函数是 [PathFindExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathfindextensionw)的重载包装。 |
| [ATLPath::FindFileName](../atl/reference/atl-path-functions.md#findfilename) | 此函数是 [PathFindFileName](/windows/win32/api/shlwapi/nf-shlwapi-pathfindfilenamew)的重载包装。 |
| [ATLPath::GetDriveNumber](../atl/reference/atl-path-functions.md#getdrivenumber) | 此函数是 [PathGetDriveNumber](/windows/win32/api/shlwapi/nf-shlwapi-pathgetdrivenumberw)的重载包装。 |
| [ATLPath::IsDirectory](../atl/reference/atl-path-functions.md#isdirectory) | 此函数是 [PathIsDirectory](/windows/win32/api/shlwapi/nf-shlwapi-pathisdirectoryw)的重载包装。 |
| [ATLPath::IsFileSpec](../atl/reference/atl-path-functions.md#isfilespec) | 此函数是 [PathIsFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathisfilespecw)的重载包装。 |
| [ATLPath::IsPrefix](../atl/reference/atl-path-functions.md#isprefix) | 此函数是 [PathIsPrefix](/windows/win32/api/shlwapi/nf-shlwapi-pathisprefixw)的重载包装。 |
| [ATLPath::IsRelative](../atl/reference/atl-path-functions.md#isrelative) | 此函数是 [PathIsRelative](/windows/win32/api/shlwapi/nf-shlwapi-pathisrelativew)的重载包装。 |
| [ATLPath::IsRoot](../atl/reference/atl-path-functions.md#isroot) | 此函数是 [PathIsRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathisrootw)的重载包装。 |
| [ATLPath::IsSameRoot](../atl/reference/atl-path-functions.md#issameroot) | 此函数是 [PathIsSameRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathissamerootw)的重载包装。 |
| [ATLPath::IsUNC](../atl/reference/atl-path-functions.md#isunc) | 此函数是 [PathIsUNC](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncw)的重载包装。 |
| [ATLPath::IsUNCServer](../atl/reference/atl-path-functions.md#isuncserver) | 此函数是 [PathIsUNCServer](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserverw)的重载包装。 |
| [ATLPath::IsUNCServerShare](../atl/reference/atl-path-functions.md#isuncservershare) | 此函数是 [PathIsUNCServerShare](/windows/win32/api/shlwapi/nf-shlwapi-pathisuncserversharew)的重载包装。 |
| [ATLPath::MakePretty](../atl/reference/atl-path-functions.md#makepretty) | 此函数是 [PathMakePretty](/windows/win32/api/shlwapi/nf-shlwapi-pathmakeprettyw)的重载包装。 |
| [ATLPath::MatchSpec](../atl/reference/atl-path-functions.md#matchspec) | 此函数是 [PathMatchSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathmatchspecw)的重载包装。 |
| [ATLPath::QuoteSpaces](../atl/reference/atl-path-functions.md#quotespaces) | 此函数是 [PathQuoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathquotespacesw)的重载包装。 |
| [ATLPath::RelativePathTo](../atl/reference/atl-path-functions.md#relativepathto) | 此函数是 [PathRelativePathTo](/windows/win32/api/shlwapi/nf-shlwapi-pathrelativepathtow)的重载包装。 |
| [ATLPath::RemoveArgs](../atl/reference/atl-path-functions.md#removeargs) | 此函数是 [PathRemoveArgs](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveargsw)的重载包装。 |
| [ATLPath::RemoveBackslash](../atl/reference/atl-path-functions.md#removebackslash) | 此函数是 [PathRemoveBackslash](/windows/win32/api/shlwapi/nf-shlwapi-pathremovebackslashw)的重载包装。 |
| [ATLPath::RemoveBlanks](../atl/reference/atl-path-functions.md#removeblanks) | 此函数是 [PathRemoveBlanks](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveblanksw)的重载包装。 |
| [ATLPath::RemoveExtension](../atl/reference/atl-path-functions.md#removeextension) | 此函数是 [PathRemoveExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathremoveextensionw)的重载包装。 |
| [ATLPath::RemoveFileSpec](../atl/reference/atl-path-functions.md#removefilespec) | 此函数是 [PathRemoveFileSpec](/windows/win32/api/shlwapi/nf-shlwapi-pathremovefilespecw)的重载包装。 |
| [ATLPath::RenameExtension](../atl/reference/atl-path-functions.md#renameextension) | 此函数是 [PathRenameExtension](/windows/win32/api/shlwapi/nf-shlwapi-pathrenameextensionw)的重载包装。 |
| [ATLPath::SkipRoot](../atl/reference/atl-path-functions.md#skiproot) | 此函数是 [PathSkipRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathskiprootw)的重载包装。 |
| [ATLPath::StripPath](../atl/reference/atl-path-functions.md#strippath) | 此函数是 [PathStripPath](/windows/win32/api/shlwapi/nf-shlwapi-pathstrippathw)的重载包装。 |
| [ATLPath::StripToRoot](../atl/reference/atl-path-functions.md#striptoroot) | 此函数是 [PathStripToRoot](/windows/win32/api/shlwapi/nf-shlwapi-pathstriptorootw)的重载包装。 |
| [ATLPath::UnquoteSpaces](../atl/reference/atl-path-functions.md#unquotespaces) | 此函数是 [PathUnquoteSpaces](/windows/win32/api/shlwapi/nf-shlwapi-pathunquotespacesw)的重载包装。 |

## <a name="see-also"></a>另请参阅

[概念](../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM 桌面组件](../atl/atl-com-desktop-components.md)

---
description: 详细了解：卷曲类
title: 卷类
ms.date: 05/06/2019
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
ms.openlocfilehash: e8453c4dd1abbfdcb6d794b89fd55f37d7b3f286
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140291"
---
# <a name="curl-class"></a>卷类

此类表示一个 URL。 它使您可以独立于其他元素处理 URL 的每个元素，无论是分析现有的 URL 字符串还是从头开始生成字符串。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CUrl
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[卷曲：：卷曲](#curl)|构造函数。|
|[卷曲：： ~ 卷曲](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[卷曲：：规范化](#canonicalize)|调用此方法可将 URL 字符串转换为规范格式。|
|[卷曲：： Clear](#clear)|调用此方法可清除所有 URL 字段。|
|[卷曲：： CrackUrl](#crackurl)|调用此方法可解码和分析 URL。|
|[卷曲：： CreateUrl](#createurl)|调用此方法可创建 URL。|
|[卷曲：： GetExtraInfo](#getextrainfo)|调用此方法可从 URL 中获取附加信息 (如 *文本* 或 # *text*) 。|
|[卷曲：： GetExtraInfoLength](#getextrainfolength)|调用此方法可获取要从 URL 中检索的额外信息 (如 *文本* 或 # *text*) 的长度。|
|[卷曲：： GetHostName](#gethostname)|调用此方法可从 URL 获取主机名。|
|[卷曲：： GetHostNameLength](#gethostnamelength)|调用此方法可获取主机名的长度。|
|[卷曲：： GetPassword](#getpassword)|调用此方法可从 URL 获取密码。|
|[卷曲：： GetPasswordLength](#getpasswordlength)|调用此方法可获取密码的长度。|
|[卷曲：： GetPortNumber](#getportnumber)|调用此方法以根据 ATL_URL_PORT 获取端口号。|
|[卷曲：： GetScheme](#getscheme)|调用此方法以获取 URL 方案。|
|[卷曲：： GetSchemeName](#getschemename)|调用此方法以获取 URL 方案名称。|
|[卷曲：： GetSchemeNameLength](#getschemenamelength)|调用此方法可获取 URL 方案名称的长度。|
|[卷曲：： GetUrlLength](#geturllength)|调用此方法以获取 URL 长度。|
|[卷曲：： GetUrlPath](#geturlpath)|调用此方法可获取 URL 路径。|
|[卷曲：： GetUrlPathLength](#geturlpathlength)|调用此方法可获取 URL 路径长度。|
|[卷曲：： GetUserName](#getusername)|调用此方法可从 URL 获取用户名。|
|[卷曲：： GetUserNameLength](#getusernamelength)|调用此方法可获取用户名的长度。|
|[卷曲：： SetExtraInfo](#setextrainfo)|调用此方法可设置附加信息 (如 URL 的 *文本* 或 # *text*) 。|
|[卷曲：： SetHostName](#sethostname)|调用此方法以设置主机名。|
|[卷曲：： SetPassword](#setpassword)|调用此方法以设置密码。|
|[卷曲：： SetPortNumber](#setportnumber)|调用此方法以根据 ATL_URL_PORT 设置端口号。|
|[卷曲：： SetScheme](#setscheme)|调用此方法可设置 URL 方案。|
|[卷曲：： SetSchemeName](#setschemename)|调用此方法可设置 URL 方案名称。|
|[卷曲：： SetUrlPath](#seturlpath)|调用此方法可设置 URL 路径。|
|[卷曲：： SetUserName](#setusername)|调用此方法可设置用户名。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[卷曲：： operator =](#operator_eq)|将指定的 `CUrl` 对象分配给当前 `CUrl` 对象。|

## <a name="remarks"></a>备注

`CUrl` 允许操作 URL 的字段，如路径或端口号。 `CUrl` 了解以下格式的 Url：

\<Scheme>://\<UserName>:\<Password>\@\<HostName>:\<PortNumber>/\<UrlPath>\<ExtraInfo>

 (一些字段是可选的。 ) 例如，请看下面的 URL：

`http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents`

[卷曲：： CrackUrl](#crackurl) 对其进行分析，如下所示：

- 方案： "http" 或 [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- 用户名： "某人"

- 密码： "secret"

- 主机名： " `www.microsoft.com` "

- PortNumber：80

- UrlPath： "visualc/stuff.htm"

- ExtraInfo： "#contents"

若要操作 UrlPath 字段 (例如) ，请使用 [GetUrlPath](#geturlpath)、 [GetUrlPathLength](#geturlpathlength)和 [SetUrlPath](#seturlpath)。 您将使用 [CreateUrl](#createurl) 创建完整的 URL 字符串。

## <a name="requirements"></a>要求

**标头：** atlutil

## <a name="curlcanonicalize"></a><a name="canonicalize"></a> 卷曲：：规范化

调用此方法可将 URL 字符串转换为规范格式。

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>parameters

dwFlags <br/>
控制规范化的标志。 如果未指定 *dwFlags* = 0)  (标志，则方法会将所有不安全字符和元 (序列（如 \\ .、\ ... 和 \\ ... ) ）转换为转义序列。 *dwFlags* 可以是下列值之一：

- ATL_URL_BROWSER_MODE：在 "#" 或 "" 后不会对字符进行编码或解码，并且不会删除 "" 后的尾随空格。 如果未指定此值，则会对整个 URL 进行编码，并删除尾随空格。

- ATL_URL _DECODE：分析 URL 之前，将所有% XX 序列转换为字符，包括转义序列。

- ATL_URL _ENCODE_PERCENT：对遇到的任何百分号进行编码。 默认情况下，不对百分号进行编码。

- ATL_URL _ENCODE_SPACES_ONLY：仅对空格进行编码。

- ATL_URL _NO_ENCODE：不将不安全字符转换为转义序列。

- ATL_URL _NO_META：不删除元序列 (如 "." 和 ".."从 URL ) 。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

转换为规范形式涉及到将不安全字符和空格转换为转义序列。

## <a name="curlclear"></a><a name="clear"></a> 卷曲：： Clear

调用此方法可清除所有 URL 字段。

```
inline void Clear() throw();
```

## <a name="curlcrackurl"></a><a name="crackurl"></a> 卷曲：： CrackUrl

调用此方法可解码和分析 URL。

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>parameters

*lpszUrl*<br/>
URL。

dwFlags <br/>
指定 ATL_URL_DECODE 或 ATL_URL_ESCAPE 在分析后将 *lpszUrl* 中的所有转义字符转换为其实际值。  (Visual C++ 2005 之前，ATL_URL_DECODE 在分析之前转换所有转义符。 ) 

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="curlcreateurl"></a><a name="createurl"></a> 卷曲：： CreateUrl

此方法从卷对象的组件字段中构造一个 URL 字符串。

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>parameters

*lpszUrl*<br/>
用于保存完整 URL 字符串的字符串缓冲区。

*pdwMaxLength*<br/>
*LpszUrl* 字符串缓冲区的最大长度。

dwFlags <br/>
指定 ATL_URL_ESCAPE 将 *lpszUrl* 中的所有转义字符转换为其实际值。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

此方法将追加其各个字段，以便使用以下格式构造完整的 URL 字符串：

**\<scheme>://\<user>:\<pass>\@\<domain>:\<port>\<path>\<extra>**

调用此方法时， *pdwMaxLength* 参数最初应包含 *lpszUrl* 参数引用的字符串缓冲区的最大长度。 *PdwMaxLength* 参数的值将更新为包含 URL 字符串的实际长度。

### <a name="example"></a>示例

此示例演示如何创建卷对象并检索其 URL 字符串

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

## <a name="curlcurl"></a><a name="curl"></a> 卷曲：：卷曲

构造函数。

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>parameters

*Url*<br/>
要 `CUrl` 复制以创建 URL 的对象。

## <a name="curlcurl"></a><a name="dtor"></a> 卷曲：： ~ 卷曲

析构函数。

```
~CUrl() throw();
```

## <a name="curlgetextrainfo"></a><a name="getextrainfo"></a> 卷曲：： GetExtraInfo

调用此方法可从 URL 中获取附加信息 (如 *文本* 或 # *text*) 。

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>返回值

返回包含附加信息的字符串。

## <a name="curlgetextrainfolength"></a><a name="getextrainfolength"></a> 卷曲：： GetExtraInfoLength

调用此方法可获取要从 URL 中检索的额外信息 (如 *文本* 或 # *text*) 的长度。

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>返回值

返回包含附加信息的字符串的长度。

## <a name="curlgethostname"></a><a name="gethostname"></a> 卷曲：： GetHostName

调用此方法可从 URL 获取主机名。

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>返回值

返回主机名。

## <a name="curlgethostnamelength"></a><a name="gethostnamelength"></a> 卷曲：： GetHostNameLength

调用此方法可获取主机名的长度。

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>返回值

返回主机名称长度。

## <a name="curlgetpassword"></a><a name="getpassword"></a> 卷曲：： GetPassword

调用此方法可从 URL 获取密码。

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>返回值

返回密码。

## <a name="curlgetpasswordlength"></a><a name="getpasswordlength"></a> 卷曲：： GetPasswordLength

调用此方法可获取密码的长度。

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>返回值

返回密码长度。

## <a name="curlgetportnumber"></a><a name="getportnumber"></a> 卷曲：： GetPortNumber

调用此方法以获取端口号。

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>返回值

返回端口号。

## <a name="curlgetscheme"></a><a name="getscheme"></a> 卷曲：： GetScheme

调用此方法以获取 URL 方案。

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>返回值

返回描述 URL 方案的 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 值。

## <a name="curlgetschemename"></a><a name="getschemename"></a> 卷曲：： GetSchemeName

调用此方法以获取 URL 方案名称。

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>返回值

返回 URL 方案名称 (如 "http" 或 "ftp" ) 。

## <a name="curlgetschemenamelength"></a><a name="getschemenamelength"></a> 卷曲：： GetSchemeNameLength

调用此方法可获取 URL 方案名称的长度。

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>返回值

返回 URL 方案名称长度。

## <a name="curlgeturllength"></a><a name="geturllength"></a> 卷曲：： GetUrlLength

调用此方法以获取 URL 长度。

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>返回值

返回 URL 长度。

## <a name="curlgeturlpath"></a><a name="geturlpath"></a> 卷曲：： GetUrlPath

调用此方法可获取 URL 路径。

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>返回值

返回 URL 路径。

## <a name="curlgeturlpathlength"></a><a name="geturlpathlength"></a> 卷曲：： GetUrlPathLength

调用此方法可获取 URL 路径长度。

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>返回值

返回 URL 路径长度。

## <a name="curlgetusername"></a><a name="getusername"></a> 卷曲：： GetUserName

调用此方法可从 URL 获取用户名。

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>返回值

返回用户名。

## <a name="curlgetusernamelength"></a><a name="getusernamelength"></a> 卷曲：： GetUserNameLength

调用此方法可获取用户名的长度。

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>返回值

返回用户名称长度。

## <a name="curloperator-"></a><a name="operator_eq"></a> 卷曲：： operator =

将指定的 `CUrl` 对象分配给当前 `CUrl` 对象。

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>parameters

*Url*<br/>
`CUrl`要复制到当前对象中的对象。

### <a name="return-value"></a>返回值

返回对当前对象的引用。

## <a name="curlsetextrainfo"></a><a name="setextrainfo"></a> 卷曲：： SetExtraInfo

调用此方法可设置附加信息 (如 URL 的 *文本* 或 # *text*) 。

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>parameters

*lpszInfo*<br/>
包含要包括在 URL 中的额外信息的字符串。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="curlsethostname"></a><a name="sethostname"></a> 卷曲：： SetHostName

调用此方法以设置主机名。

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>parameters

*lpszHost*<br/>
主机名。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="curlsetpassword"></a><a name="setpassword"></a> 卷曲：： SetPassword

调用此方法以设置密码。

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>parameters

*lpszPass*<br/>
密码。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="curlsetportnumber"></a><a name="setportnumber"></a> 卷曲：： SetPortNumber

调用此方法可设置端口号。

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>parameters

*nPrt*<br/>
端口号。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="curlsetscheme"></a><a name="setscheme"></a> 卷曲：： SetScheme

调用此方法可设置 URL 方案。

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>parameters

*nScheme*<br/>
方案 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 值之一。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

还可以按名称设置方案 (参阅 " [卷：： SetSchemeName](#setschemename)) "。

## <a name="curlsetschemename"></a><a name="setschemename"></a> 卷曲：： SetSchemeName

调用此方法可设置 URL 方案名称。

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>parameters

*lpszSchm*<br/>
URL 方案名称。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

还可以通过使用 [ATL_URL_SCHEME](atl-url-scheme-enum.md) 常量来设置方案 (请参阅 [卷：： SetScheme](#setscheme)) 。

## <a name="curlseturlpath"></a><a name="seturlpath"></a> 卷曲：： SetUrlPath

调用此方法可设置 URL 路径。

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>parameters

*lpszPath*<br/>
URL 路径。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="curlsetusername"></a><a name="setusername"></a> 卷曲：： SetUserName

调用此方法可设置用户名。

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>parameters

*lpszUser*<br/>
用户名。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="see-also"></a>请参阅

[类](../../atl/reference/atl-classes.md)

---
description: 了解详细信息： CTokenPrivileges 类
title: CTokenPrivileges 类
ms.date: 11/04/2016
f1_keywords:
- CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::CTokenPrivileges
- ATLSECURITY/ATL::CTokenPrivileges::Add
- ATLSECURITY/ATL::CTokenPrivileges::Delete
- ATLSECURITY/ATL::CTokenPrivileges::DeleteAll
- ATLSECURITY/ATL::CTokenPrivileges::GetCount
- ATLSECURITY/ATL::CTokenPrivileges::GetDisplayNames
- ATLSECURITY/ATL::CTokenPrivileges::GetLength
- ATLSECURITY/ATL::CTokenPrivileges::GetLuidsAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetNamesAndAttributes
- ATLSECURITY/ATL::CTokenPrivileges::GetPTOKEN_PRIVILEGES
- ATLSECURITY/ATL::CTokenPrivileges::LookupPrivilege
helpviewer_keywords:
- CTokenPrivileges class
ms.assetid: 89590105-f001-4014-870d-142926091231
ms.openlocfilehash: 22953c0d2aa8c4fa7dd0b79b001e46797bd3ca25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140304"
---
# <a name="ctokenprivileges-class"></a>CTokenPrivileges 类

此类是结构的包装器 `TOKEN_PRIVILEGES` 。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CTokenPrivileges
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CTokenPrivileges::CTokenPrivileges](#ctokenprivileges)|构造函数。|
|[CTokenPrivileges：： ~ CTokenPrivileges](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTokenPrivileges：： Add](#add)|向对象添加一个或多个权限 `CTokenPrivileges` 。|
|[CTokenPrivileges：:D e) ](#delete)|从对象中删除特权 `CTokenPrivileges` 。|
|[CTokenPrivileges：:D eleteAll](#deleteall)|删除对象中的所有特权 `CTokenPrivileges` 。|
|[CTokenPrivileges：： GetCount](#getcount)|返回对象中的特权项的数目 `CTokenPrivileges` 。|
|[CTokenPrivileges::GetDisplayNames](#getdisplaynames)|检索对象中包含的权限的显示名称 `CTokenPrivileges` 。|
|[CTokenPrivileges：： GetLength](#getlength)|返回保存对象所代表的结构所需的缓冲区大小（以字节为单位） `TOKEN_PRIVILEGES` `CTokenPrivileges` 。|
|[CTokenPrivileges::GetLuidsAndAttributes](#getluidsandattributes)|从对象中检索 (Luid) 和特性标志的本地唯一标识符 `CTokenPrivileges` 。|
|[CTokenPrivileges::GetNamesAndAttributes](#getnamesandattributes)|从对象中检索权限名称和特性标志 `CTokenPrivileges` 。|
|[CTokenPrivileges：： GetPTOKEN_PRIVILEGES](#getptoken_privileges)|返回指向结构的指针 `TOKEN_PRIVILEGES` 。|
|[CTokenPrivileges::LookupPrivilege](#lookupprivilege)|检索与给定的特权名称关联的特性。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CTokenPrivileges：： operator const TOKEN_PRIVILEGES *](#operator_const_token_privileges__star)|将值强制转换为指向结构的指针 `TOKEN_PRIVILEGES` 。|
|[CTokenPrivileges：： operator =](#operator_eq)|赋值运算符。|

## <a name="remarks"></a>备注

[访问令牌](/windows/win32/SecAuthZ/access-tokens)是一个对象，该对象描述进程或线程的安全上下文，并分配给登录到 Windows 系统的每个用户。

访问令牌用于描述授予每个用户的各种安全权限。 权限由64位数字组成，该数字称为本地唯一标识符 ( [LUID](/windows/win32/api/winnt/ns-winnt-luid)) 和描述符字符串。

`CTokenPrivileges`类是[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)结构的包装，包含0个或多个权限。 可以使用提供的类方法添加、删除或查询权限。

有关 Windows 中的访问控制模型的简介，请参阅 Windows SDK 中的 [访问控制](/windows/win32/SecAuthZ/access-control) 。

## <a name="requirements"></a>要求

**标头：** atlsecurity。h

## <a name="ctokenprivilegesadd"></a><a name="add"></a> CTokenPrivileges：： Add

将一个或多个权限添加到 `CTokenPrivileges` 访问令牌对象中。

```
bool Add(LPCTSTR pszPrivilege, bool bEnable) throw(...);
void Add(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>parameters

*pszPrivilege*<br/>
指向以 null 结尾的字符串的指针，该字符串指定了在 WINNT 中定义的特权的名称。H 标头文件。

*bEnable*<br/>
如果为 true，则启用特权。 如果为 false，则禁用特权。

*rPrivileges*<br/>
对 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 结构的引用。 将从该结构中复制权限和属性，并将其添加到 `CTokenPrivileges` 对象。

### <a name="return-value"></a>返回值

如果成功添加了权限，则此方法的第一种形式将返回 true，否则返回 false。

## <a name="ctokenprivilegesctokenprivileges"></a><a name="ctokenprivileges"></a> CTokenPrivileges::CTokenPrivileges

构造函数。

```
CTokenPrivileges() throw();
CTokenPrivileges(const CTokenPrivileges& rhs) throw(... );
CTokenPrivileges(const TOKEN_PRIVILEGES& rPrivileges) throw(...);
```

### <a name="parameters"></a>parameters

*rhs*<br/>
`CTokenPrivileges`要分配给新对象的对象。

*rPrivileges*<br/>
要分配给新对象的 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 结构 `CTokenPrivileges` 。

### <a name="remarks"></a>备注

`CTokenPrivileges`可以选择使用 `TOKEN_PRIVILEGES` 结构或以前定义的对象来创建对象 `CTokenPrivileges` 。

## <a name="ctokenprivilegesctokenprivileges"></a><a name="dtor"></a> CTokenPrivileges：： ~ CTokenPrivileges

析构函数。

```
virtual ~CTokenPrivileges() throw();
```

### <a name="remarks"></a>备注

析构函数释放所有已分配的资源。

## <a name="ctokenprivilegesdelete"></a><a name="delete"></a> CTokenPrivileges：:D e) 

从 `CTokenPrivileges` 访问令牌对象中删除特权。

```
bool Delete(LPCTSTR pszPrivilege) throw();
```

### <a name="parameters"></a>parameters

*pszPrivilege*<br/>
指向以 null 结尾的字符串的指针，该字符串指定了在 WINNT 中定义的特权的名称。H 标头文件。 例如，此参数可以指定常量 SE_SECURITY_NAME 或其对应的字符串 "SeSecurityPrivilege"。

### <a name="return-value"></a>返回值

如果已成功删除特权，则返回 true，否则返回 false。

### <a name="remarks"></a>备注

此方法可用作创建受限令牌的工具。

## <a name="ctokenprivilegesdeleteall"></a><a name="deleteall"></a> CTokenPrivileges：:D eleteAll

删除访问令牌对象中的所有特权 `CTokenPrivileges` 。

```cpp
void DeleteAll() throw();
```

### <a name="remarks"></a>备注

删除访问令牌对象中包含的所有特权 `CTokenPrivileges` 。

## <a name="ctokenprivilegesgetdisplaynames"></a><a name="getdisplaynames"></a> CTokenPrivileges::GetDisplayNames

检索访问令牌对象中包含的权限的显示名称 `CTokenPrivileges` 。

```cpp
void GetDisplayNames(CNames* pDisplayNames) const throw(...);
```

### <a name="parameters"></a>parameters

*pDisplayNames*<br/>
指向 `CString` 对象的数组的指针。 `CNames` 定义为 typedef： `CTokenPrivileges::CAtlArray<CString>` 。

### <a name="remarks"></a>备注

参数 `pDisplayNames` 是指向对象数组的指针， `CString` 这些对象将接收与对象中包含的权限相对应的显示名称 `CTokenPrivileges` 。 此方法仅检索在 WINNT 的 "定义的权限" 部分中指定的特权的显示名称。

此方法检索可显示名称：例如，如果 SE_REMOTE_SHUTDOWN_NAME 属性名称，则可显示名称为 "从远程系统强制关机"。 若要获取系统名称，请使用 [CTokenPrivileges：： GetNamesAndAttributes](#getnamesandattributes)。

## <a name="ctokenprivilegesgetcount"></a><a name="getcount"></a> CTokenPrivileges：： GetCount

返回对象中的特权项的数目 `CTokenPrivileges` 。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>返回值

返回对象中包含的特权的数目 `CTokenPrivileges` 。

## <a name="ctokenprivilegesgetlength"></a><a name="getlength"></a> CTokenPrivileges：： GetLength

返回对象的长度 `CTokenPrivileges` 。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>返回值

返回保存对象所代表的结构所需的字节数 `TOKEN_PRIVILEGES` `CTokenPrivileges` ，包括它包含的所有权限项。

## <a name="ctokenprivilegesgetluidsandattributes"></a><a name="getluidsandattributes"></a> CTokenPrivileges::GetLuidsAndAttributes

从对象中检索 (Luid) 和特性标志的本地唯一标识符 `CTokenPrivileges` 。

```cpp
void GetLuidsAndAttributes(
    CLUIDArray* pPrivileges,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>parameters

*pPrivileges*<br/>
指向 [LUID](/windows/win32/api/winnt/ns-winnt-luid) 对象的数组的指针。 `CLUIDArray` 是一个定义为的 typedef `CAtlArray<LUID> CLUIDArray` 。

*pAttributes*<br/>
指向 DWORD 对象的数组的指针。 如果省略此参数或为 NULL，则不检索特性。 `CAttributes` 是一个定义为的 typedef `CAtlArray <DWORD> CAttributes` 。

### <a name="remarks"></a>备注

此方法将枚举访问令牌对象中包含的所有权限 `CTokenPrivileges` ，并将各 luid 和 (（可选）) 特性标志合并为数组对象。

## <a name="ctokenprivilegesgetnamesandattributes"></a><a name="getnamesandattributes"></a> CTokenPrivileges::GetNamesAndAttributes

从对象中检索名称和特性标志 `CTokenPrivileges` 。

```cpp
void GetNamesAndAttributes(
    CNames* pNames,
    CAttributes* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>parameters

*pNames*<br/>
指向对象的数组的指针 `CString` 。 `CNames` 是一个定义为的 typedef `CAtlArray <CString> CNames` 。

*pAttributes*<br/>
指向 DWORD 对象的数组的指针。 如果省略此参数或为 NULL，则不检索特性。 `CAttributes` 是一个定义为的 typedef `CAtlArray <DWORD> CAttributes` 。

### <a name="remarks"></a>备注

此方法将枚举对象中包含的所有权限 `CTokenPrivileges` ，并将该名称和 (（可选）) 特性标志写入数组对象。

此方法检索属性名称，而不是可显示名称：例如，如果 SE_REMOTE_SHUTDOWN_NAME 属性名称，则系统名称为 "SeRemoteShutdownPrivilege"。 若要获取可显示名称，请使用方法 [CTokenPrivileges：： GetDisplayNames](#getdisplaynames)。

## <a name="ctokenprivilegesgetptoken_privileges"></a><a name="getptoken_privileges"></a> CTokenPrivileges：： GetPTOKEN_PRIVILEGES

返回指向结构的指针 `TOKEN_PRIVILEGES` 。

```
const TOKEN_PRIVILEGES* GetPTOKEN_PRIVILEGES() const throw(...);
```

### <a name="return-value"></a>返回值

返回指向 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 结构的指针。

## <a name="ctokenprivilegeslookupprivilege"></a><a name="lookupprivilege"></a> CTokenPrivileges::LookupPrivilege

检索与给定的特权名称关联的特性。

```
bool LookupPrivilege(
    LPCTSTR pszPrivilege,
    DWORD* pdwAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>parameters

*pszPrivilege*<br/>
指向以 null 结尾的字符串的指针，该字符串指定了在 WINNT 中定义的特权的名称。H 标头文件。 例如，此参数可以指定常量 SE_SECURITY_NAME 或其对应的字符串 "SeSecurityPrivilege"。

*pdwAttributes*<br/>
指向接收特性的变量的指针。

### <a name="return-value"></a>返回值

如果成功检索属性，则返回 true，否则返回 false。

## <a name="ctokenprivilegesoperator-"></a><a name="operator_eq"></a> CTokenPrivileges：： operator =

赋值运算符。

```
CTokenPrivileges& operator= (const TOKEN_PRIVILEGES& rPrivileges) throw(...);
CTokenPrivileges& operator= (const CTokenPrivileges& rhs) throw(...);
```

### <a name="parameters"></a>parameters

*rPrivileges*<br/>
要分配给对象的 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 结构 `CTokenPrivileges` 。

*rhs*<br/>
`CTokenPrivileges`要分配给对象的对象。

### <a name="return-value"></a>返回值

返回已更新的 `CTokenPrivileges` 对象。

## <a name="ctokenprivilegesoperator-const-token_privileges-"></a><a name="operator_const_token_privileges__star"></a> CTokenPrivileges：： operator const TOKEN_PRIVILEGES \*

将值强制转换为指向结构的指针 `TOKEN_PRIVILEGES` 。

```
operator const TOKEN_PRIVILEGES *() const throw(...);
```

### <a name="remarks"></a>备注

将一个值转换为指向 [TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges) 结构的指针。

## <a name="see-also"></a>请参阅

[安全示例](../../overview/visual-cpp-samples.md)<br/>
[TOKEN_PRIVILEGES](/windows/win32/api/winnt/ns-winnt-token_privileges)<br/>
[LUID](/windows/win32/api/winnt/ns-winnt-luid)<br/>
[LUID_AND_ATTRIBUTES](/windows/win32/api/winnt/ns-winnt-luid_and_attributes)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[安全全局函数](../../atl/reference/security-global-functions.md)

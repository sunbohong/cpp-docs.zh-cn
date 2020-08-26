---
title: CSid 类
ms.date: 03/27/2019
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
ms.openlocfilehash: b6787c0e3f075935f19d51aa73bbd66da9cc0fcb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835592"
---
# <a name="csid-class"></a>CSid 类

此类是 `SID` (安全标识符) 结构的包装器。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CSid
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|说明|
|----------|-----------------|
|[CSid：： CSidArray](#csidarray)|一个 `CSid` 对象数组。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|----------|-----------------|
|[CSid：： CSid](#csid)|构造函数。|
|[CSid：： ~ CSid](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|说明|
|----------|-----------------|
|[CSid：： AccountName](#accountname)|返回与对象关联的帐户的名称 `CSid` 。|
|[CSid：:D omain](#domain)|返回与对象关联的域的名称 `CSid` 。|
|[CSid：： EqualPrefix](#equalprefix)|测试 `SID` (安全标识符) 前缀是否相等。|
|[CSid：： GetLength](#getlength)|返回对象的长度 `CSid` 。|
|[CSid：： GetPSID](#getpsid)|返回指向结构的指针 `SID` 。|
|[CSid：： GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|返回指向结构的指针 `SID_IDENTIFIER_AUTHORITY` 。|
|[CSid：： GetSubAuthority](#getsubauthority)|返回结构中指定的 subauthority `SID` 。|
|[CSid：： GetSubAuthorityCount](#getsubauthoritycount)|返回 subauthority 计数。|
|[CSid：： IsValid](#isvalid)|测试 `CSid` 对象的有效性。|
|[CSid：： LoadAccount](#loadaccount)|根据 `CSid` 给定的帐户名和域或现有结构来更新对象 `SID` 。|
|[CSid：： Sid](#sid)|返回 ID 字符串。|
|[CSid：： SidNameUse](#sidnameuse)|返回对象状态的说明 `CSid` 。|

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator =](#operator_eq)|赋值运算符。|
|[operator const SID *](#operator_const_sid__star)|将对象强制转换为指向 `CSid` 结构的指针 `SID` 。|

### <a name="global-operators"></a>全局运算符

|名称|说明|
|-|-|
|[operator = =](#operator_eq_eq)|测试两个安全描述符对象是否相等|
|[operator！ =](#operator_neq)|测试两个安全描述符对象是否不相等|
|[操作员 \<](#operator_lt)|比较两个安全描述符对象的相对值。|
|[运算符 >](#operator_gt)|比较两个安全描述符对象的相对值。|
|[操作员 \<=](#operator_lt__eq)|比较两个安全描述符对象的相对值。|
|[运算符 >=](#operator_gt__eq)|比较两个安全描述符对象的相对值。|

## <a name="remarks"></a>注解

`SID`结构是用于唯一标识用户或组的可变长度结构。

应用程序不应 `SID` 直接修改结构，而是使用此包装类中提供的方法。 另请参阅 [AtlGetOwnerSid](security-global-functions.md#atlgetownersid)、 [AtlSetGroupSid](security-global-functions.md#atlsetgroupsid)、 [AtlGetGroupSid](security-global-functions.md#atlgetgroupsid)和 [AtlSetOwnerSid](security-global-functions.md#atlsetownersid)。

有关 Windows 中的访问控制模型的简介，请参阅 Windows SDK 中的 [访问控制](/windows/win32/SecAuthZ/access-control) 。

## <a name="requirements"></a>要求

**标头：** atlsecurity。h

## <a name="csidaccountname"></a><a name="accountname"></a> CSid：： AccountName

返回与对象关联的帐户的名称 `CSid` 。

```
LPCTSTR AccountName() const throw(...);
```

### <a name="return-value"></a>返回值

返回指向帐户名称的 LPCTSTR。

### <a name="remarks"></a>注解

此方法尝试查找指定 `SID` (安全标识符) 的名称。 有关完整详细信息，请参阅 [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)。

如果找不到的帐户名称 `SID` ，则 `AccountName` 返回一个空字符串。 如果网络超时使此方法无法找到该名称，则会发生这种情况。 对于没有对应帐户名称的安全标识符（如标识登录会话的），也会发生此错误 `SID` 。

## <a name="csidcsid"></a><a name="csid"></a> CSid：： CSid

构造函数。

```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>参数

*rhs*<br/>
`CSid`) 结构的现有对象或 `SID` (安全标识符。

*IdentifierAuthority*<br/>
颁发机构。

*nSubAuthorityCount*<br/>
Subauthority 计数。

*pszAccountName*<br/>
帐户名称。

*pszSystem*<br/>
系统名称。 此字符串可以是远程计算机的名称。 如果此字符串为 NULL，则改为使用本地系统。

*pSid*<br/>
指向结构的指针 `SID` 。

### <a name="remarks"></a>注解

构造函数初始化 `CSid` 对象，将内部数据成员设置为 *SidTypeInvalid*，或者从现有 `CSid` 的、 `SID` 或现有帐户复制设置。

如果初始化失败，则构造函数将引发 [CAtlException 类](../../atl/reference/catlexception-class.md)。

## <a name="csidcsid"></a><a name="dtor"></a> CSid：： ~ CSid

析构函数。

```
virtual ~CSid() throw();
```

### <a name="remarks"></a>注解

析构函数释放由该对象获取的任何资源。

## <a name="csidcsidarray"></a><a name="csidarray"></a> CSid：： CSidArray

[CSid](../../atl/reference/csid-class.md)对象的数组。

```
typedef CAtlArray<CSid> CSidArray;
```

### <a name="remarks"></a>注解

此 typedef 指定可用于从 ACL (访问控制列表) 检索安全标识符的数组类型。 请参阅 [CAcl：： GetAclEntries](../../atl/reference/cacl-class.md#getaclentries)。

## <a name="csiddomain"></a><a name="domain"></a> CSid：:D omain

返回与对象关联的域的名称 `CSid` 。

```
LPCTSTR Domain() const throw(...);
```

### <a name="return-value"></a>返回值

返回 `LPCTSTR` 指向域的。

### <a name="remarks"></a>注解

此方法尝试查找指定 `SID` (安全标识符) 的名称。 有关完整详细信息，请参阅 [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw)。

如果找不到的帐户名称 `SID` ，则会将 `Domain` 该域作为空字符串返回。 如果网络超时使此方法无法找到该名称，则会发生这种情况。 对于没有对应帐户名称的安全标识符（如标识登录会话的），也会发生此错误 `SID` 。

## <a name="csidequalprefix"></a><a name="equalprefix"></a> CSid：： EqualPrefix

测试 `SID` (安全标识符) 前缀是否相等。

```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```

### <a name="parameters"></a>参数

*rhs*<br/>
`SID`要比较的 (安全标识符) 结构或 `CSid` 对象。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>注解

有关更多详细信息，请参阅 Windows SDK 中的 [EqualPrefixSid](/windows/win32/api/securitybaseapi/nf-securitybaseapi-equalprefixsid) 。

## <a name="csidgetlength"></a><a name="getlength"></a> CSid：： GetLength

返回对象的长度 `CSid` 。

```
UINT GetLength() const throw();
```

### <a name="return-value"></a>返回值

返回对象的长度（以字节为单位） `CSid` 。

### <a name="remarks"></a>注解

如果 `CSid` 结构无效，则返回值不确定。 在调用之前 `GetLength` ，请使用 [CSid：： IsValid](#isvalid) 成员函数验证 `CSid` 是否有效。

> [!NOTE]
> 在调试版本中，如果对象无效，则该函数将导致断言 `CSid` 。

## <a name="csidgetpsid"></a><a name="getpsid"></a> CSid：： GetPSID

返回指向 `SID` (安全标识符) 结构的指针。

```
const SID* GetPSID() const throw(...);
```

### <a name="return-value"></a>返回值

返回 `CSid` 对象的基础结构的地址 `SID` 。

## <a name="csidgetpsid_identifier_authority"></a><a name="getpsid_identifier_authority"></a> CSid：： GetPSID_IDENTIFIER_AUTHORITY

返回指向结构的指针 `SID_IDENTIFIER_AUTHORITY` 。

```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```

### <a name="return-value"></a>返回值

如果该方法成功，它将返回结构的地址 `SID_IDENTIFIER_AUTHORITY` 。 如果失败，则返回值为 undefined。 如果对象无效，则可能会发生故障 `CSid` ，在这种情况下， [CSid：： IsValid](#isvalid) 方法返回 FALSE。 `GetLastError`可为扩展错误信息调用函数。

> [!NOTE]
> 在调试版本中，如果对象无效，则该函数将导致断言 `CSid` 。

## <a name="csidgetsubauthority"></a><a name="getsubauthority"></a> CSid：： GetSubAuthority

返回 `SID` (安全标识符) 结构中指定的 subauthority。

```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```

### <a name="parameters"></a>参数

*nSubAuthority*<br/>
Subauthority。

### <a name="return-value"></a>返回值

返回由 NSubAuthority 引用的 subauthority *。* Subauthority 值是 RID)  (的相对标识符。

### <a name="remarks"></a>注解

*NSubAuthority*参数指定一个索引值，用于标识该方法将返回的 subauthority 数组元素。 方法不对此值执行验证测试。 应用程序可以调用 [CSid：： GetSubAuthorityCount](#getsubauthoritycount) 来发现可接受值的范围。

> [!NOTE]
> 在调试版本中，如果对象无效，则该函数将导致断言 `CSid` 。

## <a name="csidgetsubauthoritycount"></a><a name="getsubauthoritycount"></a> CSid：： GetSubAuthorityCount

返回 subauthority 计数。

```
UCHAR GetSubAuthorityCount() const throw();
```

### <a name="return-value"></a>返回值

如果该方法成功，则返回值为 subauthority 计数。

如果该方法失败，则返回值为 undefined。 如果对象无效，则方法将失败 `CSid` 。 若要获得扩展的错误信息，请调用 `GetLastError`。

> [!NOTE]
> 在调试版本中，如果对象无效，则该函数将导致断言 `CSid` 。

## <a name="csidisvalid"></a><a name="isvalid"></a> CSid：： IsValid

测试 `CSid` 对象的有效性。

```
bool IsValid() const throw();
```

### <a name="return-value"></a>返回值

如果 `CSid` 对象有效，则返回 TRUE，否则返回 FALSE。 此方法没有扩展的错误信息;不要调用 `GetLastError` 。

### <a name="remarks"></a>注解

`IsValid`方法 `CSid` 通过验证修订号是否在已知范围内并且 subauthorities 数小于最大值来验证对象。

## <a name="csidloadaccount"></a><a name="loadaccount"></a> CSid：： LoadAccount

根据 `CSid` 给定的帐户名和域或现有 SID (安全标识符) 结构来更新对象。

```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```

### <a name="parameters"></a>参数

*pszAccountName*<br/>
帐户名称。

*pszSystem*<br/>
系统名称。 此字符串可以是远程计算机的名称。 如果此字符串为 NULL，则改为使用本地系统。

*pSid*<br/>
指向 [SID](/windows/win32/api/winnt/ns-winnt-sid) 结构的指针。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。 若要获得扩展的错误信息，请调用 `GetLastError`。

### <a name="remarks"></a>注解

`LoadAccount` 尝试查找指定名称的安全标识符。 有关更多详细信息，请参阅 [LookupAccountSid](/windows/win32/api/winbase/nf-winbase-lookupaccountsidw) 。

## <a name="csidoperator-"></a><a name="operator_eq"></a> CSid：： operator =

赋值运算符。

```
CSid& operator= (const CSid& rhs) throw(...);
CSid& operator= (const SID& rhs) throw(...);
```

### <a name="parameters"></a>参数

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 分配给 `CSid` 对象。

### <a name="return-value"></a>返回值

返回对已更新的对象的引用 `CSid` 。

## <a name="csidoperator-"></a><a name="operator_eq_eq"></a> CSid：： operator = =

测试两个安全描述符对象是否相等。

```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>参数

*lhs*<br/>
`SID` (安全标识符) 或 `CSid` 显示在 = = 运算符的左侧。

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 出现在 = = 运算符的右侧。

### <a name="return-value"></a>返回值

如果安全描述符相等，则为 TRUE; 否则为 FALSE。

## <a name="csidoperator-"></a><a name="operator_neq"></a> CSid：： operator！ =

测试两个安全描述符对象是否不相等。

```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>参数

*lhs*<br/>
`SID` (安全标识符) 或 `CSid` 显示在！ = 运算符的左侧。

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 出现在！ = 运算符右侧的。

### <a name="return-value"></a>返回值

如果安全描述符不相等，则为 TRUE; 否则为 FALSE。

## <a name="csidoperator-lt"></a><a name="operator_lt"></a> CSid：：运算符 &lt;

比较两个安全描述符对象的相对值。

```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>参数

*lhs*<br/>
`SID` (安全标识符) 或 `CSid` 显示在！ = 运算符的左侧。

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 出现在！ = 运算符右侧的。

### <a name="return-value"></a>返回值

如果 *lhs* 小于 *rhs*，则为 TRUE; 否则为 FALSE。

## <a name="csidoperator-lt"></a><a name="operator_lt__eq"></a> CSid：：运算符 &lt;=

比较两个安全描述符对象的相对值。

```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>参数

*lhs*<br/>
`SID` (安全标识符) 或 `CSid` 显示在！ = 运算符的左侧。

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 出现在！ = 运算符右侧的。

### <a name="return-value"></a>返回值

如果 *lhs* 小于或等于 *rhs*，则为 TRUE; 否则为 FALSE。

## <a name="csidoperator-gt"></a><a name="operator_gt"></a> CSid：：运算符 &gt;

比较两个安全描述符对象的相对值。

```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```

### <a name="parameters"></a>参数

*lhs*<br/>
`SID` (安全标识符) 或 `CSid` 显示在！ = 运算符的左侧。

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 出现在！ = 运算符右侧的。

### <a name="return-value"></a>返回值

如果 *lhs* 大于 *rhs*，则为 TRUE; 否则为 FALSE。

## <a name="csidoperator-gt"></a><a name="operator_gt__eq"></a> CSid：：运算符 &gt;=

比较两个安全描述符对象的相对值。

```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```

### <a name="parameters"></a>参数

*lhs*<br/>
`SID` (安全标识符) 或 `CSid` 显示在！ = 运算符的左侧。

*rhs*<br/>
`SID` (安全标识符) 或 `CSid` 出现在！ = 运算符右侧的。

### <a name="return-value"></a>返回值

如果 *lhs* 大于或等于 *rhs*，则为 TRUE; 否则为 FALSE。

## <a name="csidoperator-const-sid-"></a><a name="operator_const_sid__star"></a> CSid：： operator const SID \*

将对象强制转换为指向 `CSid` `SID` (安全标识符) 结构的指针。

```
operator const SID *() const throw(...);
```

### <a name="remarks"></a>注解

返回结构的地址 `SID` 。

## <a name="csidsid"></a><a name="sid"></a> CSid：： Sid

`SID`以字符串的形式返回 (安全标识符) 结构。

```
LPCTSTR Sid() const throw(...);
```

### <a name="return-value"></a>返回值

将 `SID` 结构返回为适用于显示、存储或传输的格式的字符串。 等效于 [ConvertSidToStringSid](/windows/win32/api/sddl/nf-sddl-convertsidtostringsidw)。

## <a name="csidsidnameuse"></a><a name="sidnameuse"></a> CSid：： SidNameUse

返回对象状态的说明 `CSid` 。

```
SID_NAME_USE SidNameUse() const throw();
```

### <a name="return-value"></a>返回值

返回数据成员的值，该值存储描述对象状态的值 `CSid` 。

|值|说明|
|-----------|-----------------|
|SidTypeUser|指示 `SID` (安全标识符) 的用户。|
|SidTypeGroup|表示组 `SID` 。|
|SidTypeDomain|指示域 `SID` 。|
|SidTypeAlias|指示别名 `SID` 。|
|SidTypeWellKnownGroup|指示 `SID` 已知组的。|
|SidTypeDeletedAccount|指示 `SID` 已删除帐户的。|
|SidTypeInvalid|指示无效的 `SID` 。|
|SidTypeUnknown|指示未知 `SID` 类型。|
|SidTypeComputer|指示 `SID` 计算机的。|

### <a name="remarks"></a>注解

[CSid::LoadAccount](#loadaccount) `CSid` 在调用 `SidNameUse` 以返回其状态之前，调用 CSid：： LoadAccount 以更新对象。 `SidNameUse` 不 (通过调用或) 来更改对象的状态 `LookupAccountName` `LookupAccountSid` ，但只返回当前状态。

## <a name="see-also"></a>另请参阅

[安全示例](../../overview/visual-cpp-samples.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[安全全局函数](../../atl/reference/security-global-functions.md)<br/>
[运算符](../../atl/reference/atl-operators.md)

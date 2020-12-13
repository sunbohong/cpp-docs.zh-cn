---
description: 了解详细信息： CTokenGroups 类
title: CTokenGroups 类
ms.date: 11/04/2016
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
ms.openlocfilehash: 3d6633afbd649aa175196f1fae8e62afdf784f99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140343"
---
# <a name="ctokengroups-class"></a>CTokenGroups 类

此类是结构的包装器 `TOKEN_GROUPS` 。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CTokenGroups
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CTokenGroups::CTokenGroups](#ctokengroups)|构造函数。|
|[CTokenGroups：： ~ CTokenGroups](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CTokenGroups：： Add](#add)|向 `CSid` 对象添加或现有 `TOKEN_GROUPS` 结构 `CTokenGroups` 。|
|[CTokenGroups：:D e) ](#delete)|`CSid`从对象中删除及其关联特性 `CTokenGroups` 。|
|[CTokenGroups：:D eleteAll](#deleteall)|`CSid`从对象中删除所有对象及其关联的属性 `CTokenGroups` 。|
|[CTokenGroups：： GetCount](#getcount)|返回 `CSid` 对象中包含的对象数和关联属性 `CTokenGroups` 。|
|[CTokenGroups：： GetLength](#getlength)|返回对象的大小 `CTokenGroups` 。|
|[CTokenGroups：： GetPTOKEN_GROUPS](#getptoken_groups)|检索指向结构的指针 `TOKEN_GROUPS` 。|
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|检索 `CSid` 属于对象的对象和属性 `CTokenGroups` 。|
|[CTokenGroups::LookupSid](#lookupsid)|检索与对象相关联的属性 `CSid` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CTokenGroups：： operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|将对象强制转换为指向 `CTokenGroups` 结构的指针 `TOKEN_GROUPS` 。|
|[CTokenGroups：： operator =](#operator_eq)|赋值运算符。|

## <a name="remarks"></a>备注

[访问令牌](/windows/win32/SecAuthZ/access-tokens)是一个对象，该对象描述进程或线程的安全上下文，并分配给登录到 Windows 系统的每个用户。

`CTokenGroups`类是[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)结构的包装，其中包含有关访问令牌中 (sid) 的组安全标识符的信息。

有关 Windows 中的访问控制模型的简介，请参阅 Windows SDK 中的 [访问控制](/windows/win32/SecAuthZ/access-control) 。

## <a name="requirements"></a>要求

**标头：** atlsecurity。h

## <a name="ctokengroupsadd"></a><a name="add"></a> CTokenGroups：： Add

向 `CSid` 对象添加或现有 `TOKEN_GROUPS` 结构 `CTokenGroups` 。

```cpp
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```

### <a name="parameters"></a>parameters

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)对象。

*dwAttributes*<br/>
要与对象关联的特性 `CSid` 。

*rTokenGroups*<br/>
[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)结构。

### <a name="remarks"></a>备注

这些方法将一个或多个 `CSid` 对象及其关联特性添加到 `CTokenGroups` 对象。

## <a name="ctokengroupsctokengroups"></a><a name="ctokengroups"></a> CTokenGroups::CTokenGroups

构造函数。

```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```

### <a name="parameters"></a>parameters

*rhs*<br/>
`CTokenGroups`用于构造对象的对象或[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)结构 `CTokenGroups` 。

### <a name="remarks"></a>备注

`CTokenGroups`可以选择使用 `TOKEN_GROUPS` 结构或以前定义的对象来创建对象 `CTokenGroups` 。

## <a name="ctokengroupsctokengroups"></a><a name="dtor"></a> CTokenGroups：： ~ CTokenGroups

析构函数。

```
virtual ~CTokenGroups() throw();
```

### <a name="remarks"></a>备注

析构函数释放所有已分配的资源。

## <a name="ctokengroupsdelete"></a><a name="delete"></a> CTokenGroups：:D e) 

`CSid`从对象中删除及其关联特性 `CTokenGroups` 。

```
bool Delete(const CSid& rSid) throw();
```

### <a name="parameters"></a>parameters

*rSid*<br/>
应为其移除安全标识符 (SID) 和属性的 [CSid](../../atl/reference/csid-class.md) 对象。

### <a name="return-value"></a>返回值

如果 `CSid` 已移除，则返回 true，否则返回 false。

## <a name="ctokengroupsdeleteall"></a><a name="deleteall"></a> CTokenGroups：:D eleteAll

`CSid`从对象中删除所有对象及其关联的属性 `CTokenGroups` 。

```cpp
void DeleteAll() throw();
```

## <a name="ctokengroupsgetcount"></a><a name="getcount"></a> CTokenGroups：： GetCount

返回 `CSid` 中包含的对象数 `CTokenGroups` 。

```
UINT GetCount() const throw();
```

### <a name="return-value"></a>返回值

返回对象中包含的 [CSid](../../atl/reference/csid-class.md) 对象及其关联属性的数目 `CTokenGroups` 。

## <a name="ctokengroupsgetlength"></a><a name="getlength"></a> CTokenGroups：： GetLength

返回对象的大小 `CTokenGroup` 。

```
UINT GetLength() const throw();
```

### <a name="remarks"></a>备注

返回对象的总大小 `CTokenGroup` （以字节为单位）。

## <a name="ctokengroupsgetptoken_groups"></a><a name="getptoken_groups"></a> CTokenGroups：： GetPTOKEN_GROUPS

检索指向结构的指针 `TOKEN_GROUPS` 。

```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```

### <a name="return-value"></a>返回值

检索指向属于访问令牌对象的 [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 结构的指针 `CTokenGroups` 。

## <a name="ctokengroupsgetsidsandattributes"></a><a name="getsidsandattributes"></a> CTokenGroups::GetSidsAndAttributes

检索 `CSid` 对象，并 (可以选择) 属于对象的特性 `CTokenGroups` 。

```cpp
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```

### <a name="parameters"></a>parameters

*pSids*<br/>
指向 [CSid](../../atl/reference/csid-class.md) 对象的数组的指针。

*pAttributes*<br/>
指向 Dword 数组的指针。 如果省略此参数或为 NULL，则不检索特性。

### <a name="remarks"></a>备注

此方法将枚举 `CSid` 对象中包含的所有对象 `CTokenGroups` ，并将其放入并 (（可选）) 属性标志转换为数组对象。

## <a name="ctokengroupslookupsid"></a><a name="lookupsid"></a> CTokenGroups::LookupSid

检索与对象相关联的属性 `CSid` 。

```
bool LookupSid(
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```

### <a name="parameters"></a>parameters

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)对象。

*pdwAttributes*<br/>
一个指向 DWORD 的指针，它将接受 `CSid` 对象的特性。 如果省略或为 NULL，则不会检索特性。

### <a name="return-value"></a>返回值

如果找到，则返回 true `CSid` ，否则返回 false。

### <a name="remarks"></a>备注

将 *pdwAttributes* 设置为 NULL 可提供一种在 `CSid` 不访问属性的情况下确认是否存在的方法。 请注意，此方法不应用于检查访问权限。 应用程序应改为使用 [CAccessToken：： CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) 方法。

## <a name="ctokengroupsoperator-"></a><a name="operator_eq"></a> CTokenGroups：： operator =

赋值运算符。

```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```

### <a name="parameters"></a>parameters

*rhs*<br/>
`CTokenGroups`要分配给对象的对象或[TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups)结构 `CTokenGroups` 。

### <a name="return-value"></a>返回值

返回已更新的 `CTokenGroups` 对象。

## <a name="ctokengroupsoperator-const-token_groups-"></a><a name="operator_const_token_groups__star"></a> CTokenGroups：： operator const TOKEN_GROUPS *

将值强制转换为指向结构的指针 `TOKEN_GROUPS` 。

```
operator const TOKEN_GROUPS *() const throw(...);
```

### <a name="remarks"></a>备注

将一个值转换为指向 [TOKEN_GROUPS](/windows/win32/api/winnt/ns-winnt-token_groups) 结构的指针。

## <a name="see-also"></a>请参阅

[安全示例](../../overview/visual-cpp-samples.md)<br/>
[CSid 类](../../atl/reference/csid-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[安全全局函数](../../atl/reference/security-global-functions.md)

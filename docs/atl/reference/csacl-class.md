---
description: 了解详细信息： CSacl 类
title: CSacl 类
ms.date: 11/04/2016
f1_keywords:
- CSacl
- ATLSECURITY/ATL::CSacl
- ATLSECURITY/ATL::CSacl::CSacl
- ATLSECURITY/ATL::CSacl::AddAuditAce
- ATLSECURITY/ATL::CSacl::GetAceCount
- ATLSECURITY/ATL::CSacl::RemoveAce
- ATLSECURITY/ATL::CSacl::RemoveAllAces
helpviewer_keywords:
- CSacl class
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
ms.openlocfilehash: 504276d22da963b9e8ec407e88ca73d63dd71541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140850"
---
# <a name="csacl-class"></a>CSacl 类

此类是 SACL (系统访问控制列表) 结构的包装器。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CSacl : public CAcl
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSacl::CSacl](#csacl)|构造函数。|
|[CSacl：： ~ CSacl](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSacl::AddAuditAce](#addauditace)|将 (ACE) 的审核访问控制项添加到 `CSacl` 对象。|
|[CSacl::GetAceCount](#getacecount)|返回对象中 (Ace) 的访问控制项的数目 `CSacl` 。|
|[CSacl::RemoveAce](#removeace)|从对象中移除特定 ACE (访问控制项) `CSacl` 。|
|[CSacl::RemoveAllAces](#removeallaces)|删除对象中包含的所有 Ace `CSacl` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CSacl：： operator =](#operator_eq)|赋值运算符。|

## <a name="remarks"></a>备注

SACL 包含 (Ace) 的访问控制项，用于指定在域控制器的安全事件日志中生成审核记录的访问尝试的类型。 请注意，SACL 仅在发生访问尝试的域控制器上生成日志条目，而不是在包含对象副本的每个域控制器上生成日志条目。

若要设置或检索对象的安全描述符中的 SACL，必须在请求线程的访问令牌中启用 SE_SECURITY_NAME 特权。 默认情况下，管理员组具有此权限，并且可以被授予其他用户或组。 赋予权限并非全部都是必需的：在可以执行特权定义的操作之前，必须在安全访问令牌中启用权限才能使其生效。 该模型只允许为特定系统操作启用权限，并在不再需要时禁用。 有关启用 SE_SECURITY_NAME 的示例，请参阅 [AtlGetSacl](security-global-functions.md#atlgetsacl) 和 [AtlSetSacl](security-global-functions.md#atlsetsacl) 。

使用提供的类方法可以从对象添加、删除、创建和删除 Ace `SACL` 。 另请参阅 [AtlGetSacl](security-global-functions.md#atlgetsacl) 和 [AtlSetSacl](security-global-functions.md#atlsetsacl)。

有关 Windows 中的访问控制模型的简介，请参阅 Windows SDK 中的 [访问控制](/windows/win32/SecAuthZ/access-control) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CAcl](../../atl/reference/cacl-class.md)

`CSacl`

## <a name="requirements"></a>要求

**标头：** atlsecurity。h

## <a name="csacladdauditace"></a><a name="addauditace"></a> CSacl::AddAuditAce

将 (ACE) 的审核访问控制项添加到 `CSacl` 对象。

```
bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags = 0) throw(...);

bool AddAuditAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    bool bSuccess,
    bool bFailure,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>parameters

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)对象。

*AccessMask*<br/>
为指定的对象指定要审核的访问权限的掩码 `CSid` 。

*bSuccess*<br/>
指定是否要审核允许的访问尝试。 将此标志设置为 true 可启用审核;否则，请将其设置为 false。

*bFailure*<br/>
指定是否要审核拒绝的访问尝试。 将此标志设置为 true 可启用审核;否则，请将其设置为 false。

*AceFlags*<br/>
控制 ACE 继承的一组位标志。

*pObjectType*<br/>
对象类型。

*pInheritedObjectType*<br/>
继承的对象类型。

### <a name="return-value"></a>返回值

如果将 ACE 添加到 `CSacl` 对象中，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

`CSacl`对象包含 (ace) 的访问控制项，这些项指定在安全事件日志中生成审核记录的访问尝试的类型。 此方法将此类 ACE 添加到 `CSacl` 对象。

有关可以在 *AceFlags* 参数中设置的各种标志的说明，请参阅 [ACE_HEADER](/windows/win32/api/winnt/ns-winnt-ace_header) 。

## <a name="csaclcsacl"></a><a name="csacl"></a> CSacl::CSacl

构造函数。

```
CSacl() throw();
CSacl(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>parameters

*rhs*<br/>
`ACL`) 结构的现有 (访问控制列表。

### <a name="remarks"></a>备注

`CSacl`可以选择使用现有的结构来创建对象 `ACL` 。 请确保此参数是系统访问控制列表 (SACL) ，而不是自由访问控制列表 (DACL) 。 在调试版本中，如果提供了 DACL，则将发生断言。 在版本中，将忽略 DACL 中的任何条目。

## <a name="csaclcsacl"></a><a name="dtor"></a> CSacl：： ~ CSacl

析构函数。

```
~CSacl() throw();
```

### <a name="remarks"></a>备注

析构函数释放对象获取的任何资源，包括 (Ace) 的所有访问控制项。

## <a name="csaclgetacecount"></a><a name="getacecount"></a> CSacl::GetAceCount

返回对象中 (Ace) 的访问控制项的数目 `CSacl` 。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>返回值

返回对象中包含的 Ace 的数量 `CSacl` 。

## <a name="csacloperator-"></a><a name="operator_eq"></a> CSacl：： operator =

赋值运算符。

```
CSacl& operator=(const ACL& rhs) throw(...);
```

### <a name="parameters"></a>parameters

*rhs*<br/>
`ACL`要分配给现有对象)  (访问控制列表。

### <a name="return-value"></a>返回值

返回对已更新的对象的引用 `CSacl` 。 请确保 `ACL` 参数实际上是系统访问控制列表 (SACL) ，而不是自由访问控制列表 (DACL) 。 在调试版本中，将发生断言，在发布版本中， `ACL` 将忽略参数。

## <a name="csaclremoveace"></a><a name="removeace"></a> CSacl::RemoveAce

从对象中移除特定 ACE (访问控制项) `CSacl` 。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要移除的 ACE 项的索引。

### <a name="remarks"></a>备注

此方法从 [CAtlArray：： RemoveAt](../../atl/reference/catlarray-class.md#removeat)派生。

## <a name="csaclremoveallaces"></a><a name="removeallaces"></a> CSacl::RemoveAllAces

删除对象中包含 (Ace) 的所有访问控制项 `CSacl` 。

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>备注

`ACE`如果对象中有任何) ，则删除每个结构 (`CSacl` 。

## <a name="see-also"></a>请参阅

[CAcl 类](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[安全全局函数](../../atl/reference/security-global-functions.md)

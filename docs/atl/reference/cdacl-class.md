---
description: 了解详细信息： CDacl 类
title: CDacl 类
ms.date: 11/04/2016
f1_keywords:
- CDacl
- ATLSECURITY/ATL::CDacl
- ATLSECURITY/ATL::CDacl::CDacl
- ATLSECURITY/ATL::CDacl::AddAllowedAce
- ATLSECURITY/ATL::CDacl::AddDeniedAce
- ATLSECURITY/ATL::CDacl::GetAceCount
- ATLSECURITY/ATL::CDacl::RemoveAce
- ATLSECURITY/ATL::CDacl::RemoveAllAces
helpviewer_keywords:
- CDacl class
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
ms.openlocfilehash: 0f071cbf426fe9cf89752defa19ff7f212e142d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141994"
---
# <a name="cdacl-class"></a>CDacl 类

此类是 DACL (自由访问控制列表) 结构的包装。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
class CDacl : public CAcl
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDacl::CDacl](#cdacl)|构造函数。|
|[CDacl：： ~ CDacl](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDacl::AddAllowedAce](#addallowedace)|向对象添加一个允许的 ACE (访问控制项) `CDacl` 。|
|[CDacl::AddDeniedAce](#adddeniedace)|将拒绝的 ACE 添加到 `CDacl` 对象。|
|[CDacl::GetAceCount](#getacecount)|返回对象中)  (访问控制项的数目 `CDacl` 。|
|[CDacl::RemoveAce](#removeace)|从对象中移除特定 ACE (访问控制项) `CDacl` 。|
|[CDacl::RemoveAllAces](#removeallaces)|删除对象中包含的所有 Ace `CDacl` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CDacl：： operator =](#operator_eq)|赋值运算符。|

## <a name="remarks"></a>备注

对象的安全描述符可以包含 DACL。 DACL 包含零个或多个 Ace (访问控制项) 用于标识可以访问对象的用户和组。 如果 DACL 为空 (也就是说，它包含零个 Ace) ，不会显式授予访问权限，因此，拒绝访问。 但是，如果对象的安全描述符没有 DACL，则该对象是不受保护的，并且每个人都具有完全访问权限。

若要检索对象的 DACL，你必须是对象的所有者，或者具有 READ_CONTROL 对对象的访问权限。 若要更改对象的 DACL，必须对该对象具有 WRITE_DAC 访问权限。

使用提供的类方法创建、添加、删除和删除对象中的 Ace `CDacl` 。 另请参阅 [AtlGetDacl](security-global-functions.md#atlgetdacl) 和 [AtlSetDacl](security-global-functions.md#atlsetdacl)。

有关 Windows 中的访问控制模型的简介，请参阅 Windows SDK 中的 [访问控制](/windows/win32/SecAuthZ/access-control) 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CAcl](../../atl/reference/cacl-class.md)

`CDacl`

## <a name="requirements"></a>要求

**标头：** atlsecurity。h

## <a name="cdacladdallowedace"></a><a name="addallowedace"></a> CDacl::AddAllowedAce

向对象添加一个允许的 ACE (访问控制项) `CDacl` 。

```
bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddAllowedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>parameters

*rSid*<br/>
[CSid](../../atl/reference/csid-class.md)对象。

*AccessMask*<br/>
指定要为指定的对象允许的访问权限的掩码 `CSid` 。

*AceFlags*<br/>
控制 ACE 继承的一组位标志。

*pObjectType*<br/>
对象类型。

*pInheritedObjectType*<br/>
继承的对象类型。

### <a name="return-value"></a>返回值

如果将 ACE 添加到 `CDacl` 对象中，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

`CDacl`对象包含零个或多个 ace (访问控制项) 用于标识可以访问对象的用户和组。 此方法添加一个允许访问对象的 ACE `CDacl` 。

有关[](/windows/win32/api/winnt/ns-winnt-ace_header)可在参数中设置的各种标志的说明，请参阅 ACE_HEADER `AceFlags` 。

## <a name="cdacladddeniedace"></a><a name="adddeniedace"></a> CDacl::AddDeniedAce

向对象添加拒绝的 ACE (访问控制项) `CDacl` 。

```
bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags = 0) throw(...);

bool AddDeniedAce(
    const CSid& rSid,
    ACCESS_MASK AccessMask,
    BYTE AceFlags,
    const GUID* pObjectType,
    const GUID* pInheritedObjectType) throw(...);
```

### <a name="parameters"></a>parameters

*rSid*<br/>
`CSid` 对象。

*AccessMask*<br/>
为指定的对象指定要拒绝的访问权限的掩码 `CSid` 。

*AceFlags*<br/>
控制 ACE 继承的一组位标志。 在方法的第一种形式下，默认值为0。

*pObjectType*<br/>
对象类型。

*pInheritedObjectType*<br/>
继承的对象类型。

### <a name="return-value"></a>返回值

如果将 ACE 添加到 `CDacl` 对象中，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

`CDacl`对象包含零个或多个 ace (访问控制项) 用于标识可以访问对象的用户和组。 此方法添加一个拒绝对对象的访问的 ACE `CDacl` 。

有关[](/windows/win32/api/winnt/ns-winnt-ace_header)可在参数中设置的各种标志的说明，请参阅 ACE_HEADER `AceFlags` 。

## <a name="cdaclcdacl"></a><a name="cdacl"></a> CDacl::CDacl

构造函数。

```
CDacl (const ACL& rhs) throw(...);
CDacl () throw();
```

### <a name="parameters"></a>parameters

*rhs*<br/>
`ACL`) 结构的现有 (访问控制列表。

### <a name="remarks"></a>备注

`CDacl`可以选择使用现有的结构来创建对象 `ACL` 。 请务必注意，只有 DACL (自由访问控制列表) ，而不是 SACL (系统访问控制列表) ，应作为此参数传递。 在调试版本中，传递 SACL 将导致断言。 在发布版本中，传递 SACL 将导致 Ace 中)  (访问控制项被忽略，并且不会发生错误。

## <a name="cdaclcdacl"></a><a name="dtor"></a> CDacl：： ~ CDacl

析构函数。

```
~CDacl () throw();
```

### <a name="remarks"></a>备注

析构函数释放对象获取的任何资源，包括使用 [CDacl：： RemoveAllAces](#removeallaces)) 的所有 ace (访问控制项。

## <a name="cdaclgetacecount"></a><a name="getacecount"></a> CDacl::GetAceCount

返回对象中)  (访问控制项的数目 `CDacl` 。

```
UINT GetAceCount() const throw();
```

### <a name="return-value"></a>返回值

返回对象中包含的 Ace 的数量 `CDacl` 。

## <a name="cdacloperator-"></a><a name="operator_eq"></a> CDacl：： operator =

赋值运算符。

```
CDacl& operator= (const ACL& rhs) throw(...);
```

### <a name="parameters"></a>parameters

*rhs*<br/>
要分配给现有对象) ACL (访问控制列表。

### <a name="return-value"></a>返回值

返回对已更新的对象的引用 `CDacl` 。

### <a name="remarks"></a>备注

你应确保仅向此函数传递 DACL (自由访问控制列表) 。 将 SACL (系统访问控制列表) 传递到此函数将导致调试生成中出现断言，但在发布版本中不会引发错误。

## <a name="cdaclremoveace"></a><a name="removeace"></a> CDacl::RemoveAce

从对象中移除特定 ACE (访问控制项) `CDacl` 。

```cpp
void RemoveAce(UINT nIndex) throw();
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
要移除的 ACE 项的索引。

### <a name="remarks"></a>备注

此方法从 [CAtlArray：： RemoveAt](../../atl/reference/catlarray-class.md#removeat)派生。

## <a name="cdaclremoveallaces"></a><a name="removeallaces"></a> CDacl::RemoveAllAces

删除对象中包含的所有 Ace (访问控制项) `CDacl` 。

```cpp
void RemoveAllAces() throw();
```

### <a name="remarks"></a>备注

`ACE`如果对象中有任何) ，则删除每个 (访问控制项) 结构 (`CDacl` 。

## <a name="see-also"></a>请参阅

[安全示例](../../overview/visual-cpp-samples.md)<br/>
[CAcl 类](../../atl/reference/cacl-class.md)<br/>
[ACL](/windows/win32/SecAuthZ/access-control-lists)<br/>
[Ace](/windows/win32/SecAuthZ/access-control-entries)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[安全全局函数](../../atl/reference/security-global-functions.md)

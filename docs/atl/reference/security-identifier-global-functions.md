---
description: 了解详细信息：安全标识符全局函数
title: 安全标识符全局函数
ms.date: 11/04/2016
f1_keywords:
- atlsecurity/ATL::Sids::AccountOps
- atlsecurity/ATL::Sids::Admins
- atlsecurity/ATL::Sids::AnonymousLogon
- atlsecurity/ATL::Sids::AuthenticatedUser
- atlsecurity/ATL::Sids::BackupOps
- atlsecurity/ATL::Sids::Batch
- atlsecurity/ATL::Sids::CreatorGroup
- atlsecurity/ATL::Sids::CreatorGroupServer
- atlsecurity/ATL::Sids::CreatorOwner
- atlsecurity/ATL::Sids::CreatorOwnerServer
- atlsecurity/ATL::Sids::Dialup
- atlsecurity/ATL::Sids::Guests
- atlsecurity/ATL::Sids::Interactive
- atlsecurity/ATL::Sids::Local
- atlsecurity/ATL::Sids::Network
- atlsecurity/ATL::Sids::NetworkService
- atlsecurity/ATL::Sids::Null
- atlsecurity/ATL::Sids::PowerUsers
- atlsecurity/ATL::Sids::PrintOps
- atlsecurity/ATL::Sids::Proxy
- atlsecurity/ATL::Sids::RasServers
- atlsecurity/ATL::Sids::Replicator
- atlsecurity/ATL::Sids::RestrictedCode
- atlsecurity/ATL::Sids::Self
- atlsecurity/ATL::Sids::ServerLogon
- atlsecurity/ATL::Sids::Service
- atlsecurity/ATL::Sids::System
- atlsecurity/ATL::Sids::SystemOps
- atlsecurity/ATL::Sids::TerminalServer
- atlsecurity/ATL::Sids::Users
- atlsecurity/ATL::Sids::World
helpviewer_keywords:
- security IDs [C++]
- SIDs [C++], returning SID objects
ms.assetid: 85404dcb-c59b-4535-ab3d-66cfa37e87de
ms.openlocfilehash: 035cdf2991f00d518bf4cfc3a93a226650728846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138861"
---
# <a name="security-identifier-global-functions"></a>安全标识符全局函数

这些函数返回常见的众所周知 SID 对象。

> [!IMPORTANT]
> 下表中列出的函数不能用于在 Windows 运行时中执行的应用程序。

|名称|描述|
|-|-|
|[Sids::AccountOps](#accountops)|返回 DOMAIN_ALIAS_RID_ACCOUNT_OPS SID。|
|[Sids::Admins](#admins)|返回 DOMAIN_ALIAS_RID_ADMINS SID。|
|[Sids::AnonymousLogon](#anonymouslogon)|返回 SECURITY_ANONYMOUS_LOGON_RID SID。|
|[Sids::AuthenticatedUser](#authenticateduser)|返回 SECURITY_AUTHENTICATED_USER_RID SID。|
|[Sids::BackupOps](#backupops)|返回 DOMAIN_ALIAS_RID_BACKUP_OPS SID。|
|[Sids::Batch](#batch)|返回 SECURITY_BATCH_RID SID。|
|[Sids::CreatorGroup](#creatorgroup)|返回 SECURITY_CREATOR_GROUP_RID SID。|
|[Sids::CreatorGroupServer](#creatorgroupserver)|返回 SECURITY_CREATOR_GROUP_SERVER_RID SID。|
|[Sids::CreatorOwner](#creatorowner)|返回 SECURITY_CREATOR_OWNER_RID SID。|
|[Sids::CreatorOwnerServer](#creatorownerserver)|返回 SECURITY_CREATOR_OWNER_SERVER_RID SID。|
|[Sids::Dialup](#dialup)|返回 SECURITY_DIALUP_RID SID。|
|[Sids::Guests](#guests)|返回 DOMAIN_ALIAS_RID_GUESTS SID。|
|[Sids::Interactive](#interactive)|返回 SECURITY_INTERACTIVE_RID SID。|
|[Sids::Local](#local)|返回 SECURITY_LOCAL_RID SID。|
|[Sids::Network](#network)|返回 SECURITY_NETWORK_RID SID。|
|[Sids::NetworkService](#networkservice)|返回 SECURITY_NETWORK_SERVICE_RID SID。|
|[Sids::Null](#null)|返回 SECURITY_NULL_RID SID。|
|[Sids::PreW2KAccess](#prew2kaccess)|返回 DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID。|
|[Sids::PowerUsers](#powerusers)|返回 DOMAIN_ALIAS_RID_POWER_USERS SID。|
|[Sids::PrintOps](#printops)|返回 DOMAIN_ALIAS_RID_PRINT_OPS SID。|
|[Sids::Proxy](#proxy)|返回 SECURITY_PROXY_RID SID。|
|[Sids::RasServers](#rasservers)|返回 DOMAIN_ALIAS_RID_RAS_SERVERS SID。|
|[Sids::Replicator](#replicator)|返回 DOMAIN_ALIAS_RID_REPLICATOR SID。|
|[Sids::RestrictedCode](#restrictedcode)|返回 SECURITY_RESTRICTED_CODE_RID SID。|
|[Sids::Self](#self)|返回 SECURITY_PRINCIPAL_SELF_RID SID。|
|[Sids::ServerLogon](#serverlogon)|返回 SECURITY_SERVER_LOGON_RID SID。|
|[Sids::Service](#service)|返回 SECURITY_SERVICE_RID SID。|
|[Sids::System](#system)|返回 SECURITY_LOCAL_SYSTEM_RID SID。|
|[Sids::SystemOps](#systemops)|返回 DOMAIN_ALIAS_RID_SYSTEM_OPS SID。|
|[Sids::TerminalServer](#terminalserver)|返回 SECURITY_TERMINAL_SERVER_RID SID。|
|[Sids::Users](#users)|返回 DOMAIN_ALIAS_RID_USERS SID。|
|[Sid：： World](#world)|返回 SECURITY_WORLD_RID SID。|

### <a name="requirements"></a>要求

**标头：** atlsecurity。h

## <a name="sidsaccountops"></a><a name="accountops"></a> Sid：： AccountOps

返回 DOMAIN_ALIAS_RID_ACCOUNT_OPS SID。

```
CSid AccountOps() throw(...);
```

## <a name="sidsadmins"></a><a name="admins"></a> Sid：： Admins

返回 DOMAIN_ALIAS_RID_ADMINS SID。

```
CSid Admins() throw(...);
```

## <a name="sidsanonymouslogon"></a><a name="anonymouslogon"></a> Sid：： AnonymousLogon

返回 SECURITY_ANONYMOUS_LOGON_RID SID。

```
CSid AnonymousLogon() throw(...);
```

## <a name="sidsauthenticateduser"></a><a name="authenticateduser"></a> Sid：： AuthenticatedUser

返回 SECURITY_AUTHENTICATED_USER_RID SID。

```
CSid AuthenticatedUser() throw(...);
```

## <a name="sidsbackupops"></a><a name="backupops"></a> Sid：： BackupOps

返回 DOMAIN_ALIAS_RID_BACKUP_OPS SID。

```
CSid BackupOps() throw(...);
```

## <a name="sidsbatch"></a><a name="batch"></a> Sid：： Batch

返回 SECURITY_BATCH_RID SID。

```
CSid Batch() throw(...);
```

## <a name="sidscreatorgroup"></a><a name="creatorgroup"></a> Sid：： CreatorGroup

返回 SECURITY_CREATOR_GROUP_RID SID。

```
CSid CreatorGroup() throw(...);
```

## <a name="sidscreatorgroupserver"></a><a name="creatorgroupserver"></a> Sid：： CreatorGroupServer

返回 SECURITY_CREATOR_GROUP_SERVER_RID SID。

```
CSid CreatorGroupServer() throw(...);
```

## <a name="sidscreatorowner"></a><a name="creatorowner"></a> Sid：： CreatorOwner

返回 SECURITY_CREATOR_OWNER_RID SID。

```
CSid CreatorOwner() throw(...);
```

## <a name="sidscreatorownerserver"></a><a name="creatorownerserver"></a> Sid：： CreatorOwnerServer

返回 SECURITY_CREATOR_OWNER_SERVER_RID SID。

```
CSid CreatorOwnerServer() throw(...);
```

## <a name="sidsdialup"></a><a name="dialup"></a> Sid：:D ialup

返回 SECURITY_DIALUP_RID SID。

```
CSid Dialup() throw(...);
```

## <a name="sidsguests"></a><a name="guests"></a> Sid：： Guest

返回 DOMAIN_ALIAS_RID_GUESTS SID。

```
CSid Guests() throw(...);
```

## <a name="sidsinteractive"></a><a name="interactive"></a> Sid：： Interactive

返回 SECURITY_INTERACTIVE_RID SID。

```
CSid Interactive() throw(...);
```

## <a name="sidslocal"></a><a name="local"></a> Sid：： Local

返回 SECURITY_LOCAL_RID SID。

```
CSid Local() throw(...);
```

## <a name="sidsnetwork"></a><a name="network"></a> Sid：： Network

返回 SECURITY_NETWORK_RID SID。

```
CSid Network() throw(...);
```

## <a name="sidsnetworkservice"></a><a name="networkservice"></a> Sid：： NetworkService

返回 SECURITY_NETWORK_SERVICE_RID SID。

```
CSid NetworkService() throw(...);
```

### <a name="remarks"></a>备注

使用 NetworkService 使 NT AUTHORITY\NetworkService 用户能够读取 CPerfMon 安全对象。 NetworkService 将 SecurityAttribute 添加到 ATLServer 代码，这将允许 DLL 在 Windows XP Home Edition、Windows XP Professional、Windows Server 2003 和更高版本的操作系统上的 NetworkService 帐户下登录。

当通过 Perfmon MMC 中的 ATLServer CPerfMon 类创建自定义日志计数器时，在查看日志文件时可能不会显示计数器，但它们会在实时视图中正确显示。 CPerfMon 自定义性能计数器没有必要的权限，无法在 Windows XP Home Edition、Windows XP Professional、Windows Server 2003 (或更高) 版本的操作系统上的 "性能日志和警报" service ( # A0) 下运行。 此服务在 "NT AUTHORITY\NetworkService" 帐户下运行。

## <a name="sidsnull"></a><a name="null"></a> Sid：： Null

返回 SECURITY_NULL_RID SID。

```
CSid Null() throw(...);
```

## <a name="sidsprew2kaccess"></a><a name="prew2kaccess"></a> Sid：:P reW2KAccess

返回 DOMAIN_ALIAS_RID_PREW2KCOMPACCESS SID。

```
CSid PreW2KAccess() throw(...);
```

## <a name="sidspowerusers"></a><a name="powerusers"></a> Sid：:P owerUsers

返回 DOMAIN_ALIAS_RID_POWER_USERS SID。

```
CSid PowerUsers() throw(...);
```

## <a name="sidsprintops"></a><a name="printops"></a> Sid：:P rintOps

返回 DOMAIN_ALIAS_RID_PRINT_OPS SID。

```
CSid PrintOps() throw(...);
```

## <a name="sidsproxy"></a><a name="proxy"></a> Sid：:P 代理

返回 SECURITY_PROXY_RID SID。

```
CSid Proxy() throw(...);
```

## <a name="sidsrasservers"></a><a name="rasservers"></a> Sid：： RasServers

返回 DOMAIN_ALIAS_RID_RAS_SERVERS SID。

```
CSid RasServers() throw(...);
```

## <a name="sidsreplicator"></a><a name="replicator"></a> Sid：：复制器

返回 DOMAIN_ALIAS_RID_REPLICATOR SID。

```
CSid Replicator() throw(...);
```

## <a name="sidsrestrictedcode"></a><a name="restrictedcode"></a> Sid：： RestrictedCode

返回 SECURITY_RESTRICTED_CODE_RID SID。

```
CSid RestrictedCode() throw(...);
```

## <a name="sidsself"></a><a name="self"></a> Sid：： Self

返回 SECURITY_PRINCIPAL_SELF_RID SID。

```
CSid Self() throw(...);
```

## <a name="sidsserverlogon"></a><a name="serverlogon"></a> Sid：： Logon

返回 SECURITY_SERVER_LOGON_RID SID。

```
CSid ServerLogon() throw(...);
```

## <a name="sidsservice"></a><a name="service"></a> Sid：： Service

返回 SECURITY_SERVICE_RID SID。

```
CSid Service() throw(...);
```

## <a name="sidssystem"></a><a name="system"></a> Sid：： System

返回 SECURITY_LOCAL_SYSTEM_RID SID。

```
CSid System() throw(...);
```

## <a name="sidssystemops"></a><a name="systemops"></a> Sid：： SystemOps

返回 DOMAIN_ALIAS_RID_SYSTEM_OPS SID。

```
CSid SystemOps() throw(...);
```

## <a name="sidsterminalserver"></a><a name="terminalserver"></a> Sid：： TerminalServer

返回 SECURITY_TERMINAL_SERVER_RID SID。

```
CSid TerminalServer() throw(...);
```

## <a name="sidsusers"></a><a name="users"></a> Sid：： Users

返回 DOMAIN_ALIAS_RID_USERS SID。

```
CSid Users() throw(...);
```

## <a name="sidsworld"></a><a name="world"></a> Sid：： World

返回 SECURITY_WORLD_RID SID。

```
CSid World() throw(...);
```

## <a name="see-also"></a>请参阅

[函数](../../atl/reference/atl-functions.md)

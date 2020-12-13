---
description: 了解详细信息： IObjectSafetyImpl 类
title: IObjectSafetyImpl 类
ms.date: 11/04/2016
f1_keywords:
- IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl
- ATLCTL/ATL::IObjectSafetyImpl::GetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::SetInterfaceSafetyOptions
- ATLCTL/ATL::IObjectSafetyImpl::m_dwCurrentSafety
helpviewer_keywords:
- controls [ATL], safe
- safe for scripting and initialization (controls)
- IObjectSafety, ATL implementation
- IObjectSafetyImpl class
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
ms.openlocfilehash: ac19fe24d12d7d09968b3e2d76f77741e83e1f81
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139459"
---
# <a name="iobjectsafetyimpl-class"></a>IObjectSafetyImpl 类

此类提供接口的默认实现 `IObjectSafety` ，以允许客户端检索和设置对象的安全级别。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <class T,DWORD dwSupportedSafety>
class IObjectSafetyImpl
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `IObjectSafetyImpl` 。

*dwSupportedSafety*<br/>
指定控件支持的安全选项。 可以是以下其中一个值：

- INTERFACESAFE_FOR_UNTRUSTED_CALLER [SetInterfaceSafetyOptions](#setinterfacesafetyoptions) 参数标识的接口 `riid` 应可安全地用于脚本编写。

- INTERFACESAFE_FOR_UNTRUSTED_DATA 在初始化期间由参数标识的接口 `SetInterfaceSafetyOptions` `riid` 应在不受信任的数据中是安全的。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[IObjectSafetyImpl：： GetInterfaceSafetyOptions](#getinterfacesafetyoptions)|检索对象支持的安全选项以及当前为该对象设置的安全选项。|
|[IObjectSafetyImpl：： SetInterfaceSafetyOptions](#setinterfacesafetyoptions)|使对象对初始化或编写脚本是安全的。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[IObjectSafetyImpl：： m_dwCurrentSafety](#m_dwcurrentsafety)|存储对象的当前安全级别。|

## <a name="remarks"></a>备注

类 `IObjectSafetyImpl` 提供的默认实现 `IObjectSafety` 。 `IObjectSafety`接口允许客户端检索和设置对象的安全级别。 例如，web 浏览器可以调用 `IObjectSafety::SetInterfaceSafetyOptions` 来使控件在初始化时安全，也可以安全地用于脚本编写。

请注意，将 [IMPLEMENTED_CATEGORY](category-macros.md#implemented_category) 宏与 CATID_SafeForScripting 和 CATID_SafeForInitializing 组件类别一起使用可以指定组件是安全的。

**相关文章** [ATL 教程](../../atl/active-template-library-atl-tutorial.md)， [创建 atl 项目](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

`IObjectSafety`

`IObjectSafetyImpl`

## <a name="requirements"></a>要求

**标头：** atlctl

## <a name="iobjectsafetyimplgetinterfacesafetyoptions"></a><a name="getinterfacesafetyoptions"></a> IObjectSafetyImpl：： GetInterfaceSafetyOptions

检索对象支持的安全选项以及当前为该对象设置的安全选项。

```
HRESULT GetInterfaceSafetyOptions(
    REFIID riid,
    DWORD* pdwSupportedOptions,
    DWORD* pdwEnabledOptions);
```

### <a name="remarks"></a>备注

实现为对象的实现所支持的任何接口返回相应的值 `IUnknown::QueryInterface` 。

> [!IMPORTANT]
> 任何支持的对象 `IObjectSafety` 负责其自身的安全性，以及它所委托的任何对象的安全性。 程序员必须考虑到在用户上下文中运行代码、跨站点脚本并执行适当区域检查引起的问题。

请参阅 Windows SDK 中的 [IObjectSafety：： GetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768223\(v=vs.85\)) 。

## <a name="iobjectsafetyimplm_dwcurrentsafety"></a><a name="m_dwcurrentsafety"></a> IObjectSafetyImpl：： m_dwCurrentSafety

存储对象的当前安全级别。

```
DWORD m_dwCurrentSafety;
```

## <a name="iobjectsafetyimplsetinterfacesafetyoptions"></a><a name="setinterfacesafetyoptions"></a> IObjectSafetyImpl：： SetInterfaceSafetyOptions

通过将 [m_dwCurrentSafety](#m_dwcurrentsafety) 成员设置为适当的值，使对象可安全初始化或编写脚本。

```
HRESULT SetInterfaceSafetyOptions(
    REFIID riid,
    DWORD dwOptionsSetMask,
    DWORD dwEnabledOptions);
```

### <a name="remarks"></a>备注

实现对于对象的实现不支持的任何接口，返回 E_NOINTERFACE `IUnknown::QueryInterface` 。

> [!IMPORTANT]
> 任何支持的对象 `IObjectSafety` 负责其自身的安全性，以及它所委托的任何对象的安全性。 程序员必须考虑到在用户上下文中运行代码、跨站点脚本并执行适当区域检查引起的问题。

请参阅 Windows SDK 中的 [IObjectSafety：： SetInterfaceSafetyOptions](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768225\(v=vs.85\)) 。

## <a name="see-also"></a>请参阅

[IObjectSafety 接口](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa768224\(v=vs.85\))<br/>
[类概述](../../atl/atl-class-overview.md)

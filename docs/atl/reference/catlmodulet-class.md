---
description: 了解详细信息： CAtlModuleT 类
title: CAtlModuleT 类
ms.date: 11/04/2016
f1_keywords:
- CAtlModuleT
- ATLBASE/ATL::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::CAtlModuleT
- ATLBASE/ATL::CAtlModuleT::InitLibId
- ATLBASE/ATL::CAtlModuleT::RegisterAppId
- ATLBASE/ATL::CAtlModuleT::RegisterServer
- ATLBASE/ATL::CAtlModuleT::UnregisterAppId
- ATLBASE/ATL::CAtlModuleT::UnregisterServer
- ATLBASE/ATL::CAtlModuleT::UpdateRegistryAppId
helpviewer_keywords:
- CAtlModuleT class
ms.assetid: 9b74d02f-9117-47b1-a05e-c5945f83dd2b
ms.openlocfilehash: 841d4a41b7df818d9e966af1050fd9e376d89447
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147220"
---
# <a name="catlmodulet-class"></a>CAtlModuleT 类

此类实现 ATL 模块。

## <a name="syntax"></a>语法

```cpp
template <class T>
class ATL_NO_VTABLE CAtlModuleT : public CAtlModule
```

### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `CAtlModuleT` 。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAtlModuleT::CAtlModuleT](#catlmodulet)|构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAtlModuleT::InitLibId](#initlibid)|初始化包含当前模块的 GUID 的数据成员。|
|[CAtlModuleT::RegisterAppId](#registerappid)|将 EXE 添加到注册表。|
|[CAtlModuleT::RegisterServer](#registerserver)|将服务添加到注册表。|
|[CAtlModuleT::UnregisterAppId](#unregisterappid)|从注册表中删除 EXE。|
|[CAtlModuleT::UnregisterServer](#unregisterserver)|从注册表中删除服务。|
|[CAtlModuleT::UpdateRegistryAppId](#updateregistryappid)|更新注册表中的 EXE 信息。|

## <a name="remarks"></a>备注

`CAtlModuleT`（派生自 [CAtlModule](../../atl/reference/catlmodule-class.md)） (exe) 或服务 (EXE) ATL 模块实现可执行文件。 可执行模块是本地的进程外服务器，而服务模块是在 Windows 启动时在后台运行的 Windows 应用程序。

`CAtlModuleT` 为模块的初始化、注册和注销提供支持。

## <a name="inheritance-hierarchy"></a>继承层次结构

[_ATL_MODULE](atl-typedefs.md#_atl_module)

[CAtlModule](../../atl/reference/catlmodule-class.md)

`CAtlModuleT`

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="catlmoduletcatlmodulet"></a><a name="catlmodulet"></a> CAtlModuleT::CAtlModuleT

构造函数。

```cpp
CAtlModuleT() throw();
```

### <a name="remarks"></a>备注

调用 [CAtlModuleT：： InitLibId](#initlibid)。

## <a name="catlmoduletinitlibid"></a><a name="initlibid"></a> CAtlModuleT::InitLibId

初始化包含当前模块的 GUID 的数据成员。

```cpp
static void InitLibId() throw();
```

### <a name="remarks"></a>备注

由构造函数 [CAtlModuleT：： CAtlModuleT](#catlmodulet)调用。

## <a name="catlmoduletregisterappid"></a><a name="registerappid"></a> CAtlModuleT::RegisterAppId

将 EXE 添加到注册表。

```cpp
HRESULT RegisterAppId() throw();
```

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="catlmoduletregisterserver"></a><a name="registerserver"></a> CAtlModuleT::RegisterServer

将服务添加到注册表。

```cpp
HRESULT RegisterServer(
    BOOL bRegTypeLib = FALSE,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>parameters

*bRegTypeLib*<br/>
如果要注册类型库，则为 TRUE。 默认值是 FALSE。

*pCLSID*<br/>
指向要注册的对象的 CLSID。 如果为 NULL (默认值) ，则将注册对象映射中的所有对象。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="catlmoduletunregisterappid"></a><a name="unregisterappid"></a> CAtlModuleT::UnregisterAppId

从注册表中删除 EXE。

```cpp
HRESULT UnregisterAppId() throw();
```

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="catlmoduletunregisterserver"></a><a name="unregisterserver"></a> CAtlModuleT::UnregisterServer

从注册表中删除服务。

```cpp
HRESULT UnregisterServer(
    BOOL bUnRegTypeLib,
    const CLSID* pCLSID = NULL) throw();
```

### <a name="parameters"></a>parameters

*bUnRegTypeLib*<br/>
如果还要注销类型库，则为 TRUE。

*pCLSID*<br/>
指向要注销的对象的 CLSID。 如果为 NULL (默认值) ，则将取消注册对象映射中的所有对象。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="catlmoduletupdateregistryappid"></a><a name="updateregistryappid"></a> CAtlModuleT::UpdateRegistryAppId

更新注册表中的 EXE 信息。

```cpp
static HRESULT WINAPI UpdateRegistryAppId(BOOL /* bRegister*/) throw();
```

### <a name="parameters"></a>parameters

*bRegister*<br/>
保留。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="see-also"></a>请参阅

[CAtlModule 类](../../atl/reference/catlmodule-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)<br/>
[Module 类](../../atl/atl-module-classes.md)

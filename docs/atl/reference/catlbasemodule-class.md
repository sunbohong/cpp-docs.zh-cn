---
description: 了解详细信息： CAtlBaseModule 类
title: CAtlBaseModule 类
ms.date: 11/04/2016
f1_keywords:
- CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::CAtlBaseModule
- ATLCORE/ATL::CAtlBaseModule::AddResourceInstance
- ATLCORE/ATL::CAtlBaseModule::GetHInstanceAt
- ATLCORE/ATL::CAtlBaseModule::GetModuleInstance
- ATLCORE/ATL::CAtlBaseModule::GetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::RemoveResourceInstance
- ATLCORE/ATL::CAtlBaseModule::SetResourceInstance
- ATLCORE/ATL::CAtlBaseModule::m_bInitFailed
helpviewer_keywords:
- CAtlBaseModule class
ms.assetid: 55ade80c-9b0c-4c51-933e-2158436c1096
ms.openlocfilehash: 249b2ad2d133ba0f407e9c5fabcf716b09605972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147532"
---
# <a name="catlbasemodule-class"></a>CAtlBaseModule 类

此类在每个 ATL 项目中实例化。

## <a name="syntax"></a>语法

```cpp
class CAtlBaseModule : public _ATL_BASE_MODULE
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAtlBaseModule::CAtlBaseModule](#catlbasemodule)|构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAtlBaseModule::AddResourceInstance](#addresourceinstance)|向存储句柄的列表添加资源实例。|
|[CAtlBaseModule::GetHInstanceAt](#gethinstanceat)|返回指定资源实例的句柄。|
|[CAtlBaseModule::GetModuleInstance](#getmoduleinstance)|从对象返回模块实例 `CAtlBaseModule` 。|
|[CAtlBaseModule::GetResourceInstance](#getresourceinstance)|从对象返回资源实例 `CAtlBaseModule` 。|
|[CAtlBaseModule::RemoveResourceInstance](#removeresourceinstance)|从存储句柄的列表中删除资源实例。|
|[CAtlBaseModule::SetResourceInstance](#setresourceinstance)|设置对象的资源实例 `CAtlBaseModule` 。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CAtlBaseModule：： m_bInitFailed](#m_binitfailed)|一个变量，指示模块初始化是否失败。|

## <a name="remarks"></a>备注

`CAtlBaseModule`命名 _AtlBaseModule 的实例存在于每个 ATL 项目中，其中包含模块实例的句柄、包含资源的模块的句柄 (默认情况下，它是一个和相同的) ，另一个是提供主要资源的模块的句柄数组。 `CAtlBaseModule` 可以从多个线程安全访问。

此类替换在早期版本的 ATL 中使用的过时 [CComModule](../../atl/reference/ccommodule-class.md) 类。

## <a name="inheritance-hierarchy"></a>继承层次结构

[_ATL_BASE_MODULE](atl-typedefs.md#_atl_base_module)

`CAtlBaseModule`

## <a name="requirements"></a>要求

**标头：** atlcore

## <a name="catlbasemoduleaddresourceinstance"></a><a name="addresourceinstance"></a> CAtlBaseModule::AddResourceInstance

向存储句柄的列表添加资源实例。

```cpp
bool AddResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>parameters

*hInst*<br/>
要添加的资源实例。

### <a name="return-value"></a>返回值

如果成功添加了资源，则返回 true，否则返回 false。

## <a name="catlbasemodulecatlbasemodule"></a><a name="catlbasemodule"></a> CAtlBaseModule::CAtlBaseModule

构造函数。

```cpp
CAtlBaseModule() throw();
```

### <a name="remarks"></a>备注

创建 `CAtlBaseModule`。

## <a name="catlbasemodulegethinstanceat"></a><a name="gethinstanceat"></a> CAtlBaseModule::GetHInstanceAt

返回指定资源实例的句柄。

```cpp
HINSTANCE GetHInstanceAt(int i) throw();
```

### <a name="parameters"></a>参数

*i*<br/>
资源实例的编号。

### <a name="return-value"></a>返回值

返回资源实例的句柄，如果不存在相应的资源实例，则返回 NULL。

## <a name="catlbasemodulegetmoduleinstance"></a><a name="getmoduleinstance"></a> CAtlBaseModule::GetModuleInstance

从对象返回模块实例 `CAtlBaseModule` 。

```cpp
HINSTANCE GetModuleInstance() throw();
```

### <a name="return-value"></a>返回值

返回模块实例。

## <a name="catlbasemodulegetresourceinstance"></a><a name="getresourceinstance"></a> CAtlBaseModule::GetResourceInstance

返回资源实例。

```cpp
HINSTANCE GetResourceInstance() throw();
```

### <a name="return-value"></a>返回值

返回资源实例。

## <a name="catlbasemodulem_binitfailed"></a><a name="m_binitfailed"></a> CAtlBaseModule：： m_bInitFailed

一个变量，指示模块初始化是否失败。

```cpp
static bool m_bInitFailed;
```

### <a name="remarks"></a>备注

如果模块已初始化，则为 True; 否则为 false。

## <a name="catlbasemoduleremoveresourceinstance"></a><a name="removeresourceinstance"></a> CAtlBaseModule::RemoveResourceInstance

从存储句柄的列表中删除资源实例。

```cpp
bool RemoveResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>parameters

*hInst*<br/>
要移除的资源实例。

### <a name="return-value"></a>返回值

如果已成功移除资源，则返回 true，否则返回 false。

## <a name="catlbasemodulesetresourceinstance"></a><a name="setresourceinstance"></a> CAtlBaseModule::SetResourceInstance

设置对象的资源实例 `CAtlBaseModule` 。

```cpp
HINSTANCE SetResourceInstance(HINSTANCE hInst) throw();
```

### <a name="parameters"></a>parameters

*hInst*<br/>
新资源实例。

### <a name="return-value"></a>返回值

返回已更新的资源实例。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)<br/>
[Module 类](../../atl/atl-module-classes.md)

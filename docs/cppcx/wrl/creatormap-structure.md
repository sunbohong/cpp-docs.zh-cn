---
description: 了解详细信息： CreatorMap 结构
title: CreatorMap 结构
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
- module/Microsoft::WRL::Details::CreatorMap::activationId
- module/Microsoft::WRL::Details::CreatorMap::factoryCache
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
- module/Microsoft::WRL::Details::CreatorMap::serverName
helpviewer_keywords:
- Microsoft::WRL::Details::CreatorMap structure
- Microsoft::WRL::Details::CreatorMap::activationId data member
- Microsoft::WRL::Details::CreatorMap::factoryCache data member
- Microsoft::WRL::Details::CreatorMap::factoryCreator data member
- Microsoft::WRL::Details::CreatorMap::serverName data member
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
ms.openlocfilehash: 0ef3b441390a22a6c4b35f274857ccb58de030d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273041"
---
# <a name="creatormap-structure"></a>CreatorMap 结构

支持 Windows 运行时 c + + 模板库基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
struct CreatorMap;
```

## <a name="remarks"></a>备注

介绍如何初始化、注册和撤消注册对象。

`CreatorMap` 包含下列信息：

- 如何初始化、注册和撤消注册对象。

- 如何根据经典 COM 或 Windows 运行时工厂对激活数据进行比较。

- 有关接口的工厂缓存和服务器名称的信息。

## <a name="members"></a>成员

### <a name="public-data-members"></a>公共数据成员

名称                                          | 描述
--------------------------------------------- | ------------------------------------------------------------------------------------------------------
[CreatorMap：： activationId](#activationid)     | 表示由经典 COM 类 ID 或 Windows 运行时名称标识的对象 ID。
[CreatorMap：： factoryCache](#factorycache)     | 将指针存储到的工厂缓存 `CreatorMap` 。
[CreatorMap：： factoryCreator](#factorycreator) | 为指定的创建工厂 `CreatorMap` 。
[CreatorMap：： serverName](#servername)         | 存储的服务器名称 `CreatorMap` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CreatorMap`

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="creatormapactivationid"></a><a name="activationid"></a> CreatorMap：： activationId

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
union {
   const IID* clsid;
   const wchar_t* (*getRuntimeName)();
} activationId;
```

### <a name="parameters"></a>parameters

*clsid*<br/>
接口 ID。

*getRuntimeName*<br/>
用于检索对象的 Windows 运行时名称的函数。

### <a name="remarks"></a>备注

表示由经典 COM 类 ID 或 Windows 运行时名称标识的对象 ID。

## <a name="creatormapfactorycache"></a><a name="factorycache"></a> CreatorMap：： factoryCache

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
FactoryCache* factoryCache;
```

### <a name="remarks"></a>备注

将指针存储到的工厂缓存 `CreatorMap` 。

## <a name="creatormapfactorycreator"></a><a name="factorycreator"></a> CreatorMap：： factoryCreator

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>parameters

*currentflags*<br/>
[RuntimeClassType](runtimeclasstype-enumeration.md)枚举器之一。

*条目*<br/>
CreatorMap。

*iidClassFactory*<br/>
类工厂的接口 ID。

*工厂*<br/>
操作完成后，为类工厂的地址。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

### <a name="remarks"></a>备注

为指定的 CreatorMap 创建一个工厂。

## <a name="creatormapservername"></a><a name="servername"></a> CreatorMap：： serverName

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
const wchar_t* serverName;
```

### <a name="remarks"></a>备注

存储 CreatorMap 的服务器名称。

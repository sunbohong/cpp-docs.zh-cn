---
description: 了解详细信息： FactoryCache 结构
title: FactoryCache 结构
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::FactoryCache
- module/Microsoft::WRL::Details::FactoryCache::cookie
- module/Microsoft::WRL::Details::FactoryCache::factory
helpviewer_keywords:
- Microsoft::WRL::Details::FactoryCache structure
- Microsoft::WRL::Details::FactoryCache::cookie data member
- Microsoft::WRL::Details::FactoryCache::factory data member
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
ms.openlocfilehash: 3e9ee084a063eb8094c309dee412a8793801921b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198541"
---
# <a name="factorycache-structure"></a>FactoryCache 结构

支持 Windows 运行时 c + + 模板库基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
struct FactoryCache;
```

## <a name="remarks"></a>备注

包含类工厂的位置以及用于标识已注册的 wrt 或 COM 类对象的值。

## <a name="members"></a>成员

### <a name="public-data-members"></a>公共数据成员

名称                              | 描述
--------------------------------- | ------------------------------------------------------------------------------------------------------------------------------
[FactoryCache：： cookie](#cookie)   | 包含一个值，该值标识已注册的 Windows 运行时或 COM 类对象，稍后用于取消注册对象。
[FactoryCache：： factory](#factory) | 指向 Windows 运行时或 COM 类工厂。

## <a name="inheritance-hierarchy"></a>继承层次结构

`FactoryCache`

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="factorycachecookie"></a><a name="cookie"></a> FactoryCache：： cookie

支持 Windows 运行时 c + + 模板库基础结构，不应在代码中直接使用。

```cpp
union {
   WINRT_REGISTRATION_COOKIE winrt;
   DWORD com;
} cookie;
```

### <a name="remarks"></a>备注

包含一个值，该值标识已注册的 Windows 运行时或 COM 类对象，稍后用于取消注册对象。

## <a name="factorycachefactory"></a><a name="factory"></a> FactoryCache：： factory

支持 Windows 运行时 c + + 模板库基础结构，不应在代码中直接使用。

```cpp
IUnknown* factory;
```

### <a name="remarks"></a>备注

指向 Windows 运行时或 COM 类工厂。

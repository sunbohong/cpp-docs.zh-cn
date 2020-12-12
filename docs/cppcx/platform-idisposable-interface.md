---
description: 了解更多： Platform：： IDisposable 接口
title: Platform::IDisposable 接口
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
ms.openlocfilehash: 0a1e7b44861d48f496f21d634d4d28ff1c968bcf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276772"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable 接口

用于释放非托管资源。

## <a name="syntax"></a>语法

```cpp
public interface class IDisposable
```

## <a name="attributes"></a>特性

**GuidAttribute** ( "de0cbaea-8065-4a45-b196-c9d443f9bab3" ) 

**VersionAttribute** (NTDDI_WIN8) 

### <a name="members"></a>成员

IDisposable 接口从 IUnknown 接口继承。 IDisposable 还具有下列类型的成员：

**方法**

IDisposable 接口具有以下方法。

|方法|描述|
|------------|-----------------|
|释放|用于释放非托管资源。|

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

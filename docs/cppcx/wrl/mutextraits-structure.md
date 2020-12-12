---
description: 了解详细信息： MutexTraits 结构
title: MutexTraits 结构
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::MutexTraits::Unlock method
ms.assetid: 6582df80-b9ba-4892-948f-d572a3b23d54
ms.openlocfilehash: e3dfcee1251794734ed5cf787096361403d80c7f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330827"
---
# <a name="mutextraits-structure"></a>MutexTraits 结构

定义 [Mutex](mutex-class.md) 类的公共特性。

## <a name="syntax"></a>语法

```cpp
struct MutexTraits : HANDLENullTraits;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

“属性”                           | 描述
------------------------------ | ------------------------------------------------
[MutexTraits：： Unlock](#unlock) | 释放共享资源的独占控制。

## <a name="inheritance-hierarchy"></a>继承层次结构

`HANDLENullTraits`

`MutexTraits`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装：： HandleTraits

## <a name="mutextraitsunlock-method"></a><a name="unlock"></a> MutexTraits：： Unlock 方法

释放共享资源的独占控制。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
Mutex 对象的句柄。

---
description: 了解详细信息： SemaphoreTraits 结构
title: SemaphoreTraits 结构
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SemaphoreTraits::Unlock method
ms.assetid: eddb8576-d063-409b-9201-cc87ca5d111e
ms.openlocfilehash: 5779a30d22fd2d32e57f96f752bb52e2bf469cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135221"
---
# <a name="semaphoretraits-structure"></a>SemaphoreTraits 结构

定义对象的常见特性 `Semaphore` 。

## <a name="syntax"></a>语法

```cpp
struct SemaphoreTraits : HANDLENullTraits;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

“属性”                               | 描述
---------------------------------- | --------------------------------------
[SemaphoreTraits：： Unlock](#unlock) | 释放对共享资源的控制。

## <a name="inheritance-hierarchy"></a>继承层次结构

`HANDLENullTraits`

`SemaphoreTraits`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装：： HandleTraits

## <a name="semaphoretraitsunlock"></a><a name="unlock"></a> SemaphoreTraits：： Unlock

释放对共享资源的控制。

```cpp
inline static void Unlock(
   _In_ Type h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
对象的句柄 `Semaphore` 。

### <a name="remarks"></a>备注

如果解除锁定操作失败，则 `Unlock()` 会发出错误，指出失败的原因。

---
description: 了解详细信息： SRWLockSharedTraits 结构
title: SRWLockSharedTraits 结构
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock method
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
ms.openlocfilehash: 2cdfbd584adeffc9dedd8504d9183d6c5d4c1a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135117"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 结构

描述 `SRWLock` 类在共享锁定模式下的常见特性。

## <a name="syntax"></a>语法

```cpp
struct SRWLockSharedTraits;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称   | 描述
------ | --------------------------------------------------------------------------
`Type` | 指向 [SRWLOCK](srwlock-class.md) 类的指针的同义词。

### <a name="public-methods"></a>公共方法

“属性”                                                     | 描述
-------------------------------------------------------- | -----------------------------------------------------------------
[SRWLockSharedTraits：： GetInvalidValue](#getinvalidvalue) | 检索 `SRWLockSharedTraits` 始终无效的对象。
[SRWLockSharedTraits：： Unlock](#unlock)                   | 释放指定对象的独占控件 `SRWLock` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`SRWLockSharedTraits`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装：： HandleTraits

## <a name="srwlocksharedtraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockSharedTraits：： GetInvalidValue

检索 `SRWLockSharedTraits` 始终无效的对象。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>返回值

对象的句柄 `SRWLockSharedTraits` 。

## <a name="srwlocksharedtraitsunlock"></a><a name="unlock"></a> SRWLockSharedTraits：： Unlock

释放指定对象的独占控件 `SRWLock` 。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>parameters

*srwlock*<br/>
对象的句柄 `SRWLock` 。

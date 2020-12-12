---
description: 了解详细信息： SRWLockExclusiveTraits 结构
title: SRWLockExclusiveTraits 结构
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::GetInvalidValue method
- Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock method
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
ms.openlocfilehash: 135d4f866d1ca32ee9170ef9844cb0bf8d38c29a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186202"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 结构

说明 `SRWLock` 类在排他锁模式下的常见特性。

## <a name="syntax"></a>语法

```cpp
struct SRWLockExclusiveTraits;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称   | 描述
------ | --------------------------------------------------------------------------
`Type` | 指向 [SRWLOCK](srwlock-class.md) 类的指针的同义词。

### <a name="public-methods"></a>公共方法

“属性”                                                        | 描述
----------------------------------------------------------- | --------------------------------------------------------------------
[SRWLockExclusiveTraits：： GetInvalidValue](#getinvalidvalue) | 检索 `SRWLockExclusiveTraits` 始终无效的对象。
[SRWLockExclusiveTraits：： Unlock](#unlock)                   | 释放指定对象的独占控件 `SRWLock` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`SRWLockExclusiveTraits`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装：： HandleTraits

## <a name="srwlockexclusivetraitsgetinvalidvalue"></a><a name="getinvalidvalue"></a> SRWLockExclusiveTraits：： GetInvalidValue

检索 `SRWLockExclusiveTraits` 始终无效的对象。

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>返回值

空的 `SRWLockExclusiveTraits` 对象。

## <a name="srwlockexclusivetraitsunlock"></a><a name="unlock"></a> SRWLockExclusiveTraits：： Unlock

释放指定对象的独占控件 `SRWLock` 。

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>parameters

*srwlock*<br/>
对象的句柄 `SRWLock` 。

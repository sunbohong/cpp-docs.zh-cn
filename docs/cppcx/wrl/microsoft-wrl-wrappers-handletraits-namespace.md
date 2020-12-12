---
description: 了解详细信息： Microsoft：： WRL：：包装：： HandleTraits 命名空间
title: Microsoft::WRL::Wrappers::HandleTraits 命名空间
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits
helpviewer_keywords:
- HandleTraits namespace
ms.assetid: 2fb5c6d1-bfc2-4e09-91eb-31705064ffb3
ms.openlocfilehash: 4bbc970a6d3445e8acda752be1a2030ee99759a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178051"
---
# <a name="microsoftwrlwrappershandletraits-namespace"></a>Microsoft::WRL::Wrappers::HandleTraits 命名空间

介绍常见的基于句柄的资源类型的特征。

## <a name="syntax"></a>语法

```cpp
namespace Microsoft::WRL::Wrappers::HandleTraits;
```

## <a name="members"></a>成员

### <a name="structures"></a>結構

|名称|描述|
|----------|-----------------|
|[CriticalSectionTraits 结构](criticalsectiontraits-structure.md)|专用化 `CriticalSection` 对象，以支持无效的临界区或函数以释放关键部分。|
|[EventTraits 结构](eventtraits-structure.md)|定义 `Event` 类句柄的特征。|
|[FileHandleTraits 结构](filehandletraits-structure.md)|定义文件句柄的特征。|
|[HANDLENullTraits 结构](handlenulltraits-structure.md)|定义未初始化的句柄的常见特性。|
|[HANDLETraits 结构](handletraits-structure.md)|定义句柄的常见特性。|
|[MutexTraits 结构](mutextraits-structure.md)|定义 [Mutex](mutex-class.md) 类的公共特性。|
|[SemaphoreTraits 结构](semaphoretraits-structure.md)|定义信号量对象的常见特性。|
|[SRWLockExclusiveTraits 结构](srwlockexclusivetraits-structure.md)|说明 `SRWLock` 类在排他锁模式下的常见特性。|
|[SRWLockSharedTraits 结构](srwlocksharedtraits-structure.md)|描述 `SRWLock` 类在共享锁定模式下的常见特性。|

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="see-also"></a>请参阅

[Microsoft：： WRL：：包装命名空间](microsoft-wrl-wrappers-namespace.md)

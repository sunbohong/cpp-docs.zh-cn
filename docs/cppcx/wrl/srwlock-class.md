---
description: 了解详细信息： SRWLock 类
title: SRWLock 类
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::SRWLock_
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::~SRWLock
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
helpviewer_keywords:
- Microsoft::WRL::Wrappers::SRWLock class
- Microsoft::WRL::Wrappers::SRWLock::LockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::LockShared method
- Microsoft::WRL::Wrappers::SRWLock::SRWLock, constructor
- Microsoft::WRL::Wrappers::SRWLock::SRWLock_ data member
- Microsoft::WRL::Wrappers::SRWLock::~SRWLock, destructor
- Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive method
- Microsoft::WRL::Wrappers::SRWLock::TryLockShared method
ms.assetid: 4fa250e3-5f29-4b06-ac24-61b6c04ade93
ms.openlocfilehash: 10bc3dc700f90d5154ece1546cdf3ec464ea6e56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135182"
---
# <a name="srwlock-class"></a>SRWLock 类

表示精简读取器/编写器锁定。

## <a name="syntax"></a>语法

```cpp
class SRWLock;
```

## <a name="remarks"></a>备注

超薄读取器/写入器锁用于同步跨线程对对象或资源的访问。 有关详细信息，请参阅 [同步函数](/windows/win32/Sync/synchronization-functions)。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称                | 描述
------------------- | -------------------------------------------------------------------
`SyncLockExclusive` | `SRWLock`以独占模式获取的对象的同义词。
`SyncLockShared`    | `SRWLock`在共享模式下获取的对象的同义词。

### <a name="public-constructors"></a>公共构造函数

“属性”                                     | 描述
---------------------------------------- | --------------------------------------------------
[SRWLock：： SRWLock](#srwlock-constructor) | 初始化 `SRWLock` 类的新实例。
[SRWLock：： ~ SRWLock](#tilde-srwlock)      | 取消初始化类的实例 `SRWLock` 。

### <a name="public-methods"></a>公共方法

“属性”                                           | 描述
---------------------------------------------- | -------------------------------------------------------------------------------------------------------
[SRWLock：： LockExclusive](#lockexclusive)       | 获取 `SRWLock` 独占模式下的对象。
[SRWLock：： LockShared](#lockshared)             | 获取 `SRWLock` 共享模式下的对象。
[SRWLock：： TryLockExclusive](#trylockexclusive) | 尝试以 `SRWLock` 独占模式获取当前或指定对象的对象 `SRWLock` 。
[SRWLock：： TryLockShared](#trylockshared)       | 尝试为 `SRWLock` 当前或指定的对象获取共享模式下的对象 `SRWLock` 。

### <a name="protected-data-member"></a>受保护的数据成员

名称                                      | 描述
----------------------------------------- | -----------------------------------------------------------------------
[SRWLock：： SRWLock_](#srwlock-data-member) | 包含当前对象的基础锁变量 `SRWLock` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`SRWLock`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="srwlocksrwlock"></a><a name="tilde-srwlock"></a> SRWLock：： ~ SRWLock

取消初始化类的实例 `SRWLock` 。

```cpp
~SRWLock();
```

## <a name="srwlocklockexclusive"></a><a name="lockexclusive"></a> SRWLock：： LockExclusive

获取 `SRWLock` 独占模式下的对象。

```cpp
SyncLockExclusive LockExclusive();

static SyncLockExclusive LockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>parameters

*lock*<br/>
指向对象的指针 `SRWLock` 。

### <a name="return-value"></a>返回值

`SRWLock`独占模式下的对象。

## <a name="srwlocklockshared"></a><a name="lockshared"></a> SRWLock：： LockShared

获取 `SRWLock` 共享模式下的对象。

```cpp
SyncLockShared LockShared();

static SyncLockShared LockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>parameters

*lock*<br/>
指向对象的指针 `SRWLock` 。

### <a name="return-value"></a>返回值

`SRWLock`处于共享模式的对象。

## <a name="srwlocksrwlock"></a><a name="srwlock-constructor"></a> SRWLock：： SRWLock

初始化 `SRWLock` 类的新实例。

```cpp
SRWLock();
```

## <a name="srwlocksrwlock_"></a><a name="srwlock-data-member"></a> SRWLock：： SRWLock_

包含当前对象的基础锁变量 `SRWLock` 。

```cpp
SRWLOCK SRWLock_;
```

## <a name="srwlocktrylockexclusive"></a><a name="trylockexclusive"></a> SRWLock：： TryLockExclusive

尝试以 `SRWLock` 独占模式获取当前或指定对象的对象 `SRWLock` 。 如果调用成功，则调用线程获取锁的所有权。

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>parameters

*lock*<br/>
指向对象的指针 `SRWLock` 。

### <a name="return-value"></a>返回值

如果成功，则 `SRWLock` 处于独占模式的对象和调用线程取得锁的所有权。 否则为 `SRWLock` 其状态无效的对象。

## <a name="srwlocktrylockshared"></a><a name="trylockshared"></a> SRWLock：： TryLockShared

尝试为 `SRWLock` 当前或指定的对象获取共享模式下的对象 `SRWLock` 。

```cpp
WRL_NOTHROW SyncLockShared TryLockShared();
WRL_NOTHROW static SyncLockShared TryLockShared(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>parameters

*lock*<br/>
指向对象的指针 `SRWLock` 。

### <a name="return-value"></a>返回值

如果成功，则 `SRWLock` 处于共享模式的对象和调用线程取得锁的所有权。 否则为 `SRWLock` 其状态无效的对象。

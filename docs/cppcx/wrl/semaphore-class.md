---
description: 详细了解：信号量类
title: Semaphore 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Semaphore class
- Microsoft::WRL::Wrappers::Semaphore::Lock method
- Microsoft::WRL::Wrappers::Semaphore::operator= operator
- Microsoft::WRL::Wrappers::Semaphore::Semaphore, constructor
ms.assetid: ded53526-17b4-4381-9c60-ea5e77363db6
ms.openlocfilehash: 0cf99ff0a0e5263b3ed924ec5ac69b7edb0bd1f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186228"
---
# <a name="semaphore-class"></a>Semaphore 类

表示控制可支持有限数量用户的共享资源的同步对象。

## <a name="syntax"></a>语法

```cpp
class Semaphore : public HandleT<HandleTraits::SemaphoreTraits>;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称       | 描述
---------- | ------------------------------------------------------
`SyncLock` | 支持同步锁定的类的同义词。

### <a name="public-constructors"></a>公共构造函数

“属性”                               | 描述
---------------------------------- | ----------------------------------------------------
[信号灯：：信号灯](#semaphore) | 初始化 `Semaphore` 类的新实例。

### <a name="public-methods"></a>公共方法

“属性”                     | 描述
------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------
[信号灯：： Lock](#lock) | 等待当前对象或与指定句柄关联的对象处于终止状态或指定的超时间隔已过。

### <a name="public-operators"></a>公共运算符

名称                                     | 描述
---------------------------------------- | ---------------------------------------------------------------------------------------
[信号灯：： operator =](#operator-assign) | 将指定的句柄从 `Semaphore` 对象移到当前 `Semaphore` 对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

`Semaphore`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="semaphorelock"></a><a name="lock"></a> 信号灯：： Lock

等待当前对象或 `Semaphore` 与指定句柄关联的对象处于终止状态或指定的超时间隔已过。

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>parameters

milliseconds<br/>
超时间隔（以毫秒为单位）。 默认值为 INFINITE，其表示将无限期地等待。

*h*<br/>
对象的句柄 `Semaphore` 。

### <a name="return-value"></a>返回值

一个 `Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`

## <a name="semaphoreoperator"></a><a name="operator-assign"></a> 信号灯：： operator =

将指定的句柄从 `Semaphore` 对象移到当前 `Semaphore` 对象。

```cpp
Semaphore& operator=(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
右值-对对象的引用 `Semaphore` 。

### <a name="return-value"></a>返回值

对当前对象的引用 `Semaphore` 。

## <a name="semaphoresemaphore"></a><a name="semaphore"></a> 信号灯：：信号灯

初始化 `Semaphore` 类的新实例。

```cpp
explicit Semaphore(
   HANDLE h
);

WRL_NOTHROW Semaphore(
   _Inout_ Semaphore&& h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
对象的句柄或 rvalue 引用 `Semaphore` 。

---
description: 了解详细信息： Mutex 类
title: Mutex 类
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Lock
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
- corewrappers/Microsoft::WRL::Wrappers::Mutex::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Mutex class
- Microsoft::WRL::Wrappers::Mutex::Lock method
- Microsoft::WRL::Wrappers::Mutex::Mutex, constructor
- Microsoft::WRL::Wrappers::Mutex::operator= operator
ms.assetid: 682a0963-721c-46a2-8871-000e9997505b
ms.openlocfilehash: f69c14014a2283fe56ef8e7f705bebe5a5f6dc9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330837"
---
# <a name="mutex-class"></a>Mutex 类

表示完全控制共享资源的同步对象。

## <a name="syntax"></a>语法

```cpp
class Mutex : public HandleT<HandleTraits::MutexTraits>;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称       | 描述
---------- | ------------------------------------------------------
`SyncLock` | 支持同步锁定的类的同义词。

### <a name="public-constructor"></a>公共构造函数

名称                   | 描述
---------------------- | ------------------------------------------------
[Mutex：： Mutex](#mutex) | 初始化 `Mutex` 类的新实例。

### <a name="public-members"></a>公共成员

名称                 | 描述
-------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------
[Mutex：： Lock](#lock) | 等待当前对象或 `Mutex` 与指定句柄关联的对象释放 mutex 或指定的超时间隔已过。

### <a name="public-operator"></a>公共运算符

名称                                 | 描述
------------------------------------ | ---------------------------------------------------------------------------
[Mutex：： operator =](#operator-assign) | 将指定对象)  (移动 `Mutex` 到当前 `Mutex` 对象。

## <a name="inheritance-hierarchy"></a>继承层次结构

`Mutex`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="mutexlock"></a><a name="lock"></a> Mutex：： Lock

等待当前对象或 `Mutex` 与指定句柄关联的对象释放 mutex 或指定的超时间隔已过。

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
对象的句柄 `Mutex` 。

### <a name="return-value"></a>返回值

## <a name="mutexmutex"></a><a name="mutex"></a> Mutex：： Mutex

初始化 `Mutex` 类的新实例。

```cpp
explicit Mutex(
   HANDLE h
);

Mutex(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
指向对象的句柄（或对句柄的右值引用） `Mutex` 。

### <a name="remarks"></a>备注

第一个构造函数 `Mutex` 从指定的句柄初始化一个对象。 第二个构造函数 `Mutex` 从指定的句柄初始化对象，然后将该 mutex 的所有权转移到当前 `Mutex` 对象。

## <a name="mutexoperator"></a><a name="operator-assign"></a> Mutex：： operator =

将指定对象)  (移动 `Mutex` 到当前 `Mutex` 对象。

```cpp
Mutex& operator=(
   _Inout_ Mutex&& h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
对对象的 rvalue 引用 `Mutex` 。

### <a name="return-value"></a>返回值

对当前对象的引用 `Mutex` 。

### <a name="remarks"></a>备注

有关详细信息，请参阅 [右值引用声明符](../../cpp/rvalue-reference-declarator-amp-amp.md)的 **移动语义** 部分：  &&。

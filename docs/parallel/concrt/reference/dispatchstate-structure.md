---
description: 了解详细信息： DispatchState 结构
title: DispatchState 结构
ms.date: 11/04/2016
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
ms.openlocfilehash: 1352a283d6f75d90872e75da92450a4867cf497f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169419"
---
# <a name="dispatchstate-structure"></a>DispatchState 结构

`DispatchState` 结构用于将状态传输给 `IExecutionContext::Dispatch` 方法。 它描述了在 `IExecutionContext` 接口上调用 `Dispatch` 方法的情形。

## <a name="syntax"></a>语法

```cpp
struct DispatchState;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[DispatchState：:D ispatchState](#ctor)|构造新的 `DispatchState` 对象。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[DispatchState：： m_dispatchStateSize](#m_dispatchstatesize)|此结构的大小，用于版本控制。|
|[DispatchState：： m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|指示此上下文是否已进入 `Dispatch` 方法，因为上一个上下文已异步阻止。 这仅用于 UMS 计划上下文，并设置为 `0` 所有其他执行上下文的值。|
|[DispatchState：： m_reserved](#m_reserved)|保留以供将来信息通过的 Bits。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`DispatchState`

## <a name="requirements"></a>要求

**标头：** concrtrm。h

**命名空间：** 并发

## <a name="dispatchstatedispatchstate-constructor"></a><a name="ctor"></a> DispatchState：:D ispatchState 构造函数

构造新的 `DispatchState` 对象。

```cpp
DispatchState();
```

## <a name="dispatchstatem_dispatchstatesize-data-member"></a><a name="m_dispatchstatesize"></a> DispatchState：： m_dispatchStateSize 数据成员

此结构的大小，用于版本控制。

```cpp
unsigned long m_dispatchStateSize;
```

## <a name="dispatchstatem_fispreviouscontextasynchronouslyblocked-data-member"></a><a name="m_fispreviouscontextasynchronouslyblocked"></a> DispatchState：： m_fIsPreviousContextAsynchronouslyBlocked 数据成员

指示此上下文是否已进入 `Dispatch` 方法，因为上一个上下文已异步阻止。 这仅用于 UMS 计划上下文，并设置为 `0` 所有其他执行上下文的值。

```cpp
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

## <a name="dispatchstatem_reserved-data-member"></a><a name="m_reserved"></a> DispatchState：： m_reserved 数据成员

保留以供将来信息通过的 Bits。

```cpp
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)

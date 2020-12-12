---
description: 了解详细信息： ModuleBase 类
title: ModuleBase 类
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 6540068cee62da5d1a9039a15bcb5bd53ff3aea2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186241"
---
# <a name="modulebase-class"></a>ModuleBase 类

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
class ModuleBase;
```

## <a name="remarks"></a>备注

表示 [模块](module-class.md) 类的基类。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

“属性”                                         | 描述
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase：： ModuleBase](#modulebase)        | 初始化 `Module` 类的实例。
[ModuleBase：： ~ ModuleBase](#tilde-modulebase) | 取消初始化类的当前实例 `Module` 。

### <a name="public-methods"></a>公共方法

“属性”                                                      | 描述
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase：:D ecrementObjectCount](#decrementobjectcount) | 实现时，将减少模块跟踪的对象数。
[ModuleBase：： IncrementObjectCount](#incrementobjectcount) | 实现时，将增加模块跟踪的对象数。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ModuleBase`

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="modulebasemodulebase"></a><a name="tilde-modulebase"></a> ModuleBase：： ~ ModuleBase

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>备注

取消初始化类的当前实例 `ModuleBase` 。

## <a name="modulebasedecrementobjectcount"></a><a name="decrementobjectcount"></a> ModuleBase：:D ecrementObjectCount

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>返回值

递减操作之前的计数。

### <a name="remarks"></a>备注

实现时，将减少模块跟踪的对象数。

## <a name="modulebaseincrementobjectcount"></a><a name="incrementobjectcount"></a> ModuleBase：： IncrementObjectCount

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>返回值

递增操作之前的计数。

### <a name="remarks"></a>备注

实现时，将增加模块跟踪的对象数。

## <a name="modulebasemodulebase"></a><a name="modulebase"></a> ModuleBase：： ModuleBase

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
ModuleBase();
```

### <a name="remarks"></a>备注

初始化 `Module` 类的实例。

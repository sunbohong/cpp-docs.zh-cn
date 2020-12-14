---
description: 了解详细信息： task_handle 类
title: task_handle 类
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 21fa2a1782fad200061deb1e85bf052613354a34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188217"
---
# <a name="task_handle-class"></a>task_handle 类

`task_handle` 类表示单个并行工作项。 它封装执行一项工作所需的指令和数据。

## <a name="syntax"></a>语法

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>parameters

*_Function*<br/>
将调用以执行由对象表示的工作的函数对象的类型 `task_handle` 。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[task_handle](#task_handle)|构造新的 `task_handle` 对象。 任务的工作是通过调用指定为构造函数的参数的函数来执行的。|
|[~ task_handle 析构函数](#dtor)|销毁 `task_handle` 对象。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[运算符 ( # B1 ](#task_handle__operator_call)|运行时调用以执行任务句柄工作的函数调用运算符。|

## <a name="remarks"></a>备注

`task_handle` 对象可以与 `structured_task_group` 或更通用的对象结合使用 `task_group` ，以便将工作分解为并行任务。 有关详细信息，请参阅 [任务并行](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)。

请注意，对象的创建者 `task_handle` 负责维护所创建的对象的生存期， `task_handle` 直至并发运行时不再需要它。 通常，这意味着在调用了对象的或的 `task_handle` 方法之前，对象不能析构 `wait` `run_and_wait` `task_group` `structured_task_group` 。

`task_handle` 对象通常与 c + + lambda 一起使用。 由于你不知道 lambda 的真正类型，因此 [make_task](concurrency-namespace-functions.md#make_task) 函数通常用于创建 `task_handle` 对象。

运行时创建您传递给对象的工作函数的副本 `task_handle` 。 因此，传递到对象的函数对象中发生的任何状态更改 `task_handle` 都不会出现在该函数对象的副本中。

## <a name="inheritance-hierarchy"></a>继承层次结构

`task_handle`

## <a name="requirements"></a>要求

**标头：** ppl。h

**命名空间：** 并发

## <a name="operator"></a><a name="task_handle__operator_call"></a> 运算符 ( # A1

运行时调用以执行任务句柄工作的函数调用运算符。

```cpp
void operator()() const;
```

## <a name="task_handle"></a><a name="task_handle"></a> task_handle

构造新的 `task_handle` 对象。 任务的工作是通过调用指定为构造函数的参数的函数来执行的。

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>parameters

*_Func*<br/>
将调用以执行由对象表示的工作的函数 `task_handle` 。 这可能是 lambda 函子、指向函数的指针或支持具有签名的函数调用运算符版本的任何对象 `void operator()()` 。

### <a name="remarks"></a>备注

运行时创建要传递给构造函数的工作函数的副本。 因此，传递到对象的函数对象中发生的任何状态更改 `task_handle` 都不会出现在该函数对象的副本中。

## <a name="task_handle"></a><a name="dtor"></a> ~ task_handle

销毁 `task_handle` 对象。

```cpp
~task_handle();
```

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[task_group 类](task-group-class.md)<br/>
[structured_task_group 类](structured-task-group-class.md)

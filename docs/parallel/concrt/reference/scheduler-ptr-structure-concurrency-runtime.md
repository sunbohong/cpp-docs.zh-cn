---
description: 了解详细信息： scheduler_ptr 结构
title: scheduler_ptr 结构
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 314f587c0fd55772a8b1b7b5b8fdf3ddeb53a7a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188776"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr 结构

表示指向计划程序的指针。 此类可用于通过使用 shared_ptr 或仅通过使用原始指针来指定共享生存期。

## <a name="syntax"></a>语法

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[scheduler_ptr：： scheduler_ptr](#ctor)|已重载。 创建一个从 shared_ptr 到计划程序的计划程序指针|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[scheduler_ptr：： get](#get)|返回指向计划程序的原始指针|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[scheduler_ptr：： operator bool](#operator_bool)|测试计划程序指针是否为非 null|
|[scheduler_ptr：： operator-&gt;](#operator_ptr)|行为类似于指针|

## <a name="inheritance-hierarchy"></a>继承层次结构

`scheduler_ptr`

## <a name="requirements"></a>要求

**标头：** pplinterface。h

**命名空间：** 并发

## <a name="scheduler_ptrget-method"></a><a name="get"></a> scheduler_ptr：： get 方法

返回指向计划程序的原始指针。

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>返回值

## <a name="scheduler_ptroperator-bool"></a><a name="operator_bool"></a> scheduler_ptr：： operator bool

测试计划程序指针是否为非 null。

```cpp
operator bool() const;
```

## <a name="scheduler_ptroperator-gt"></a><a name="operator_ptr"></a> scheduler_ptr：： operator-&gt;

的行为类似于指针。

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>返回值

## <a name="scheduler_ptrscheduler_ptr-constructor"></a><a name="ctor"></a> scheduler_ptr：： scheduler_ptr 构造函数

创建从 shared_ptr 到计划程序的计划程序指针。

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>parameters

*日程*<br/>
要转换的计划程序。

*pScheduler*<br/>
要转换的计划程序指针。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)

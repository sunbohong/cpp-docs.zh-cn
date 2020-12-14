---
description: 了解详细信息： static_partitioner 类
title: static_partitioner 类
ms.date: 11/04/2016
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
ms.openlocfilehash: f75d2e620a66e0ed347d39d429f59e3e2715369a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188490"
---
# <a name="static_partitioner-class"></a>static_partitioner 类

`static_partitioner` 类表示由 `parallel_for` 循环访问的范围的静态分区。 分区程序将范围划分为多个块，因为有可用于基础计划程序的工作线程。

## <a name="syntax"></a>语法

```cpp
class static_partitioner;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[static_partitioner](#ctor)|构造 `static_partitioner` 对象。|
|[~ static_partitioner 析构函数](#dtor)|销毁 `static_partitioner` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`static_partitioner`

## <a name="requirements"></a>要求

**标头：** ppl。h

**命名空间：** 并发

## <a name="static_partitioner"></a><a name="dtor"></a> ~ static_partitioner

销毁 `static_partitioner` 对象。

```cpp
~static_partitioner();
```

## <a name="static_partitioner"></a><a name="ctor"></a> static_partitioner

构造 `static_partitioner` 对象。

```cpp
static_partitioner();
```

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)

---
description: 了解详细信息： affinity_partitioner 类
title: affinity_partitioner 类
ms.date: 11/04/2016
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
ms.openlocfilehash: 44aa693d5007507e33f062a673713d1ddbda3172
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172318"
---
# <a name="affinity_partitioner-class"></a>affinity_partitioner 类

`affinity_partitioner` 类与 `static_partitioner` 类相似，但它选择将子范围映射到工作线程，从而改善缓存关联。 在同一数据集中重新执行循环且数据适应缓存时，它可以显著提高性能。 请注意，必须与在特定数据集中执行的并行循环的后续迭代一起使用同一 `affinity_partitioner` 对象，才能受益于数据位置。

## <a name="syntax"></a>语法

```cpp
class affinity_partitioner;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[affinity_partitioner](#ctor)|构造 `affinity_partitioner` 对象。|
|[~ affinity_partitioner 析构函数](#dtor)|销毁 `affinity_partitioner` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`affinity_partitioner`

## <a name="requirements"></a>要求

**标头：** ppl。h

**命名空间：** 并发

## <a name="affinity_partitioner"></a><a name="dtor"></a> ~ affinity_partitioner

销毁 `affinity_partitioner` 对象。

```cpp
~affinity_partitioner();
```

## <a name="affinity_partitioner"></a><a name="ctor"></a> affinity_partitioner

构造 `affinity_partitioner` 对象。

```cpp
affinity_partitioner();
```

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)

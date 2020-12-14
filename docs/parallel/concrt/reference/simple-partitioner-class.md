---
description: 了解详细信息： simple_partitioner 类
title: simple_partitioner 类
ms.date: 11/04/2016
f1_keywords:
- simple_partitioner
- PPL/concurrency::simple_partitioner
- PPL/concurrency::simple_partitioner::simple_partitioner
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
ms.openlocfilehash: 76dcac6d7fc2dce5b69d0a9dbefaf01420f8bcde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188685"
---
# <a name="simple_partitioner-class"></a>simple_partitioner 类

`simple_partitioner` 类表示由 `parallel_for` 循环访问的范围的静态分区。 分区程序将该范围分成区块，以便每个区块都至少具有区块大小指定的迭代数量。

## <a name="syntax"></a>语法

```cpp
class simple_partitioner;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[simple_partitioner](#ctor)|构造 `simple_partitioner` 对象。|
|[~ simple_partitioner 析构函数](#dtor)|销毁 `simple_partitioner` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`simple_partitioner`

## <a name="requirements"></a>要求

**标头：** ppl。h

**命名空间：** 并发

## <a name="simple_partitioner"></a><a name="dtor"></a> ~ simple_partitioner

销毁 `simple_partitioner` 对象。

```cpp
~simple_partitioner();
```

## <a name="simple_partitioner"></a><a name="ctor"></a> simple_partitioner

构造 `simple_partitioner` 对象。

```cpp
explicit simple_partitioner(_Size_type _Chunk_size);
```

### <a name="parameters"></a>parameters

*_Chunk_size*<br/>
最小分区大小。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)

---
description: 了解详细信息： tiled_extent 类
title: tiled_extent 类
ms.date: 11/04/2016
f1_keywords:
- tiled_extent
- AMP/tiled_extent
- AMP/Concurrency::tiled_extent::tiled_extent
- AMP/Concurrency::tiled_extent::get_tile_extent
- AMP/Concurrency::tiled_extent::pad
- AMP/Concurrency::tiled_extent::truncate
- AMP/Concurrency::tiled_extent::tile_dim0
- AMP/Concurrency::tiled_extent::tile_dim1
- AMP/Concurrency::tiled_extent::tile_dim2
- AMP/Concurrency::tiled_extent::tile_extent
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
ms.openlocfilehash: ca5b5c630152263ca49adf5c201ee0b892a192c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163868"
---
# <a name="tiled_extent-class"></a>tiled_extent 类

`tiled_extent`对象是 `extent` 一到三个维度的对象，它将范围空间细分为一维、二维或三维平铺。

## <a name="syntax"></a>语法

```cpp
template <
    int _Dim0,
    int _Dim1,
    int _Dim2
>
class tiled_extent : public Concurrency::extent<3>;

template <
    int _Dim0,
    int _Dim1
>
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;

template <
    int _Dim0
>
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;
```

### <a name="parameters"></a>parameters

*_Dim0*<br/>
最有效维度的长度。

*_Dim1*<br/>
最后面的重要维度的长度。

*_Dim2*<br/>
最小的有效维度的长度。

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[tiled_extent 构造函数](#ctor)|初始化 `tiled_extent` 类的新实例。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[get_tile_extent](#get_tile_extent)|返回 `extent` 捕获 `tiled_extent` 模板参数、和的值的对象 `_Dim0` `_Dim1` `_Dim2` 。|
|[类似](#pad)|返回一个新的 `tiled_extent` 对象，其中的区向上调整，以使磁贴尺寸可以整除。|
|[truncate](#truncate)|返回一个新的 `tiled_extent` 对象，其中的区向下调整为可被图块尺寸均匀分配。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[operator =](#operator_eq)|将指定对象的内容复制 `tiled_index` 到此对象中。|

### <a name="public-constants"></a>公共常量

|名称|描述|
|----------|-----------------|
|[tile_dim0 常量](#tile_dim0)|存储最高有效维度的长度。|
|[tile_dim1 常量](#tile_dim1)|存储下一个到最重要的维度的长度。|
|[tile_dim2 常量](#tile_dim2)|存储最不重要维度的长度。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[tile_extent](#tile_extent)|获取 `extent` 捕获 `tiled_extent` 模板参数、和的值的对象 `_Dim0` `_Dim1` `_Dim2` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`extent`

`tiled_extent`

## <a name="requirements"></a>要求

**标头：** amp.h

**命名空间：** 并发

## <a name="tiled_extent-constructor"></a><a name="ctor"></a> Tiled_extent 构造函数

初始化 `tiled_extent` 类的新实例。

### <a name="syntax"></a>语法

```cpp
tiled_extent();

tiled_extent(
    const Concurrency::extent<rank>& _Other );

tiled_extent(
    const tiled_extent& _Other );
```

### <a name="parameters"></a>parameters

*_Other*<br/>
`extent` `tiled_extent` 要复制的或对象。

## <a name="get_tile_extent"></a><a name="get_tile_extent"></a> get_tile_extent

返回 `extent` 捕获 `tiled_extent` 模板参数、和的值的对象 `_Dim0` `_Dim1` `_Dim2` 。

### <a name="syntax"></a>语法

```cpp
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);
```

### <a name="return-value"></a>返回值

`extent`捕获此实例的维度的对象 `tiled_extent` 。

## <a name="pad"></a><a name="pad"></a>填充

返回一个新的 `tiled_extent` 对象，其中的区向上调整，以使磁贴尺寸可以整除。

### <a name="syntax"></a>语法

```cpp
tiled_extent pad() const;
```

### <a name="return-value"></a>返回值

新的 `tiled_extent` 对象，按值。

## <a name="truncate"></a><a name="truncate"></a>截断

返回一个新的 `tiled_extent` 对象，其中的区向下调整为可被图块尺寸均匀分配。

### <a name="syntax"></a>语法

```cpp
tiled_extent truncate() const;
```

### <a name="return-value"></a>返回值

返回一个新的 `tiled_extent` 对象，其中的区向下调整为可被图块尺寸均匀分配。

## <a name="operator"></a><a name="operator_eq"></a> operator =

将指定对象的内容复制 `tiled_index` 到此对象中。

### <a name="syntax"></a>语法

```cpp
tiled_extent&  operator= (
    const tiled_extent& _Other ) restrict (amp, cpu);
```

### <a name="parameters"></a>parameters

*_Other*<br/>
`tiled_index`要从中进行复制的对象。

### <a name="return-value"></a>返回值

对此实例的引用 `tiled_index` 。

## <a name="tile_dim0"></a><a name="tile_dim0"></a> tile_dim0

存储最高有效维度的长度。

### <a name="syntax"></a>语法

```cpp
static const int tile_dim0 = _Dim0;
```

## <a name="tile_dim1"></a><a name="tile_dim1"></a> tile_dim1

存储下一个到最重要的维度的长度。

### <a name="syntax"></a>语法

```cpp
static const int tile_dim1 = _Dim1;
```

## <a name="tile_dim2"></a><a name="tile_dim2"></a> tile_dim2

存储最不重要维度的长度。

### <a name="syntax"></a>语法

```cpp
static const int tile_dim2 = _Dim2;
```

## <a name="tile_extent"></a><a name="tile_extent"></a> tile_extent

获取 `extent` 捕获 `tiled_extent` 模板参数、和的值的对象 `_Dim0` `_Dim1` `_Dim2` 。

### <a name="syntax"></a>语法

```cpp
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;
```

## <a name="see-also"></a>请参阅

[并发命名空间 (C++ AMP) ](concurrency-namespace-cpp-amp.md)

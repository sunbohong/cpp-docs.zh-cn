---
description: 了解详细信息： float_2 类
title: float_2 类
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_2::yx
- amp_short_vectors/Concurrency::graphics::float_2::operator-=
- amp_short_vectors/Concurrency::graphics::float_2::operator++
- amp_short_vectors/Concurrency::graphics::float_2::operator-
- amp_short_vectors/Concurrency::graphics::float_2::r
- amp_short_vectors/Concurrency::graphics::float_2::get_yx
- amp_short_vectors/Concurrency::graphics::float_2::get_xy
- amp_short_vectors/Concurrency::graphics::float_2::operator/=
- amp_short_vectors/Concurrency::graphics::float_2::set_yx
- amp_short_vectors/Concurrency::graphics::float_2::x
- amp_short_vectors/Concurrency::graphics::float_2::get_y
- amp_short_vectors/Concurrency::graphics::float_2::operator+=
- amp_short_vectors/Concurrency::graphics::float_2::gr
- amp_short_vectors/Concurrency::graphics::float_2::operator=
- amp_short_vectors/Concurrency::graphics::float_2::set_x
- amp_short_vectors/Concurrency::graphics::float_2::operator--
- amp_short_vectors/Concurrency::graphics::float_2::get_x
- amp_short_vectors/Concurrency::graphics::float_2::operator*=
- amp_short_vectors/Concurrency::graphics::float_2::rg
- amp_short_vectors/Concurrency::graphics::float_2::set_xy
- amp_short_vectors/Concurrency::graphics::float_2::xy
- amp_short_vectors/Concurrency::graphics::float_2
- amp_short_vectors/Concurrency::graphics::float_2::set_y
- amp_short_vectors/Concurrency::graphics::float_2::y
- amp_short_vectors/Concurrency::graphics::float_2::g
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
ms.openlocfilehash: a0d350c9742da6c11a5bf982a1638a1fc0921eb9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325845"
---
# <a name="float_2-class"></a>float_2 类

表示两个浮点数的短矢量。

## <a name="syntax"></a>语法

```cpp
class float_2;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[float_2 构造函数](#ctor)|已重载。 默认构造函数，用0初始化所有元素。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|float_2：： get_x||
|float_2：： get_xy||
|float_2：： get_y||
|float_2：： get_yx||
|float_2：： ref_g||
|float_2：： ref_r||
|float_2：： ref_x||
|float_2：： ref_y||
|float_2：： set_x||
|float_2：： set_xy||
|float_2：： set_y||
|float_2：： set_yx||

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|float_2：： operator-||
|float_2：： operator--||
|float_2：： operator * =||
|float_2：： operator/=||
|float_2：： operator + +||
|float_2：： operator + =||
|float_2：： operator =||
|float_2：： operator-=||

### <a name="public-constants"></a>公共常量

|名称|描述|
|----------|-----------------|
|[大小常量](#float_2__size)||

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|float_2：： g||
|float_2：： gr||
|float_2：： r||
|float_2：： rg||
|float_2：： x||
|float_2：： xy||
|float_2：： y||
|float_2：： yx||

## <a name="inheritance-hierarchy"></a>继承层次结构

`float_2`

## <a name="requirements"></a>要求

**标头：** amp_short_vectors。h

**命名空间：** Concurrency：： graphics

## <a name="float_2"></a><a name="ctor"></a> float_2

默认构造函数，用0初始化所有元素。

```cpp
float_2() restrict(amp,
    cpu);

float_2(
    float _V0,
    float _V1) restrict(amp,
    cpu);

float_2(
    float _V) restrict(amp,
    cpu);

float_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline float_2(
    const double_2& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>parameters

*_V0*<br/>
要初始化元素0的值。

*_V1*<br/>
要初始化元素1的值。

*_V*<br/>
用于初始化的值。

*_Other*<br/>
用于初始化的对象。

## <a name="size"></a><a name="float_2__size"></a> 规格

```cpp
static const int size = 2;
```

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)

---
description: 了解详细信息： int_2 类
title: int_2 类
ms.date: 11/04/2016
f1_keywords:
- amp_short_vectors/Concurrency::graphics::int_2::y
- amp_short_vectors/Concurrency::graphics::int_2::set_x
- amp_short_vectors/Concurrency::graphics::int_2::set_y
- amp_short_vectors/Concurrency::graphics::int_2::get_yx
- amp_short_vectors/Concurrency::graphics::int_2::operator++
- amp_short_vectors/Concurrency::graphics::int_2::x
- amp_short_vectors/Concurrency::graphics::int_2::set_yx
- amp_short_vectors/Concurrency::graphics::int_2::operator/=
- amp_short_vectors/Concurrency::graphics::int_2::get_y
- amp_short_vectors/Concurrency::graphics::int_2::gr
- amp_short_vectors/Concurrency::graphics::int_2::operator*=
- amp_short_vectors/Concurrency::graphics::int_2::r
- amp_short_vectors/Concurrency::graphics::int_2::get_xy
- amp_short_vectors/Concurrency::graphics::int_2::operator=
- amp_short_vectors/Concurrency::graphics::int_2::g
- amp_short_vectors/Concurrency::graphics::int_2::rg
- amp_short_vectors/Concurrency::graphics::int_2::xy
- amp_short_vectors/Concurrency::graphics::int_2::operator-=
- amp_short_vectors/Concurrency::graphics::int_2::get_x
- amp_short_vectors/Concurrency::graphics::int_2::yx
- amp_short_vectors/Concurrency::graphics::int_2
- amp_short_vectors/Concurrency::graphics::int_2::operator-
- amp_short_vectors/Concurrency::graphics::int_2::set_xy
- amp_short_vectors/Concurrency::graphics::int_2::operator+=
- amp_short_vectors/Concurrency::graphics::int_2::operator--
ms.assetid: 258b02e9-f1ee-46c2-8edd-dc9f69184846
ms.openlocfilehash: 7ee3f2726ce5c96a51a8246933c8d2d9d9eacc38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330043"
---
# <a name="int_2-class"></a>int_2 类

表示两个整数的短矢量。

## <a name="syntax"></a>语法

```cpp
class int_2;
```

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`value_type`||

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[int_2 构造函数](#ctor)|已重载。 默认构造函数，用0初始化所有元素。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|int_2：： get_x||
|int_2：： get_xy||
|int_2：： get_y||
|int_2：： get_yx||
|int_2：： ref_g||
|int_2：： ref_r||
|int_2：： ref_x||
|int_2：： ref_y||
|int_2：： set_x||
|int_2：： set_xy||
|int_2：： set_y||
|int_2：： set_yx||

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|int_2：： operator-||
|int_2：： operator--||
|int_2：： operator% =||
|int_2：： operator&=||
|int_2：： operator * =||
|int_2：： operator/=||
|int_2：： operator ^ =||
|int_2：： operator&#124;=||
|int_2：： operator ~||
|int_2：： operator + +||
|int_2：： operator + =||
|int_2：： operator<\<=||
|int_2：： operator =||
|int_2：： operator-=||
|int_2：： operator>>=||

### <a name="public-constants"></a>公共常量

|名称|描述|
|----------|-----------------|
|[大小常量](#int_2__size)||

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|int_2：： g||
|int_2：： gr||
|int_2：： r||
|int_2：： rg||
|int_2：： x||
|int_2：： xy||
|int_2：： y||
|int_2：： yx||

## <a name="inheritance-hierarchy"></a>继承层次结构

`int_2`

## <a name="requirements"></a>要求

**标头：** amp_short_vectors。h

**命名空间：** Concurrency：： graphics

## <a name="int_2"></a><a name="ctor"></a> int_2

默认构造函数，用0初始化所有元素。

```cpp
int_2() restrict(amp,
    cpu);

int_2(
    int _V0,
    int _V1) restrict(amp,
    cpu);

int_2(
    int _V) restrict(amp,
    cpu);

int_2(
    const int_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const uint_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const float_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
    const norm_2& _Other) restrict(amp,
    cpu);

explicit inline int_2(
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

## <a name="size"></a><a name="int_2__size"></a> 规格

```cpp
static const int size = 2;
```

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)

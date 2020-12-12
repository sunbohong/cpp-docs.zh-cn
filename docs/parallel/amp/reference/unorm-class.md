---
description: 了解详细信息： unorm 类
title: unorm 类
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: 947660d046ea41025e70aa4e6521e3c8f34c0a94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314517"
---
# <a name="unorm-class"></a>unorm 类

表示 unorm 的数字。 每个元素都是 [0.0 f，1.0 f] 范围内的一个浮点数。

## <a name="syntax"></a>语法

```cpp
class unorm;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[unorm 构造函数](#ctor)|已重载。 默认构造函数。 初始化为 0.0f。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|unorm：： operator--||
|unorm：： operator float|转换运算符。 将 unorm 数字转换为浮点值。|
|unorm：： operator * =||
|unorm：： operator/=||
|unorm：： operator + +||
|unorm：： operator + =||
|unorm：： operator =||
|unorm：： operator-=||

## <a name="inheritance-hierarchy"></a>继承层次结构

`unorm`

## <a name="requirements"></a>要求

**标头：** amp_short_vectors。h

**命名空间：** Concurrency：： graphics

## <a name="unorm"></a><a name="ctor"></a> unorm

默认构造函数。 初始化为 0.0f。

```cpp
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>parameters

*_V*<br/>
用来初始化的值。

*_Other*<br/>
用于初始化的标准对象。

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)

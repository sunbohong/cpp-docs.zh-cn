---
description: 了解详细信息：标准类
title: norm 类
ms.date: 11/04/2016
f1_keywords:
- AMP_SHORT_VECTORS/norm
- AMP_SHORT_VECTORS/Concurrency::graphics::norm Constructor
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
ms.openlocfilehash: 29e376e5e42212c87ae244c7a606a38d6a07ddf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327647"
---
# <a name="norm-class"></a>norm 类

表示一个标准数字。 每个元素都是 [-1.0 f，1.0 f] 范围内的一个浮点数。

## <a name="syntax"></a>语法

```cpp
class norm;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[标准构造函数](#ctor)|已重载。 默认构造函数。 初始化为 0.0f。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|标准：： operator-||
|标准：： operator--||
|模：： operator float|转换运算符。 将标准数字转换为浮点值。|
|标准：： operator * =||
|标准：： operator/=||
|标准：： operator + +||
|标准：： operator + =||
|模：： operator =||
|标准：： operator-=||

## <a name="inheritance-hierarchy"></a>继承层次结构

`norm`

## <a name="requirements"></a>要求

**标头：** amp_short_vectors。h

**命名空间：** Concurrency：： graphics

## <a name="norm"></a><a name="ctor"></a> 做法

默认构造函数。 初始化为 0.0f。

```cpp
norm(
    void) restrict(amp,
    cpu);

explicit norm(
    float _V) restrict(amp,
    cpu);

explicit norm(
    unsigned int _V) restrict(amp,
    cpu);

explicit norm(
    int _V) restrict(amp,
    cpu);

explicit norm(
    double _V) restrict(amp,
    cpu);

norm(
    const norm& _Other) restrict(amp,
    cpu);

norm(
    const unorm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>parameters

*_V*<br/>
用来初始化的值。

*_Other*<br/>
用于初始化的对象。

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)

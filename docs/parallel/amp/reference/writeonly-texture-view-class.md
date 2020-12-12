---
description: 了解详细信息： writeonly_texture_view 类
title: writeonly_texture_view 类
ms.date: 11/04/2016
f1_keywords:
- writeonly_texture_view
- AMP_GRAPHICS/writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view
- AMP_GRAPHICS/Concurrency::graphics::writeonly_texture_view::set
- AMP_GRAPHICS/Concurrency::graphics::rank Constant
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
ms.openlocfilehash: 17e9ed49c5fb3c976343d8c3ad8690d7f41b166d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314511"
---
# <a name="writeonly_texture_view-class"></a>writeonly_texture_view 类

提供对纹理的 writeonly 访问。

## <a name="syntax"></a>语法

```cpp
template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view;

template <
    typename value_type,
    int _Rank
>
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;
```

### <a name="parameters"></a>parameters

*value_type*<br/>
纹理中元素的类型。

*_Rank*<br/>
纹理的排名。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`scalar_type`||
|`value_type`|纹理中元素的类型。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[writeonly_texture_view 构造函数](#ctor)|初始化 `writeonly_texture_view` 类的新实例。|
|[~ writeonly_texture_view 析构函数](#ctor)|销毁 `writeonly_texture_view` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[set](#set)|设置指定索引处的元素的值。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[operator =](#operator_eq)|将指定的 `writeonly_texture_view` 对象复制到此对象。|

### <a name="public-constants"></a>公共常量

|名称|描述|
|----------|-----------------|
|[rank 常量](#rank)|获取对象的秩 `writeonly_texture_view` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`_Texture_base`

`writeonly_texture_view`

## <a name="requirements"></a>要求

**标头：** amp_graphics。h

**命名空间：** Concurrency：： graphics

## <a name="writeonly_texture_view"></a><a name="dtor"></a> ~ writeonly_texture_view

销毁 `writeonly_texture_view` 对象。

```cpp
~writeonly_texture_view() restrict(amp,cpu);
```

## <a name="operator"></a><a name="operator_eq"></a> operator =

将指定的 `writeonly_texture_view` 对象复制到此对象。

```cpp
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>parameters

*_Other*<br/>
`writeonly_texture_view` 要从中进行复制的对象。

### <a name="return-value"></a>返回值

对此对象的引用 `writeonly_texture_view` 。

## <a name="rank"></a><a name="rank"></a> 级别

获取对象的秩 `writeonly_texture_view` 。

```cpp
static const int rank = _Rank;
```

## <a name="set"></a><a name="set"></a> 字符集

设置指定索引处的元素的值。

```cpp
void set(
    const index<_Rank>& _Index,
    const value_type& value) const restrict(amp);
```

### <a name="parameters"></a>parameters

*_Index*<br/>
元素的索引。

*value*<br/>
该元素的新值。

## <a name="writeonly_texture_view"></a><a name="ctor"></a> writeonly_texture_view

初始化 `writeonly_texture_view` 类的新实例。

```cpp
writeonly_texture_view(
    texture<value_type,
    _Rank>& _Src) restrict(amp);

writeonly_texture_view(
    const writeonly_texture_view<value_type,
    _Rank>& _Src) restrict(amp,cpu);
```

### <a name="parameters"></a>parameters

*_Rank*<br/>
纹理的排名。

*value_type*<br/>
纹理中元素的类型。

*_Src*<br/>
用于创建 `writeonly_texture_view` 的纹理。

## <a name="see-also"></a>请参阅

[Concurrency::graphics 命名空间](concurrency-graphics-namespace.md)

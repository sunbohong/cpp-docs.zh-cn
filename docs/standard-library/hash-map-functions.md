---
title: '&lt;hash_map&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: a29254d32954556ad3a2fbedb89fb3556533ff1f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841189"
---
# <a name="lthash_mapgt-functions"></a>&lt;hash_map&gt; 函数

[购](#swap)\
[swap (hash_map)](#swap_hash_map)

## <a name="swap-hash_map"></a><a name="swap_hash_map"></a> 交换 (hash_map) 

> [!NOTE]
> 此 API 已废弃不用。 替代项为 [unordered_map 类](../standard-library/unordered-map-class.md)。

交换两个 hash_map 的元素。

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>参数

*然后*\
其元素要与 *左侧*地图的元素进行交换的 hash_map。

*左中*\
其元素要与地图 *权限*的元素进行交换的 hash_map。

### <a name="remarks"></a>注解

模板函数是容器类 hash_map 上专用化的算法，用以执行成员函数 `left.`[swap](../standard-library/basic-ios-class.md#swap)*(right*)。 这是由编译器进行的函数模板偏序实例。 模板函数以此种方式重载时，模板与函数调用的匹配并不唯一，随后编译器会选择此模板函数的最专用化版本。 算法标头文件中的模板函数的通用版本 ** \<class T> (T&，t&) **，它是按赋值方式运行的，并且速度缓慢。 每个容器中的专用化版本速度快很多，因为专用化版本可适用于容器类的内部表示形式。

## <a name="swap"></a><a name="swap"></a> 购

> [!NOTE]
> 此 API 已废弃不用。 替代项为 [unordered_multimap 类](../standard-library/unordered-multimap-class.md)。

交换两个 hash_multimap 的元素。

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>参数

*然后*\
其元素要与 *左侧*地图的元素进行交换的 hash_multimap。

*左中*\
其元素要与地图 *权限*的元素进行交换的 hash_multimap。

### <a name="remarks"></a>注解

模板函数是容器类 hash_multimap 上专用化的算法，用以执行成员函数 `left.`[swap](../standard-library/hash-multimap-class.md#swap)*(right*`)`。 这是由编译器进行的函数模板偏序实例。 模板函数以此种方式重载时，模板与函数调用的匹配并不唯一，随后编译器会选择此模板函数的最专用化版本。 算法标头文件中的模板函数的通用版本 ** \<class T> (T&，t&) **，它是按赋值方式运行的，并且速度缓慢。 每个容器中的专用化版本速度快很多，因为专用化版本可适用于容器类的内部表示形式。

## <a name="see-also"></a>另请参阅

[<hash_map>](../standard-library/hash-map.md)

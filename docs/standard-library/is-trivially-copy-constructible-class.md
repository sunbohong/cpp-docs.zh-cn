---
description: 了解详细信息： is_trivially_copy_constructible 类
title: is_trivially_copy_constructible 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copy_constructible
helpviewer_keywords:
- is_trivially_copy_constructible
ms.assetid: 4274cef5-afdd-4f2d-bc83-7562e7944ddf
ms.openlocfilehash: c247e81f52ad98e546a840bb38938fe15bc9b302
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118519"
---
# <a name="is_trivially_copy_constructible-class"></a>is_trivially_copy_constructible 类

测试类型是否包含普通复制构造函数。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct is_trivially_copy_constructible;
```

### <a name="parameters"></a>parameters

*关心*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *T* 是具有普通复制构造函数的类，则类型谓词的实例为 true; 否则为 false。

如果类 *t* 的复制构造函数被隐式声明、 *类 t 没有* 虚拟函数或虚拟基，则类 t 的所有直接 *基都具有* 普通复制构造函数，类类型的所有非静态数据成员的类具有普通复制构造函数，并且类的类型数组的所有非静态数据成员的类具有普通复制构造函数。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)

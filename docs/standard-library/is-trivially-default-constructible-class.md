---
description: 了解详细信息： is_trivially_default_constructible 类
title: is_trivially_default_constructible 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_default_constructible
helpviewer_keywords:
- is_trivially_default_constructible
ms.assetid: 653ecd73-909f-4dd8-b95a-d1164d1c2da4
ms.openlocfilehash: 3686dab86b8bf04fe7629b53651988d7ccef161e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118402"
---
# <a name="is_trivially_default_constructible-class"></a>is_trivially_default_constructible 类

测试类型是否具有普通默认构造函数。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
struct is_trivially_default_constructible;
```

### <a name="parameters"></a>parameters

*Ty*\
要查询的类型。

## <a name="remarks"></a>备注

如果类型 *Ty* 是具有普通构造函数的类，则类型谓词的实例为 true; 否则为 false。

类 *Ty* 的默认构造函数在以下情况下是普通构造函数：

- 它是一个隐式声明的默认构造函数

- 类 *Ty* 没有虚函数

- 类 *Ty* 没有虚拟基

- 类 *Ty* 的所有直接基都具有普通构造函数

- 类类型的所有非静态数据成员的类具有普通构造函数

- 类的类型数组的所有非静态数据成员的类具有普通构造函数

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)

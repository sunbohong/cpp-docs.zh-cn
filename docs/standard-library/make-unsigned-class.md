---
description: 了解详细信息： make_unsigned 类
title: make_unsigned 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_unsigned
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
ms.openlocfilehash: 3767a9971c17667b5d2fe545e524f563df2a7f42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277513"
---
# <a name="make_unsigned-class"></a>make_unsigned 类

设置类型或大小大于或等于类型的无符号的最小类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>parameters

*关心*\
要修改的类型。

## <a name="remarks"></a>备注

如果保留为 true，则类型修饰符的实例保留 *修改后的* 类型 `is_unsigned<T>` 。 否则，它就是适用于 `sizeof (T) <= sizeof (ST)` 的最小的带符号类型 `ST`。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)

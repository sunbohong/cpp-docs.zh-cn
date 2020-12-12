---
description: 了解详细信息： make_signed 类
title: make_signed 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::make_signed
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
ms.openlocfilehash: 2f11fe3223e6193613772d2c4abbf0182215a17d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277552"
---
# <a name="make_signed-class"></a>make_signed 类

设置类型或大小大于或等于类型的有符号的最小类型。

## <a name="syntax"></a>语法

```cpp
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```

### <a name="parameters"></a>parameters

*关心*\
要修改的类型。

## <a name="remarks"></a>备注

如果保留为 true，则类型修饰符的实例保留 *修改后的* 类型 `is_signed<T>` 。 否则，它就是适用于 `sizeof (T) <= sizeof (UT)` 的最小的无符号类型 `UT`。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)

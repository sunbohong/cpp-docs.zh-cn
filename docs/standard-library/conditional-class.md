---
description: 了解详细信息：条件类
title: conditional 类
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::conditional
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
ms.openlocfilehash: f8edbd7341598957ecbe8b0822a832973f0e06a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324966"
---
# <a name="conditional-class"></a>conditional 类

根据指定的条件，从两种类型之中选择其中一种。

## <a name="syntax"></a>语法

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>parameters

*B*\
用于确定所选类型的值。

*T1*\
当 B 为 true 时的类型结果。

\
当 B 为 false 时的类型结果。

## <a name="remarks"></a>备注

当 b 的计算结果为时，模板成员 typedef 的 `conditional<B, T1, T2>::type` 计算结果为 *T1*  **`true`** ，当 *b* 计算为时，其计算结果为 *T2* **`false`** 。

## <a name="requirements"></a>要求

**标头：**\<type_traits>

**命名空间:** std

## <a name="see-also"></a>请参阅

[<type_traits>](../standard-library/type-traits.md)

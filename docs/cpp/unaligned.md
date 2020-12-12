---
description: 了解详细信息： __unaligned
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: f5afd0c6c1a506cbaeb03d497e64eac743ecc4df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145751"
---
# <a name="__unaligned"></a>__unaligned

**特定于 Microsoft 的**。 当你使用修饰符声明指针时 **`__unaligned`** ，编译器将假定指针寻址未对齐的数据。 因此，生成了平台相应的代码来处理通过指针进行的未对齐读写操作。

## <a name="remarks"></a>备注

此修饰符描述由指针寻址的数据的对齐方式;指针本身被假定为对齐。

关键字的必要性 **`__unaligned`** 因平台和环境而异。 如果未能适当地标记数据，可能会导致问题，范围从性能损失到硬件故障。 **`__unaligned`** 修饰符对于 x86 平台无效。

为了与早期版本兼容， **`_unaligned`** 将作为同义词， **`__unaligned`** 除非指定了编译器选项 " [ `/Za` \( 禁用语言扩展")](../build/reference/za-ze-disable-language-extensions.md) 。

有关对齐的详细信息，请参阅：

- [`align`](../cpp/align-cpp.md)

- [`alignof` 操作员](../cpp/alignof-operator.md)

- [`pack`](../preprocessor/pack.md)

- [`/Zp` (结构成员对齐) ](../build/reference/zp-struct-member-alignment.md)

- [结构对齐示例](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)

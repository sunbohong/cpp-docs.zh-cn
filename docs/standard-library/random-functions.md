---
description: 了解详细信息： &lt; 随机 &gt; 函数
title: '&lt;random&gt; 函数'
ms.date: 09/04/2019
f1_keywords:
- random/std::generate_canonical
ms.assetid: 2ac9ec59-619b-4b85-a425-f729277c1bc8
helpviewer_keywords:
- std::generate_canonical
ms.openlocfilehash: 39670fcd9b200a6bd56656bbfa07391fdd0d96be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163335"
---
# <a name="ltrandomgt-functions"></a>&lt;random&gt; 函数

## <a name="generate_canonical"></a><a name="generate_canonical"></a> generate_canonical

从随机序列返回浮点值。

```cpp
template <class RealType, size_t Bits, class Generator>
RealType generate_canonical(Generator& Gen);
```

### <a name="parameters"></a>parameters

*RealType*\
浮点整型。 有关可能的类型，请参阅 [\<random>](../standard-library/random.md) 。

*带宽*\
要使用的随机性位数。

*生成器*\
随机数生成器类。

*常规*\
对类型 *生成器* 的随机数生成器的实例的引用。

### <a name="remarks"></a>备注

模板函数重复调用 `operator()` 了 *Gen* ，并将返回的值打包为 RealType 类型的浮点值， `x` 直到它在中收集了指定数目的尾数位 `x` 。 指定的数字是 *位数* 较小的 (，其中必须为非零) ，以及 *RealType* 中的尾数位的完整数目。 第一个调用提供最低序位。 该函数返回 `x`。

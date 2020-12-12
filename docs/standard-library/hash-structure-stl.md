---
description: '了解详细信息： c + + 标准库 (的哈希结构) '
title: hash 结构（C++ 标准库）| Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- thread/std::hash
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
ms.openlocfilehash: 095566b6855c837c3ee6049a5cbedfbb087420bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324063"
---
# <a name="hash-structure-c-standard-library"></a>hash 结构（C++ 标准库）

定义一个成员函数，该函数返回一个由 `Val` 唯一决定的值。 此成员函数定义一个 [hash](../standard-library/hash-class.md) 函数，此函数适用于将 `thread::id` 类型的值映射到索引值的分布。

## <a name="syntax"></a>语法

```cpp
template <>
struct hash<thread::id> :
    public unary_function<thread::id, size_t>
{
    size_t operator()(thread::id Val) const;

};
```

## <a name="requirements"></a>要求

**标头：**\<thread>

**命名空间:** std

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[\<thread>](../standard-library/thread.md)\
[unary_function 结构](../standard-library/unary-function-struct.md)

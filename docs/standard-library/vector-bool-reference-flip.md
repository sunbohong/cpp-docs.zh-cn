---
description: 了解详细信息： vector &lt; bool &gt; ：： reference：： flip
title: vector&lt;bool&gt;::reference::flip
ms.date: 11/04/2016
f1_keywords:
- vector/std::vector<bool>::reference::flip
helpviewer_keywords:
- reference::flip method
ms.assetid: ef940365-cbe4-4a87-a3e2-1f3cfa357e29
ms.openlocfilehash: fc07fada718e440d6e2ae76c75e7e5b24c6644d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280412"
---
# <a name="vectorltboolgtreferenceflip"></a>vector&lt;bool&gt;::reference::flip

反转所引用[矢量 \<bool> ](../standard-library/vector-bool-class.md)元素的布尔值。

## <a name="syntax"></a>语法

```cpp
void flip();
```

## <a name="example"></a>示例

```cpp
// vector_bool_ref_flip.cpp
// compile with: /EHsc /W4
#include <vector>
#include <iostream>

int main()
{
    using namespace std;
    cout << boolalpha;

    vector<bool> vb = { true, false, false, true, true };

    cout << "The vector is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;

    vector<bool>::reference vbref = vb.front();
    vbref.flip();

    cout << "The vector with first element flipped is: " << endl << "    ";
    for (const auto& b : vb) {
        cout << b << " ";
    }
    cout << endl;
}
```

## <a name="output"></a>输出

```Output
The vector is:
    true false false true true
The vector with first element flipped is:
    false false false true true
```

## <a name="requirements"></a>要求

**标头：**\<vector>

**命名空间:** std

## <a name="see-also"></a>请参阅

[vector \<bool> ：： Reference 类](../standard-library/vector-bool-reference-class.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)

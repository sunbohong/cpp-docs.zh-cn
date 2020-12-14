---
description: 了解详细信息： &lt; typeindex>&gt;
title: '&lt;typeindex&gt;'
ms.date: 11/04/2016
f1_keywords:
- <typeindex>
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
ms.openlocfilehash: 0f5aee958aee01bcccc87145087001f093ab6749
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226436"
---
# <a name="lttypeindexgt"></a>&lt;typeindex&gt;

包含标准标头 \<typeindex> 以定义支持类 [type_info](../cpp/type-info-class.md)的对象索引的类和函数。

## <a name="syntax"></a>语法

```cpp
#include <typeindex>
```

## <a name="remarks"></a>备注

[hash 结构](../standard-library/hash-structure.md)可定义适合将 [type_index](../standard-library/type-index-class.md) 类型的值映射到索引值的分布的 `hash function`。

`type_index` 类包装指向 `type_info` 对象的指针，以便辅助编写索引。

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)

---
description: 了解详细信息： &lt; 内存 &gt; 枚举
title: '&lt;memory&gt; 枚举'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: da9bb22a6095f74b94e1745210fa55061ecf3c71
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97149092"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 枚举

## <a name="pointer_safety-enumeration"></a><a name="pointer_safety"></a> pointer_safety 枚举

由 `get_pointer_safety` 返回的可能值的枚举。

```cpp
class pointer_safety {
   relaxed,
   preferred,
   strict
};
```

### <a name="remarks"></a>备注

作用域 **`enum`** 定义可由返回的值 `get_pointer_safety()` ：

`relaxed` -- 未安全派生的指针（显然是指向声明或分配对象的指针）将视为与安全派生的指针相同。

`preferred` -- 与以前一样，但不应取消引用未安全派生的指针。

`strict` -- 未安全派生的指针可能视为与安全派生的指针不同。

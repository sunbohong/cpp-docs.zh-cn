---
description: 了解详细信息： &lt; cassert&gt;
title: '&lt;cassert&gt;'
ms.date: 11/04/2016
f1_keywords:
- <cassert>
helpviewer_keywords:
- cassert header
ms.assetid: 6ead15a3-ac45-4075-be8e-350bca995c26
ms.openlocfilehash: e2b515fe492e6847c4d0cc5841dc43a2d879dd99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325351"
---
# <a name="ltcassertgt"></a>&lt;cassert&gt;

包括 C 标准库标头 \<assert.h> 并将关联名称添加到 `std` 命名空间。 包括此标头可确保在命名空间中声明使用 C 标准库标头中的外部链接声明的名称 `std` 。

> [!NOTE]
> \<assert.h> 不定义 **`static_assert`** 宏。

## <a name="syntax"></a>语法

```cpp
#include <cassert>
```

## <a name="macros"></a>宏

```cpp
#define assert(E)
```

### <a name="remarks"></a>备注

`assert(E)` 仅为常量，如果定义了 NDEBUG，定义 `assert` 了最后定义或重新定义的，或者 *E* 转换为 bool，则计算结果为 **`true`** 。

## <a name="see-also"></a>请参阅

[assert 宏、_assert、_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)\
[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[C + + 标准库概述](../standard-library/cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)

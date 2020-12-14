---
description: 了解详细信息： _HAS_ITERATOR_DEBUGGING
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: ee1765739624fe7c6fccd41ff84f455d5f90cc42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231987"
---
# <a name="_has_iterator_debugging"></a>_HAS_ITERATOR_DEBUGGING

由 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) 取代，该宏定义调试版本中是否启用了迭代器调试功能。 默认情况下，迭代器调试在调试版本中处于启用状态，在零售版本中处于禁用状态。 有关详细信息，请参阅[调试迭代器支持](../standard-library/debug-iterator-support.md)。

> [!IMPORTANT]
> 不推荐使用 _HAS_ITERATOR_DEBUGGING 宏的直接用法。 请改用 _ITERATOR_DEBUG_LEVEL 来控制迭代器调试设置。 有关详细信息，请参阅 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)。

## <a name="remarks"></a>备注

若要在调试版本中启用迭代器调试，请将 _ITERATOR_DEBUG_LEVEL 设置为2。 这等效于 "1" 或 "已启用" _HAS_ITERATOR_DEBUGGING 设置：

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL 不能设置为 2 (并且在零售版本中 _HAS_ITERATOR_DEBUGGING 不能设置为 1) 。

若要在调试版本中禁用调试迭代器，请将 _ITERATOR_DEBUG_LEVEL 设置为0或1。 这等效于设置为0或已禁用的 _HAS_ITERATOR_DEBUGGING：

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>请参阅

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[调试迭代器支持](../standard-library/debug-iterator-support.md)\
[检查迭代器](../standard-library/checked-iterators.md)\
[安全库： c + + 标准库](../standard-library/safe-libraries-cpp-standard-library.md)

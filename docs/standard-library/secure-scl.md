---
description: 了解详细信息： _SECURE_SCL
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1a0e32ada449709a60eb601138ce0bb8b7ae9123
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197096"
---
# <a name="_secure_scl"></a>_SECURE_SCL

被 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) 所取代，此宏可定义是否已启用[经过检查的迭代器](../standard-library/checked-iterators.md)。 默认情况下，经过检查的迭代器在调试版本中处于启用状态，在零售版本中处于禁用状态。

> [!IMPORTANT]
> 不推荐使用 _SECURE_SCL 宏的直接用法。 请改用 _ITERATOR_DEBUG_LEVEL 来控制检查的迭代器设置。 有关详细信息，请参阅 [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)。

## <a name="remarks"></a>备注

启用经过检查的迭代器时，使用不安全的迭代器会导致运行时错误并终止程序。 若要启用选中的迭代器，请将 _ITERATOR_DEBUG_LEVEL 设置为1或2。 这等效于 "1" 或 "已启用" _SECURE_SCL 设置：

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

若要禁用选中的迭代器，请将 _ITERATOR_DEBUG_LEVEL 设置为0。 这等效于设置为0或已禁用的 _SECURE_SCL：

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

有关如何禁用经过检查的迭代器的警告信息，请参阅 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)。

## <a name="see-also"></a>请参阅

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[检查迭代器](../standard-library/checked-iterators.md)\
[调试迭代器支持](../standard-library/debug-iterator-support.md)\
[安全库： c + + 标准库](../standard-library/safe-libraries-cpp-standard-library.md)

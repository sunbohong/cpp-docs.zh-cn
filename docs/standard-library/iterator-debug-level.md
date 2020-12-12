---
description: 了解详细信息： _ITERATOR_DEBUG_LEVEL
title: _ITERATOR_DEBUG_LEVEL
ms.date: 11/04/2016
f1_keywords:
- _ITERATOR_DEBUG_LEVEL
helpviewer_keywords:
- _ITERATOR_DEBUG_LEVEL
ms.assetid: 718549cd-a9a9-4ab3-867b-aac00b321e67
ms.openlocfilehash: 769b7f3a8eecd3c994ee82b67385f080f0945f33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306633"
---
# <a name="_iterator_debug_level"></a>_ITERATOR_DEBUG_LEVEL

_ITERATOR_DEBUG_LEVEL 宏控制是否启用[检查迭代](../standard-library/checked-iterators.md)[器和调试迭代器支持](../standard-library/debug-iterator-support.md)。 此宏取代旧的 _SECURE_SCL 和 _HAS_ITERATOR_DEBUGGING 宏的功能并将其结合起来。

## <a name="macro-values"></a>宏值

下表汇总了 _ITERATOR_DEBUG_LEVEL 宏的可能值。

|编译模式|宏值|描述|
|----------------------|----------------|-----------------|
|**调试**|||
||0|禁用经过检查的迭代器，并禁用迭代器调试。|
||1|启用经过检查的迭代器，禁用迭代器调试。|
||2（默认值）|启用迭代器调试；经过检查的迭代器不相关。|
|**版本**|||
||0（默认值）|禁用经过检查的迭代器。|
||1|启用经过检查的迭代器；迭代器调试不相关。|

在发布模式下，如果将 _ITERATOR_DEBUG_LEVEL 指定为2，则编译器将生成错误。

## <a name="remarks"></a>备注

_ITERATOR_DEBUG_LEVEL 宏控制是否启用 [检查迭代](../standard-library/checked-iterators.md) 器，以及调试模式下是否启用了 [调试迭代器支持](../standard-library/debug-iterator-support.md) 。 如果 _ITERATOR_DEBUG_LEVEL 定义为1或2，则检查迭代器可确保容器的边界不会被覆盖。 如果 _ITERATOR_DEBUG_LEVEL 为0，则不检查迭代器。 如果 _ITERATOR_DEBUG_LEVEL 定义为1，则任何不安全迭代器都将导致运行时错误，并且程序将终止。 如果 _ITERATOR_DEBUG_LEVEL 定义为2，则不安全迭代器使用会导致断言和运行时错误对话框，使你可以中断到调试器。

由于 _ITERATOR_DEBUG_LEVEL 宏支持与 _SECURE_SCL 和 _HAS_ITERATOR_DEBUGGING 宏类似的功能，因此您可能不确定在特定情况下使用哪个宏和宏值。 为了避免混淆，我们建议您仅使用 _ITERATOR_DEBUG_LEVEL 宏。 下表描述了在现有代码中用于 _SECURE_SCL 和 _HAS_ITERATOR_DEBUGGING 的各种值的等效 _ITERATOR_DEBUG_LEVEL 宏值。

|**_ITERATOR_DEBUG_LEVEL** |**_SECURE_SCL** |**_HAS_ITERATOR_DEBUGGING**|
|---|---|---|
|0（发布默认值）|0（禁用）|0（禁用）|
|1|1（启用）|0（禁用）|
|2（调试默认值）|（不相关）|1（在调试模式中启用）|

有关如何禁用经过检查的迭代器的警告信息，请参阅 [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md)。

### <a name="example"></a>示例

若要为 _ITERATOR_DEBUG_LEVEL 宏指定值，请使用 [/d](../build/reference/d-preprocessor-definitions.md) 编译器选项在命令行上对其进行定义，或在将 `#define` c + + 标准库标头包含在源文件中之前使用。 例如，在命令行中，若要在调试模式下编译 *sample* ，并使用调试迭代器支持，可以指定 _ITERATOR_DEBUG_LEVEL 宏定义：

`cl /EHsc /Zi /MDd /D_ITERATOR_DEBUG_LEVEL=1 sample.cpp`

在源文件中，请在定义迭代器的任何标准库标头前指定宏。

```cpp
// sample.cpp

#define _ITERATOR_DEBUG_LEVEL 1

#include <vector>

// ...
```

## <a name="see-also"></a>请参阅

[检查迭代器](../standard-library/checked-iterators.md)\
[调试迭代器支持](../standard-library/debug-iterator-support.md)\
[安全库： c + + 标准库](../standard-library/safe-libraries-cpp-standard-library.md)

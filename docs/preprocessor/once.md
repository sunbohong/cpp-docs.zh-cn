---
description: 了解详细信息：一次 pragma
title: 曾经 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.once
- once_CPP
helpviewer_keywords:
- once pragma
- pragma, once
no-loc:
- pragma
ms.openlocfilehash: 3edb5f88202ee783e587b1f886eddddf427f6133
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713475"
---
# <a name="once-no-locpragma"></a>`once` pragma

指定在编译源代码文件时编译器仅包含头文件一次。

## <a name="syntax"></a>语法

> **`#pragma once`**

## <a name="remarks"></a>备注

使用 `#pragma once` 可以减少生成时间，因为编译器不会在翻译单元中的第一个文件之后打开并再次读取该文件 `#include` 。 这称为 " *多个包含优化*"。 它的作用类似于 *include guard* 方法，该方法使用预处理器宏定义来防止多次包含文件内容。 它还有助于防止违反 *单个定义规则*：要求所有模板、类型、函数和对象在代码中都不能有多个定义。

例如：

```cpp
// header.h
#pragma once
// Code placed here is included only once per translation unit
```

建议对新代码使用 `#pragma once` 指令，因为它不会用预处理器符号污染全局命名空间。 它需要更少的键入，它不会造成混乱，而且它不会导致 *符号冲突*。 当不同的标头文件使用与临界值相同的预处理器符号时，符号冲突就会导致错误。 它不是 c + + 标准的一部分，而是由多个常用编译器来实现移植。

在同一文件中同时使用 include 防护方法并没有优势 `#pragma once` 。 编译器可识别 include guard 方法，并以与指令相同的方式实现多重包含优化，前提是在 `#pragma once` 标准形式的方法之前或之后没有任何非注释代码或预处理器指令：

```cpp
// header.h
// Demonstration of the #include guard idiom.
// Note that the defined symbol can be arbitrary.
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_
#define HEADER_H_
// Code placed here is included only once per translation unit
#endif // HEADER_H_
```

如果必须将代码移植到未实现指令的编译器 `#pragma once` 、保持与现有代码的一致性或无法进行多重包含优化，则建议包含 guard。 如果文件系统别名或别名包含路径包含路径，则可能会在复杂的项目中出现此问题。

请注意不要使用 `#pragma once` 或在设计为多次包含的标头文件中包含防护用法，使用预处理器符号控制其效果。 有关此设计的示例，请参阅 \<assert.h> 标头文件。 还要小心管理包含路径，以避免创建到包含文件的多个路径，这会使其中包含保护和的多包含优化 `#pragma once` 。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

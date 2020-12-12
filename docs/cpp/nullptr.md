---
description: 了解详细信息： nullptr
title: nullptr
ms.date: 07/22/2020
f1_keywords:
- nullptr_cpp
helpviewer_keywords:
- nullptr keyword [C++]
ms.assetid: e9d80ea6-2506-4eb5-b47b-2349df085832
ms.openlocfilehash: 8d7eb3a578addc14b85c53c50ab81c6e5592d541
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146147"
---
# <a name="nullptr"></a>nullptr

**`nullptr`** 关键字指定类型的 null 指针常量 `std::nullptr_t` ，该常量可转换为任何原始指针类型。  尽管可以使用关键字 **`nullptr`** 而不包含任何标头，但如果代码使用类型 `std::nullptr_t` ，则必须通过包含标头来定义该类型 `<cstddef>` 。

> [!NOTE]
> 此 **`nullptr`** 关键字还在托管代码应用程序的 c + +/cli 中定义，并且不能与 ISO 标准 c + + 关键字互换。 如果你的代码可能是使用 [`/clr`](../build/reference/clr-common-language-runtime-compilation.md) 针对托管代码的编译器选项编译的，则 `__nullptr` 在你必须保证编译器使用本机 c + + 解释的任何代码行中使用。 有关详细信息，请参阅[ `nullptr` (c + +/Cli 和 c + +/cx) ](../extensions/nullptr-cpp-component-extensions.md)。

## <a name="remarks"></a>备注

避免使用 `NULL` 或零 (`0`) 为 null 指针常量; 在 **`nullptr`** 大多数情况下，不太容易受到滥用和工作。  例如，给定 `func(std::pair<const char *, double>)`，那么调用 `func(std::make_pair(NULL, 3.14))` 会导致编译器错误。  宏 `NULL` 展开为 `0` ，以便调用 `std::make_pair(0, 3.14)` 返回 `std::pair<int, double>` ，这在中不能转换为 `std::pair<const char *, double>` 参数类型 `func` 。  调用 `func(std::make_pair(nullptr, 3.14))` 将会成功编译，因为 `std::make_pair(nullptr, 3.14)` 返回 `std::pair<std::nullptr_t, double>`，此结果可转换为 `std::pair<const char *, double>`。

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)<br/>
[`nullptr` (c + +/CLI 和 c + +/CX) ](../extensions/nullptr-cpp-component-extensions.md)

---
title: 混合 C (结构化) 和 c + + 异常
description: 如何混合使用结构化异常处理和 c + + 异常以及一些潜在问题。
ms.date: 08/24/2020
helpviewer_keywords:
- exceptions [C++], mixed C and C++
- C++ exception handling, mixed-language
- structured exception handling [C++], mixed C and C++
- catch keyword [C++], mixed
- try-catch keyword [C++], mixed-language
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
ms.openlocfilehash: 98ce2335ff3b08b7a5d71e03305c481ba068e5e6
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898412"
---
# <a name="mixing-c-structured-and-c-exceptions"></a>混合 C (结构化) 和 c + + 异常

如果要编写可移植的代码，不建议在 c + + 程序中使用结构化异常处理 (SEH) 。 但是，有时您可能希望使用进行编译， [`/EHa`](../build/reference/eh-exception-handling-model.md) 并混合使用结构化异常和 c + + 源代码，并且需要一些功能来处理这两种异常。 由于结构化异常处理程序没有对象或类型化异常的概念，因此它无法处理 c + + 代码引发的异常。 但是，c + + **`catch`** 处理程序可以处理结构化异常。 C + + 异常处理语法 (**`try`** 、 **`throw`** 、 **`catch`**) 不被 c 编译器接受， (但是 **`__try`** **`__except`** **`__finally`** c + + 编译器支持) 。

[`_set_se_translator`](../c-runtime-library/reference/set-se-translator.md)有关如何处理结构化异常作为 c + + 异常的信息，请参阅。

如果混合使用结构化异常和 c + + 异常，请注意以下潜在问题：

- 不能在同一函数内混合 c + + 异常和结构化异常。

- **`__finally`** 始终执行 (块) 终止处理程序，即使在引发异常后在展开过程中也是如此。

- C + + 异常处理可以在使用编译器选项编译的所有模块中捕获和保留展开语义 [`/EH`](../build/reference/eh-exception-handling-model.md) ，这将启用展开语义。

- 在某些情况下，不会为所有对象调用析构函数。 例如，尝试通过未初始化的函数指针进行函数调用时，可能会出现结构化异常。 如果函数参数是在调用之前构造的对象，则不会在堆栈展开过程中调用这些对象的析构函数。

## <a name="next-steps"></a>后续步骤

- [`setjmp` `longjmp` 在 c + + 程序中使用或](../cpp/using-setjmp-longjmp.md)

  请参阅在 `setjmp` `longjmp` c + + 程序中使用和的详细信息。

- [处理 C++ 中的结构性异常](../cpp/exception-handling-differences.md)

  请参阅使用 c + + 处理结构化异常的方式的示例。

## <a name="see-also"></a>请参阅

[异常和错误处理的新式 c + + 最佳做法](../cpp/errors-and-exception-handling-modern-cpp.md)

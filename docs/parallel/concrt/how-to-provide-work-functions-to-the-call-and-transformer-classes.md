---
title: 如何：为 call 和 transformer 类提供工作函数
ms.date: 11/04/2016
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
ms.openlocfilehash: b629d0e0e11388e212c56b8e1f6bea290368c884
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414342"
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>如何：为 call 和 transformer 类提供工作函数

本主题演示了向 [concurrency：： call](../../parallel/concrt/reference/call-class.md) 和 [concurrency：：变压器](../../parallel/concrt/reference/transformer-class.md) 类提供工作函数的几种方法。

第一个示例演示如何将 lambda 表达式传递给 `call` 对象。 第二个示例演示如何将函数对象传递给 `call` 对象。 第三个示例演示如何将类方法绑定到 `call` 对象。

为了举例说明，本主题中的每个示例都使用 `call` 类。 有关使用类的示例 `transformer` ，请参阅 [如何：在数据管道中使用转换器](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)。

## <a name="example-call-class"></a>示例： call 类

下面的示例演示了如何使用 `call` 类。 此示例将 lambda 函数传递给 `call` 构造函数。

[!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]

本示例生成以下输出。

```Output
13 squared is 169.
```

## <a name="example-call-class-with-function-object"></a>示例：用函数对象调用类

下面的示例与上一个示例类似，不同之处在于它将 `call` 类与函数对象一起使用 (函子) 。

[!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]

## <a name="example-functions-to-bind-call-object"></a>示例：用于绑定调用对象的函数

下面的示例与上一个示例类似，只不过它使用 [std：： bind1st](../../standard-library/functional-functions.md#bind1st) 和 [std：： mem_fun](../../standard-library/functional-functions.md#mem_fun) 函数将 `call` 对象绑定到类方法。

如果必须将 `call` 或 `transformer` 对象绑定到特定类方法而不是函数调用运算符，请使用此方法 `operator()` 。

[!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]

你还可以将函数的结果分配 `bind1st` 给 [std：： function](../../standard-library/function-class.md) 对象或使用 **`auto`** 关键字，如下面的示例中所示。

[!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]

## <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `call.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

> **cl.exe/EHsc 调用 .cpp**

## <a name="see-also"></a>另请参阅

[异步代理库](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[异步消息块](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[如何：在数据管道中使用转换器](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)<br/>
[call 类](../../parallel/concrt/reference/call-class.md)<br/>
[变压器类](../../parallel/concrt/reference/transformer-class.md)

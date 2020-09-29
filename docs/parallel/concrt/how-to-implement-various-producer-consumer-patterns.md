---
title: 如何：实现各种制造者-使用者模式
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 70813adf6715a2bcaf4af7370ce43d99c44263bd
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413770"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>如何：实现各种制造者-使用者模式

本主题介绍如何在应用程序中实现制造者-使用者模式。 在此模式下，制造者向消息块发送消息，使用者从该块读取消息。

本主题演示了两种方案。 在第一个方案中，使用者必须收到制造者发送的每条消息。 在第二种情况下，使用者会定期轮询数据，因此无需接收每条消息。

本主题中的两个示例都使用代理、消息块和消息传递函数将消息从生成者传输到使用者。 制造者代理使用 [concurrency：： send](reference/concurrency-namespace-functions.md#send) 函数将消息写入 [Concurrency：： ITarget](../../parallel/concrt/reference/itarget-class.md) 对象。 使用者代理使用 [concurrency：： receive](reference/concurrency-namespace-functions.md#receive) 函数从 [Concurrency：： ISource](../../parallel/concrt/reference/isource-class.md) 对象读取消息。 这两个代理都包含一个 sentinel 值来协调处理结束。

有关异步代理的详细信息，请参阅 [异步代理](../../parallel/concrt/asynchronous-agents.md)。 有关消息块和消息传递函数的详细信息，请参阅 [异步消息块](../../parallel/concrt/asynchronous-message-blocks.md) 和 [消息传递函数](../../parallel/concrt/message-passing-functions.md)。

## <a name="example-send-series-of-numbers-to-consumer-agent"></a>示例：将一系列号码发送到使用者代理

在此示例中，制造者代理将一系列号码发送到使用者代理。 使用者接收其中每个数字并计算其平均值。 应用程序将平均值写入控制台。

此示例使用 [concurrency：： unbounded_buffer](reference/unbounded-buffer-class.md) 对象，使生成者能够对消息进行排队。 `unbounded_buffer`类实现 `ITarget` 和， `ISource` 以便制造者和使用者可以与共享缓冲区之间收发消息。 `send`和 `receive` 函数协调将数据从制造者传播到使用者的任务。

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

本示例生成以下输出。

```Output
The average is 50.
```

## <a name="example-send-series-of-stock-quotes-to-consumer-agent"></a>示例：将股票行情序列发送到使用者代理

在此示例中，制造者代理将一系列股票行情发送到使用者代理。 使用者代理会定期读取当前报价，并将其打印到控制台。

此示例与上一个示例类似，不同之处在于它使用 [concurrency：： overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) 对象来使生成者与使用者共享一条消息。 如前面的示例中所示， `overwrite_buffer` 类实现 `ITarget` `ISource` 了，因此，制造者和使用者可以操作共享消息缓冲区。

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

此示例将生成以下示例输出。

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

与对象不同 `unbounded_buffer` ，函数不 `receive` 会从对象中移除消息 `overwrite_buffer` 。 如果使用者在生成方覆盖该消息之前多次读取消息缓冲区，接收方将每次获取相同的消息。

## <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `producer-consumer.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

**cl.exe/EHsc producer-consumer**

## <a name="see-also"></a>另请参阅

[异步代理库](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[异步代理](../../parallel/concrt/asynchronous-agents.md)<br/>
[异步消息块](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[消息传递函数](../../parallel/concrt/message-passing-functions.md)

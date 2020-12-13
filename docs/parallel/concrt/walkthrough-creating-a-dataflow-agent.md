---
description: 了解详细信息：演练：创建数据流代理
title: 演练：创建数据流代理
ms.date: 04/25/2019
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
ms.openlocfilehash: 2f7f2435d5a4ede1dd48a4dee672ed7affbdfd9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163855"
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>演练：创建数据流代理

本文档演示如何创建基于代理的应用程序，这些应用程序基于数据流而不是控制流。

*控制流* 是指程序中操作的执行顺序。 控制流通过使用条件语句、循环等控制结构进行控制。 另外， *数据流* 是指一种编程模型，在该模型中，只在所有必需的数据都可用时才进行计算。 数据流编程模型与消息传递的概念相关，其中程序的独立组件通过发送消息相互通信。

异步代理同时支持控制流和数据流编程模型。 尽管在很多情况下使用控制流模型，但在其他情况下，数据流模型是合适的，例如，当代理接收数据并执行基于该数据负载的操作时。

## <a name="prerequisites"></a>先决条件

在开始本演练之前，请阅读以下文档：

- [异步代理](../../parallel/concrt/asynchronous-agents.md)

- [异步消息块](../../parallel/concrt/asynchronous-message-blocks.md)

- [如何：使用消息块筛选器](../../parallel/concrt/how-to-use-a-message-block-filter.md)

## <a name="sections"></a><a name="top"></a> 个

本演练包含以下各节：

- [创建基本 Control-Flow 代理](#control-flow)

- [创建基本数据流代理](#dataflow)

- [创建 Message-Logging 代理](#logging)

## <a name="creating-a-basic-control-flow-agent"></a><a name="control-flow"></a> 创建基本 Control-Flow 代理

请考虑以下定义类的示例 `control_flow_agent` 。 `control_flow_agent`类作用于三个消息缓冲区：一个输入缓冲区和两个输出缓冲区。 `run`方法读取循环中的源消息缓冲区，并使用条件语句来指示程序执行的流动。 代理为非零的负值递增一个计数器，并为非零值正值递增另一个计数器。 代理接收到 sentinel 值 zero 后，将计数器的值发送到输出消息缓冲区。 使用 `negatives` 和 `positives` 方法，应用程序可以从代理读取负数值和正值值的计数。

[!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]

尽管此示例在代理中对控制流进行了基本使用，但它演示了基于控制流的编程的串行特性。 必须按顺序处理每条消息，即使输入消息缓冲区中有多条消息可以使用。 数据流模型允许同时计算条件语句的两个分支。 数据流模型还能让你创建更复杂的消息传递网络，这些网络在数据可用时对数据进行操作。

[[顶部](#top)]

## <a name="creating-a-basic-dataflow-agent"></a><a name="dataflow"></a> 创建基本数据流代理

本部分演示如何转换 `control_flow_agent` 类以使用数据流模型执行相同的任务。

数据流代理的工作原理是创建消息缓冲区网络，其中每个消息缓冲区都提供特定用途。 某些消息块使用筛选器函数根据其有效负载接受或拒绝消息。 筛选器函数可确保消息块仅接收某些值。

#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>将控制流代理转换为数据流代理

1. 将类的主体复制 `control_flow_agent` 到其他类，例如 `dataflow_agent` 。 或者，您可以重命名 `control_flow_agent` 类。

1. 删除从方法调用的循环的主体 `receive` `run` 。

[!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]

1. 在 `run` 方法中，在初始化变量 `negative_count` 和后 `positive_count` ，添加一个 `countdown_event` 对象，该对象跟踪活动操作的计数。

[!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]

   `countdown_event`本主题后面将会介绍类。

1. 创建将参与数据流网络的消息缓冲区对象。

[!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]

1. 连接消息缓冲区以形成网络。

[!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]

1. 等待 `event` `countdown event` 设置和对象。 这些事件指示代理已收到 sentinel 值并且所有操作都已完成。

[!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]

下图显示了类的完整数据流网络 `dataflow_agent` ：

![数据流网络](../../parallel/concrt/media/concrt_dataflow.png "数据流网络")

下表描述了网络的成员。

|成员|描述|
|------------|-----------------|
|`increment_active`|一个 [concurrency：：变压器](../../parallel/concrt/reference/transformer-class.md) 对象，它递增活动事件计数器，并将输入值传递到网络的其余部分。|
|`negatives`, `positives`|[concurrency：：调用](../../parallel/concrt/reference/call-class.md) 对象，这些对象可递增数字计数并递减活动事件计数器。 每个对象都使用筛选器来接受负数或正数。|
|`sentinel`|[Concurrency：： call](../../parallel/concrt/reference/call-class.md)对象，它仅接受带有0的 sentinel 值并递减活动事件计数器。|
|`connector`|[Concurrency：： unbounded_buffer](reference/unbounded-buffer-class.md)对象，它将源消息缓冲区连接到内部网络。|

由于在 `run` 单独的线程上调用了方法，因此在网络完全连接之前，其他线程可以向网络发送消息。 `_source`数据成员是一个 `unbounded_buffer` 对象，该对象将从应用程序发送到代理的所有输入缓冲。 为了确保网络处理所有输入消息，代理首先将网络的内部节点链接在一起，然后将该网络的起点链接 `connector` 到 `_source` 数据成员。 这可确保在网络形成时不会处理消息。

由于此示例中的网络基于数据流而不是控制流，因此，网络必须与代理进行通信，使其已完成处理每个输入值，并且该 sentinel 节点已接收到其值。 此示例使用 `countdown_event` 对象来表示所有输入值都已得到处理，并使用 [concurrency：： event](../../parallel/concrt/reference/event-class.md) 对象指示 sentinel 节点已接收其值。 `countdown_event` `event` 当计数器值达到零时，类使用对象进行信号。 数据流网络的开头会递增计数器每次收到值时的值。 网络的每个终端节点在处理输入值后会递减计数器。 在该代理形成数据流网络后，它将等待 sentinel 节点设置 `event` 对象，并等待该对象的 `countdown_event` 计数器达到0。

下面的示例演示了 `control_flow_agent` 、 `dataflow_agent` 和 `countdown_event` 类。 `wmain`函数创建 `control_flow_agent` 和 `dataflow_agent` 对象，并使用 `send_values` 函数将一系列随机值发送到代理。

[!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]

此示例将生成以下示例输出：

```Output
Control-flow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
Dataflow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
```

### <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `dataflow-agent.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

**cl.exe/EHsc dataflow-agent**

[[顶部](#top)]

## <a name="creating-a-message-logging-agent"></a><a name="logging"></a> 创建 Message-Logging 代理

下面的示例演示 `log_agent` 类，该类与类相似 `dataflow_agent` 。 `log_agent`类实现将日志消息写入文件和控制台的异步日志记录代理。 `log_agent`通过类，应用程序可以将消息归类为信息性、警告或错误。 它还使应用程序能够指定是否将每个日志类别写入到文件和/或控制台。 此示例将所有日志消息写入文件，并且仅将错误消息写入控制台。

[!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]

此示例将以下输出写入控制台。

```Output
error: This is a sample error message.
```

此示例还生成 log.txt 文件，其中包含以下文本。

```Output
info: ===Logging started.===
warning: This is a sample warning message.
error: This is a sample error message.
info: ===Logging finished.===
```

### <a name="compiling-the-code"></a>编译代码

复制代码示例并将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `log-filter.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

**cl.exe/EHsc log-filter**

[[顶部](#top)]

## <a name="see-also"></a>请参阅

[并发运行时演练](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

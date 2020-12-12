---
description: 了解有关以下内容的详细信息：异步代理
title: 异步代理
ms.date: 11/19/2018
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
ms.openlocfilehash: 38d2325404d83443ed0bd054793ca200a562359f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338297"
---
# <a name="asynchronous-agents"></a>异步代理

*异步代理* (或仅) *代理* 是一个应用程序组件，该组件与其他代理异步工作以解决更多计算任务。 将代理视为具有设定的生命周期的任务。 例如，一个代理可能会从输入/输出设备 (（例如键盘、磁盘上的文件或网络) 连接）中读取数据，并且其他代理可能会在数据可用时对其执行操作。 第一个代理使用消息传递来向第二个代理通知更多的可用数据。 并发运行时任务计划程序提供了一种高效的机制，使代理能够在无需更低效率的抢占的情况下进行阻止和生成。

代理库定义了 [concurrency：： agent](../../parallel/concrt/reference/agent-class.md) 类来表示异步代理。 `agent` 是一个抽象类，用于声明虚拟方法 [concurrency：： agent：： run](reference/agent-class.md#run)。 `run`方法执行代理执行的任务。 由于 `run` 是抽象的，因此必须在派生自的每个类中实现此方法 `agent` 。

## <a name="agent-life-cycle"></a>代理生命周期

代理具有设定的生命周期。 [Concurrency：： agent_status](reference/concurrency-namespace-enums.md#agent_status)枚举定义代理的各种状态。 下图显示了代理如何从一个状态到另一个状态的进度。 在此图中，实线表示从应用程序调用的方法;虚线表示从运行时调用的方法。

![代理状态图](../../parallel/concrt/media/agentstate.png "代理状态图")

下表描述枚举中的每个状态 `agent_status` 。

|代理状态|描述|
|-----------------|-----------------|
|`agent_created`|尚未计划执行代理。|
|`agent_runnable`|运行时正在计划要执行的代理。|
|`agent_started`|代理已启动并正在运行。|
|`agent_done`|代理已完成。|
|`agent_canceled`|代理在进入状态之前已被取消 `started` 。|

`agent_created` 代理的初始状态， `agent_runnable` `agent_started` 是活动状态，并且 `agent_done` 和 `agent_canceled` 是终端状态。

使用 [concurrency：： agent：： status](reference/agent-class.md#status) 方法检索对象的当前状态 `agent` 。 尽管该 `status` 方法是并发安全方法，但该方法返回时代理的状态可能会发生变化 `status` 。 例如， `agent_started` 当你调用方法时，代理可以处于状态 `status` ，但会在 `agent_done` 该方法返回后移动到状态 `status` 。

## <a name="methods-and-features"></a>方法和功能

下表显示属于类的一些重要的方法 `agent` 。 有关所有类方法的详细信息 `agent` ，请参阅 [代理类](../../parallel/concrt/reference/agent-class.md)。

|方法|描述|
|------------|-----------------|
|[start](reference/agent-class.md#start)|计划 `agent` 要执行的对象并将其设置为 `agent_runnable` 状态。|
|[用](reference/agent-class.md#run)|执行要由对象执行的任务 `agent` 。|
|[完成](reference/agent-class.md#done)|将代理移动到 `agent_done` 状态。|
|[cancel](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|如果代理未启动，则此方法将取消代理的执行并将其设置为 `agent_canceled` 状态。|
|[status](reference/agent-class.md#status)|检索对象的当前状态 `agent` 。|
|[wait](reference/agent-class.md#wait)|等待 `agent` 对象进入 `agent_done` 或 `agent_canceled` 状态。|
|[wait_for_all](reference/agent-class.md#wait_for_all)|等待所有提供 `agent` 的对象进入 `agent_done` 或 `agent_canceled` 状态。|
|[wait_for_one](reference/agent-class.md#wait_for_one)|等待至少一个提供的 `agent` 对象进入 `agent_done` 或 `agent_canceled` 状态。|

创建代理对象后，调用 [concurrency：： agent：： start](reference/agent-class.md#start) 方法将其计划为执行。 运行时在 `run` 计划代理并将其设置为状态后，调用方法 `agent_runnable` 。

运行时不管理异步代理引发的异常。 有关异常处理和代理的详细信息，请参阅 [异常处理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)。

## <a name="example"></a>示例

有关演示如何创建基本的基于代理的应用程序的示例，请参阅 [演练：创建 Agent-Based 应用程序](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)。

## <a name="see-also"></a>请参阅

[异步代理库](../../parallel/concrt/asynchronous-agents-library.md)

---
description: 了解详细信息：计划程序实例
title: 计划程序实例
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: a11c22815c7a73c39033e51ccf47a64ceb47a92d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188048"
---
# <a name="scheduler-instances"></a>计划程序实例

本文档介绍并发运行时中计划程序实例的角色，以及如何使用 [concurrency：：](../../parallel/concrt/reference/scheduler-class.md) [CurrentScheduler 和 Concurrency：：](../../parallel/concrt/reference/currentscheduler-class.md) 类来创建和管理计划程序实例。 当你希望将显式计划策略与特定类型的工作负荷关联时，计划程序实例很有用。 例如，你可以创建一个计划程序实例来以提升的线程优先级运行一些任务，并使用默认计划程序以普通线程优先级运行其他任务。

> [!TIP]
> 并发运行时提供了一个默认计划程序，因此无需在应用程序中创建一个。 由于任务计划程序有助于精细调整应用程序的性能，因此我们建议你从 [并行模式库 (PPL) ](../../parallel/concrt/parallel-patterns-library-ppl.md) 或 [异步代理库](../../parallel/concrt/asynchronous-agents-library.md) （如果你不熟悉并发运行时）开始。

## <a name="sections"></a><a name="top"></a> 个

- [计划程序和 CurrentScheduler 类](#classes)

- [创建计划程序实例](#creating)

- [管理计划程序实例的生存期](#managing)

- [方法和功能](#features)

- [示例](#example)

## <a name="the-scheduler-and-currentscheduler-classes"></a><a name="classes"></a> 计划程序和 CurrentScheduler 类

任务计划程序使应用程序能够使用一个或多个 *计划程序实例* 来计划工作。 [Concurrency：：调度](../../parallel/concrt/reference/scheduler-class.md)器类表示一个计划程序实例，并封装与计划任务相关的功能。

附加到计划程序的线程称为 " *执行上下文*" 或 "只是 *上下文*"。 在当前上下文上，一个计划程序可随时处于活动状态。 活动计划程序也称为 *当前计划程序*。 并发运行时使用 [Concurrency：： CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) 类提供对当前计划程序的访问。 一个上下文的当前计划程序可能不同于另一个上下文的当前计划程序。 运行时不提供当前计划程序的进程级表示形式。

通常， `CurrentScheduler` 类用于访问当前计划程序。 `Scheduler`当需要管理不是当前计划程序的计划程序时，此类很有用。

以下各节介绍了如何创建和管理计划程序实例。 有关阐释这些任务的完整示例，请参阅 [如何：管理计划程序实例](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)。

[[顶部](#top)]

## <a name="creating-a-scheduler-instance"></a><a name="creating"></a> 创建计划程序实例

可以通过以下三种方式创建 `Scheduler` 对象：

- 如果不存在任何计划程序，则运行时在使用运行时功能（例如并行算法）执行工作时，将为您创建一个默认计划程序。 默认计划程序将成为启动并行工作的上下文的当前计划程序。

- [Concurrency：： CurrentScheduler：： Create](reference/currentscheduler-class.md#create)方法可创建一个 `Scheduler` 使用特定策略的对象，并将该计划程序与当前上下文相关联。

- [Concurrency：：调度：： Create](reference/scheduler-class.md#create)方法可创建一个 `Scheduler` 使用特定策略的对象，但不会将其与当前上下文相关联。

允许运行时创建默认计划程序，使所有并发任务共享同一计划程序。 通常， [并行模式库](../../parallel/concrt/parallel-patterns-library-ppl.md) 提供的功能 (PPL) 或 [异步代理库](../../parallel/concrt/asynchronous-agents-library.md) 用于执行并行工作。 因此，无需直接使用计划程序来控制其策略或生存期。 使用 PPL 或代理库时，运行时将创建默认计划程序（如果不存在），并使其成为每个上下文的当前计划程序。 当你创建计划程序并将其设置为当前计划程序时，运行时将使用该计划程序来计划任务。 仅当需要特定计划策略时，才创建其他计划程序实例。 有关与计划程序关联的策略的详细信息，请参阅 [计划程序策略](../../parallel/concrt/scheduler-policies.md)。

[[顶部](#top)]

## <a name="managing-the-lifetime-of-a-scheduler-instance"></a><a name="managing"></a> 管理计划程序实例的生存期

运行时使用引用计数机制来控制对象的生存期 `Scheduler` 。

使用 `CurrentScheduler::Create` 方法或 `Scheduler::Create` 方法创建 `Scheduler` 对象时，运行时将该计划程序的初始引用计数设置为1。 调用 [concurrency：：调度：： Attach](reference/scheduler-class.md#attach) 方法时，运行时将递增引用计数。 `Scheduler::Attach`方法将 `Scheduler` 对象与当前上下文相关联。 这会使其成为当前计划程序。 调用 `CurrentScheduler::Create` 方法时，运行时将创建一个 `Scheduler` 对象并将其附加到当前上下文 (并将引用计数设置为一个) 。 你还可以使用 [concurrency：：调度器：： Reference](reference/scheduler-class.md#reference) 方法递增对象的引用计数 `Scheduler` 。

调用 [concurrency：： CurrentScheduler：:D etach](reference/currentscheduler-class.md#detach) 方法分离当前计划程序或调用 [Concurrency：：：： Release](reference/scheduler-class.md#release) 方法时，运行时会递减引用计数。 当引用计数达到零时，运行时会在 `Scheduler` 所有计划任务完成后销毁对象。 允许正在运行的任务递增当前计划程序的引用计数。 因此，如果引用计数为零，而任务递增引用计数，则运行时不会销毁对象， `Scheduler` 直到引用计数再次达到零且所有任务完成。

运行时 `Scheduler` 为每个上下文维护一个内部对象堆栈。 当调用 `Scheduler::Attach` 或方法时 `CurrentScheduler::Create` ，运行时会将该 `Scheduler` 对象推送到当前上下文的堆栈上。 这会使其成为当前计划程序。 调用时 `CurrentScheduler::Detach` ，运行时会从当前上下文的堆栈中弹出当前计划程序，并将前一个计划程序设置为当前计划程序。

运行时提供了多种方法来管理计划程序实例的生存期。 下表显示了从创建计划程序或将计划程序附加到当前上下文的每个方法的当前上下文中释放或分离计划程序的适当方法。

|Create 或 attach 方法|Release 或分离方法|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

调用不适当的发布或分离方法会在运行时生成未指定的行为。

当你使用可导致运行时创建默认计划程序的 PPL 时，请不要释放或分离此计划程序。 运行时管理它创建的任何计划程序的生存期。

由于运行时不会 `Scheduler` 在所有任务完成之前销毁对象，因此可以使用 [concurrency：： RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) 方法或 [concurrency：： CurrentScheduler：： RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) 方法在 `Scheduler` 对象被销毁时接收通知。 当必须等待对象计划的每个任务完成时，此方法非常有用 `Scheduler` 。

[[顶部](#top)]

## <a name="methods-and-features"></a><a name="features"></a> 方法和功能

本部分概述和类的重要方法 `CurrentScheduler` `Scheduler` 。

将 `CurrentScheduler` 类视为用于创建在当前上下文中使用的计划程序的帮助程序。 `Scheduler`类可用于控制属于另一上下文的计划程序。

下表显示了由类定义的重要方法 `CurrentScheduler` 。

|方法|说明|
|------------|-----------------|
|[创建](reference/currentscheduler-class.md#create)|创建一个 `Scheduler` 对象，该对象使用指定的策略并将其与当前上下文相关联。|
|[Get](reference/currentscheduler-class.md#get)|检索指向 `Scheduler` 与当前上下文关联的对象的指针。 此方法不会递增对象的引用计数 `Scheduler` 。|
|[分离](reference/currentscheduler-class.md#detach)|将当前计划程序与当前上下文分离，并将前一个计划程序设置为当前计划程序。|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|注册在销毁当前计划程序时运行时设置的事件。|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|在当前计划程序中创建 [concurrency：： ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 对象。|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|将轻量级任务添加到当前计划程序的计划队列。|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|检索与当前计划程序关联的策略的副本。|

下表显示了由类定义的重要方法 `Scheduler` 。

|方法|说明|
|------------|-----------------|
|[创建](reference/scheduler-class.md#create)|创建一个 `Scheduler` 对象，该对象使用指定的策略。|
|[附加](reference/scheduler-class.md#attach)|将 `Scheduler` 对象与当前上下文相关联。|
|[引用](reference/scheduler-class.md#reference)|递增对象的引用计数器 `Scheduler` 。|
|[版本](reference/scheduler-class.md#release)|递减对象的引用计数器 `Scheduler` 。|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|在对象被销毁时注册运行时设置的事件 `Scheduler` 。|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|在对象中创建 [concurrency：： ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 对象 `Scheduler` 。|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|从对象计划轻量级任务 `Scheduler` 。|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|检索与对象关联的策略的副本 `Scheduler` 。|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|设置在创建默认计划程序时要使用的运行时所用的策略。|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|将默认策略还原到在调用之前处于活动状态的策略 `SetDefaultSchedulerPolicy` 。 如果在此调用之后创建默认计划程序，则运行时将使用默认策略设置来创建计划程序。|

[[顶部](#top)]

## <a name="example"></a><a name="example"></a> 示例

有关如何创建和管理计划程序实例的基本示例，请参阅 [如何：管理计划程序实例](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)。

## <a name="see-also"></a>请参阅

[任务计划程序](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[如何：管理计划程序实例](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[计划程序策略](../../parallel/concrt/scheduler-policies.md)<br/>
[计划组](../../parallel/concrt/schedule-groups.md)

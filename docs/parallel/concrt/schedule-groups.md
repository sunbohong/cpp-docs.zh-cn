---
description: 了解详细信息：计划组
title: 计划组
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
ms.openlocfilehash: bee4f20ae58f94ddad93770232028df7b82dd39e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188061"
---
# <a name="schedule-groups"></a>计划组

本文档介绍并发运行时中计划组的角色。 *计划组* 关联或组相关任务。 每个计划程序都有一个或多个计划组。 当你需要在任务之间处于较高位置时（例如，当一组相关的任务受益于在相同的处理器节点上执行操作时），可使用计划组。 相反，当您的应用程序具有特定质量要求时（例如，当您想要限制分配给一组任务的处理资源量）时，请使用计划程序实例。 有关计划程序实例的详细信息，请参阅 [计划程序实例](../../parallel/concrt/scheduler-instances.md)。

> [!TIP]
> 并发运行时提供了一个默认计划程序，因此无需在应用程序中创建一个。 由于任务计划程序有助于精细调整应用程序的性能，因此我们建议你从 [并行模式库 (PPL) ](../../parallel/concrt/parallel-patterns-library-ppl.md) 或 [异步代理库](../../parallel/concrt/asynchronous-agents-library.md) （如果你不熟悉并发运行时）开始。

每个 `Scheduler` 对象都具有每个计划节点的默认计划组。 *计划节点* 映射到基础系统拓扑。 运行时为每个处理器包或非一致性内存体系结构创建一个计划节点 (NUMA) node，其中有一个数字较大。 如果未将任务显式关联到计划组，计划程序将选择要将任务添加到哪个组。

`SchedulingProtocol`计划程序策略会影响计划程序执行每个计划组中的任务的顺序。 如果 `SchedulingProtocol` 设置为 `EnhanceScheduleGroupLocality` (这是默认的) ，则任务计划程序会从当前任务完成或以协作方式生成任务时所使用的计划组选择下一任务。 任务计划程序在当前计划组的工作移到下一个可用组之前，搜索工作。 相反，当 `SchedulingProtocol` 设置为时 `EnhanceForwardProgress` ，计划程序将在每个任务完成或生成后移动到下一个计划组。 有关比较这些策略的示例，请参阅 [如何：使用计划组影响执行顺序](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)。

运行时使用 [concurrency：： ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) 类来表示计划组。 若要创建 `ScheduleGroup` 对象，请调用 [concurrency：： CurrentScheduler：： CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup) 或 [concurrency：：：： CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup) 方法。 运行时使用引用计数机制来控制对象的生存期，与 `ScheduleGroup` 处理对象时一样 `Scheduler` 。 创建 `ScheduleGroup` 对象时，运行时将引用计数器设置为一个。 [Concurrency：： ScheduleGroup：： reference](reference/schedulegroup-class.md#reference)方法将引用计数器递增1。 [Concurrency：： ScheduleGroup：： Release](reference/schedulegroup-class.md#release)方法将引用计数器减一。

并发运行时中的许多类型允许将对象与计划组相关联。 例如， [concurrency：： agent](../../parallel/concrt/reference/agent-class.md) 类和 message block 类（如 [concurrency：： unbounded_buffer](reference/unbounded-buffer-class.md)、 [concurrency：： join](../../parallel/concrt/reference/join-class.md)和 concurrency：：[timer](reference/timer-class.md)）提供采用对象的构造函数的重载版本 `ScheduleGroup` 。 运行时使用 `Scheduler` 与此对象关联的对象 `ScheduleGroup` 来计划任务。

你还可以使用 [concurrency：： ScheduleGroup：： ScheduleTask](reference/schedulegroup-class.md#scheduletask) 方法来计划轻量级任务。 有关轻量级任务的详细信息，请参阅 [轻量级任务](../../parallel/concrt/lightweight-tasks.md)。

## <a name="example"></a>示例

有关使用计划组控制任务执行顺序的示例，请参阅 [如何：使用计划组影响执行顺序](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)。

## <a name="see-also"></a>请参阅

[任务计划程序](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[计划程序实例](../../parallel/concrt/scheduler-instances.md)<br/>
[如何：使用计划组影响执行顺序](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

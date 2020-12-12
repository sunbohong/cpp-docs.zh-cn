---
description: 了解详细信息：并发运行时演练
title: 并发运行时演练
ms.date: 11/04/2016
helpviewer_keywords:
- walkthroughs [Concurrency Runtime]
- Concurrency Runtime, walkthroughs
ms.assetid: 7374c5e9-54eb-44bf-9ed9-5e190cfd290b
ms.openlocfilehash: 733a4dddbd800042257a89f88d93a5a6ac11de63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257233"
---
# <a name="concurrency-runtime-walkthroughs"></a>并发运行时演练

本部分中的基于方案的主题介绍如何使用并发运行时的许多功能。

## <a name="in-this-section"></a>本节内容

[演练：使用任务和 XML HTTP 请求进行连接](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
演示如何将 [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) 和 [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) 接口与任务一起使用，以将 HTTP GET 和 POST 请求发送到通用 Windows 平台 (UWP) 应用程序中的 web 服务。

[演练：创建 Agent-Based 应用程序](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)<br/>
介绍如何创建基本的基于代理的应用程序。

[演练：创建数据流代理](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
演示如何创建基于代理的应用程序，这些应用程序基于数据流而不是控制流。

[演练：创建 Image-Processing 网络](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
演示如何创建执行图像处理的异步消息块网络。

[演练：实现先期备货](../../parallel/concrt/walkthrough-implementing-futures.md)<br/>
演示如何异步计算值以便以后使用。

[演练：使用 join 避免死锁](../../parallel/concrt/walkthrough-using-join-to-prevent-deadlock.md)<br/>
使用哲学家就餐问题说明如何使用 [concurrency：： join](../../parallel/concrt/reference/join-class.md) 类来防止应用程序中出现死锁。

[演练：从 User-Interface 线程中移除工作](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)<br/>
演示如何提高用于绘制 Mandelbrot 分形的 MFC 应用程序的性能。

[演练：在 COM-Enabled 应用程序中使用并发运行时](../../parallel/concrt/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application.md)<br/>
演示如何在使用组件对象模型 (COM) 的应用程序中使用并发运行时。

[演练：调整现有代码以使用轻量级任务](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)<br/>
演示如何改编使用 Windows API 的现有代码，以创建和执行线程以使用轻量级任务。

[演练：创建自定义消息块](../../parallel/concrt/walkthrough-creating-a-custom-message-block.md)<br/>
描述如何创建按优先级对传入消息进行排序的自定义消息块类型。

## <a name="related-sections"></a>相关章节

[并发运行时](../../parallel/concrt/concurrency-runtime.md)<br/>
介绍 Visual C++ 的并发编程框架。

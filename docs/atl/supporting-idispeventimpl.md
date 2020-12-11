---
description: 了解详细信息：支持 IDispEventImpl
title: 支持 IDispEventImpl
ms.date: 11/04/2016
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
ms.openlocfilehash: 6a5c12e011ad0dc0f27594325a22dadddd5b92c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157368"
---
# <a name="supporting-idispeventimpl"></a>支持 IDispEventImpl

模板类 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 可用于在 ATL 类中提供对连接点接收器的支持。 连接点接收器使你的类能够处理从外部 COM 对象激发的事件。 使用由类提供的事件接收器映射来映射这些连接点接收器。

若要正确实现类的连接点接收器，必须完成以下步骤：

- 导入每个外部对象的类型库

- 声明 `IDispEventImpl` 接口

- 声明事件接收器映射

- 通知和 unadvise 连接点

实现连接点接收器所涉及的步骤都是通过仅修改类的头文件 () 来实现的。

## <a name="importing-the-type-libraries"></a>导入类型库

对于要处理其事件的每个外部对象，您必须导入类型库。 此步骤定义可以处理的事件，并提供声明事件接收器映射时使用的信息。 [#Import](../preprocessor/hash-import-directive-cpp.md)指令可用于实现此目的。 将支持的 `#import` 每个调度接口行添加到类的标头文件 ( .h) 。

下面的示例 () 导入外部 COM 服务器的类型库 `MSCAL.Calendar.7` ：

[!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]

> [!NOTE]
> 您必须 `#import` 为将支持的每个外部类型库提供单独的语句。

## <a name="declaring-the-idispeventimpl-interfaces"></a>声明 IDispEventImpl 接口

导入每个调度接口的类型库后，需要为 `IDispEventImpl` 每个外部调度接口声明单独的接口。 通过 `IDispEventImpl` 为每个外部对象添加接口声明来修改类的声明。 有关参数的详细信息，请参阅 [IDispEventImpl](../atl/reference/idispeventimpl-class.md)。

对于 `DCalendarEvents` 由类实现的 COM 对象，以下代码为接口声明了两个连接点接收器 `CMyCompositCtrl2` ：

[!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]

## <a name="declaring-an-event-sink-map"></a>声明事件接收器映射

为了使事件通知通过正确的函数进行处理，类必须将每个事件路由到正确的处理程序。 这是通过声明事件接收器映射来实现的。

ATL 提供几个宏、 [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map)、 [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map)和 [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex)，使此映射更容易。 标准格式如下所示：

```cpp
BEGIN_SINK_MAP(comClass)
  SINK_ENTRY_EX(id, iid, dispid, func)
  . . . //additional external event entries
END_SINK_MAP()
```

下面的示例声明一个包含两个事件处理程序的事件接收器映射：

[!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]

实现已接近完成。 最后一个步骤涉及外部接口的通知和 unadvising。

## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>通知和 Unadvising IDispEventImpl 接口

最后一步是实现一个方法，该方法将在正确的时间通知 (或 unadvise) 所有连接点。 必须先完成此建议，然后才能在外部客户端和你的对象之间进行通信。 在对象变得可见之前，将查询对象支持的每个外部调度接口以获取传出接口。 建立连接后，将使用对输出接口的引用来处理来自对象的事件。 此过程称为 "通知"。

使用外部接口完成对象后，应通知传出接口不再由您的类使用。 此过程称为 "unadvising"。

由于 COM 对象的独特性质，此过程在实现之间的详细和执行方面有所不同。 这些详细信息超出了本主题的讨论范围，也不会得到解决。

## <a name="see-also"></a>请参阅

[ATL COM 对象的基本知识](../atl/fundamentals-of-atl-com-objects.md)

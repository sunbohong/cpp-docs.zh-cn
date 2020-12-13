---
description: 了解详细信息：使用 IDispEventSimpleImpl
title: '使用 IDispEventSimpleImpl (ATL) '
ms.date: 08/19/2019
helpviewer_keywords:
- IDispEventSimpleImpl class, using
ms.assetid: 8640ad1a-4bd0-40a5-b5e4-7322685d7aab
ms.openlocfilehash: c0b3f6a0ecdcaae084d3f5d62c19745ee15ac6e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138159"
---
# <a name="using-idispeventsimpleimpl"></a>使用 IDispEventSimpleImpl

使用 `IDispEventSimpleImpl` 处理事件时，你将需要：

- 从 [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)派生类。

- 将事件接收器映射添加到你的类。

- 定义描述事件 [_ATL_FUNC_INFO](../atl/reference/atl-func-info-structure.md) 结构。

- 使用 [SINK_ENTRY_INFO](reference/composite-control-macros.md#sink_entry_info) 宏向事件接收器映射添加条目。

- 实现您想要处理的方法。

- 建议和 unadvise 事件源。

## <a name="example"></a>示例

下面的示例演示如何处理 `DocumentChange` 由 Word 的 **应用程序** 对象触发的事件。 此事件在调度接口上定义为方法 `ApplicationEvents` 。

该示例来自 [ATLEventHandling 示例](../overview/visual-cpp-samples.md)。

```cpp
[ uuid(000209F7-0000-0000-C000-000000000046), hidden ]
dispinterface ApplicationEvents {
properties:
methods:
    [id(0x00000001), restricted, hidden]
    void Startup();

    [id(0x00000002)]
    void Quit();

    [id(0x00000003)]
    void DocumentChange();
};
```

该示例使用 `#import` 从 Word 的类型库生成所需的标头文件。 如果要将此示例与其他版本的 Word 一起使用，则必须指定正确的 mso dll 文件。 例如，Office 2000 提供 mso9.dll 和 OfficeXP 提供 mso.dll。 此代码在 Visual Studio 2017 和更早版本的 *stdafx.h* *(中* 进行了简化) ：

[!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventsimpleimpl_1.h)]

在此示例中，实际使用的类型库中的唯一信息是 Word 对象的 CLSID `Application` 和接口的 IID `ApplicationEvents` 。 此信息仅在编译时使用。

下面的代码以简单的 .h 显示。 相关代码按注释记录：

[!code-cpp[NVC_ATL_EventHandlingSample#3](../atl/codesnippet/cpp/using-idispeventsimpleimpl_2.h)]

下面的代码来自简单的 .cpp：

[!code-cpp[NVC_ATL_EventHandlingSample#4](../atl/codesnippet/cpp/using-idispeventsimpleimpl_3.cpp)]

## <a name="see-also"></a>请参阅

[事件处理](../atl/event-handling-and-atl.md)<br/>
[ATLEventHandling 示例](../overview/visual-cpp-samples.md)

---
description: 了解更多相关信息：使用窗口对象
title: 使用窗口对象
ms.date: 11/04/2016
helpviewer_keywords:
- child windows [MFC], working with
- window objects [MFC], working with
ms.assetid: f73aa254-90e3-46a9-8e9b-d78b7054a331
ms.openlocfilehash: 4a8c6f2c40eadbfe53aa79683bea29847adf684f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172579"
---
# <a name="working-with-window-objects"></a>使用窗口对象

对两种类型的活动使用 windows 调用：

- 处理 Windows 消息

- 在窗口中绘制

若要在任何窗口（包括您自己的子窗口）中处理 Windows 消息，请参阅将 [消息映射到函数](../mfc/reference/mapping-messages-to-functions.md) 以将消息映射到 c + + 窗口类。 然后在类中编写消息处理程序成员函数。

框架应用程序中的大多数绘图发生在视图中，只要必须绘制窗口的内容，就会调用其 [OnDraw](../mfc/reference/cview-class.md#ondraw) 成员函数。 如果窗口是视图的子级，则可以通过 `OnDraw` 调用窗口的成员函数之一，将视图的某些绘图委托给子窗口。

在任何情况下，都需要用于绘图的设备上下文。 您可以使用与您的窗口关联的设备上下文中包含的股票笔、画笔和其他图形对象。 也可以修改这些对象，以获得所需的绘图效果。 根据需要设置设备上下文，调用 [CDC](../mfc/reference/cdc-class.md) 类 (设备上下文类的成员函数) 来绘制线条、形状和文本;使用颜色;和用于处理坐标系统。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [消息处理和映射](../mfc/message-handling-and-mapping.md)

- [在视图中绘制](../mfc/drawing-in-a-view.md)

- [设备上下文](../mfc/device-contexts.md)

- [图形对象](../mfc/graphic-objects.md)

## <a name="see-also"></a>请参阅

[窗口对象](../mfc/window-objects.md)

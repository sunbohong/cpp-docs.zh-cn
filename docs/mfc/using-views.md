---
description: 了解详细信息：使用视图
title: 使用视图
ms.date: 11/04/2016
helpviewer_keywords:
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
ms.openlocfilehash: f17855c1389da44630a21830033c4457db6e3703
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236641"
---
# <a name="using-views"></a>使用视图

视图的职责是将文档的数据以图形方式显示给用户，并接受和解释文档中的用户输入作为操作。 编写视图类的任务是：

- 编写视图类的 [OnDraw](../mfc/reference/cview-class.md#ondraw) 成员函数，用于呈现文档的数据。

- 将相应的 Windows 消息和用户界面对象（如菜单项）连接到视图类中的消息处理程序成员函数。

- 实现这些处理程序来解释用户输入。

此外，您可能还需要覆盖 `CView` 派生视图类中的其他成员函数。 特别是，你可能想要重写 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 以对视图执行特殊的初始化 [，并在视图重绘](../mfc/reference/cview-class.md#onupdate) 自身之前执行任何特殊处理。 对于多页文档，还必须重写 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 以初始化 "打印" 对话框，其中包含要打印的页数和其他信息。 有关重写成员函数的详细信息 `CView` ，请参阅 *MFC 参考* 中的类 [CView](../mfc/reference/cview-class.md) 。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [MFC 中可用的派生视图类](../mfc/derived-view-classes-available-in-mfc.md)

- [在视图中绘制](../mfc/drawing-in-a-view.md)

- [通过视图解释用户输入](../mfc/interpreting-user-input-through-a-view.md)

- [视图在打印中的作用](../mfc/role-of-the-view-in-printing.md)

- [滚动和缩放视图](../mfc/scrolling-and-scaling-views.md)

- [初始化和清理文档和视图](../mfc/initializing-and-cleaning-up-documents-and-views.md)

## <a name="see-also"></a>请参阅

[文档/视图体系结构](../mfc/document-view-architecture.md)<br/>
[CFormView 类](../mfc/reference/cformview-class.md)<br/>
[记录视图 (MFC 数据访问) ](../data/record-views-mfc-data-access.md)<br/>
[跳过序列化机制](../mfc/bypassing-the-serialization-mechanism.md)

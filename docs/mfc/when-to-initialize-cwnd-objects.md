---
description: 了解详细信息：何时初始化 CWnd 对象
title: 何时初始化 CWnd 对象
ms.date: 11/04/2016
helpviewer_keywords:
- window objects [MFC], when to initialize CWnd
- initializing CWnd objects [MFC]
- initializing objects [MFC], CWnd
- CWnd objects [MFC], when HWND is attached
- HWND, when attached to CWnd object
- CWnd objects [MFC], when to initialize
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
ms.openlocfilehash: 89d40b826507574fddd41364ac6cecc526663519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142761"
---
# <a name="when-to-initialize-cwnd-objects"></a>何时初始化 CWnd 对象

不能创建自己的子窗口，也不能在派生对象的构造函数中调用任何 Windows API 函数 `CWnd` 。 这是因为尚未 `HWND` `CWnd` 创建对象的。 大多数特定于 Windows 的初始化（如添加子窗口）都必须在 [OnCreate](../mfc/reference/cwnd-class.md#oncreate) 消息处理程序中完成。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [创建文档框架窗口](../mfc/creating-document-frame-windows.md)

- [文档/视图创建](../mfc/document-view-creation.md)

## <a name="see-also"></a>请参阅

[使用框架窗口](../mfc/using-frame-windows.md)

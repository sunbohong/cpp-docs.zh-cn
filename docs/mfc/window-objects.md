---
description: 了解有关以下内容的详细信息：窗口对象
title: 窗口对象
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], window
- Windows window [MFC]
- MFC, windows
- frame windows [MFC], C++ window objects
- window objects [MFC]
- windows [MFC], C++ window objects
- window messages [MFC]
- HWND
- messages [MFC], Windows
- Visual C++, window objects [MFC]
- HWND, window objects [MFC]
ms.assetid: 28b33ce2-af05-4617-9d03-1cb9a02be687
ms.openlocfilehash: 5a7755dfecc8205279785a6452b04c3f8dc429d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214489"
---
# <a name="window-objects"></a>窗口对象

MFC 提供类 [CWnd](../mfc/reference/cwnd-class.md) 来封装 `HWND` 窗口的句柄。 `CWnd` 对象是一个 C++ 窗口对象，与表示一个 Windows 窗口但包含它的 `HWND` 不同。 使用 `CWnd` 可派生您自己的子窗口类，或使用派生自 `CWnd` 的很多 MFC 类之一。 `CWnd` 类是所有窗口的基类，包括框架窗口、对话框、子窗口、控件和控件条（如工具栏）。 充分了解 [c + + 窗口对象与 HWND 之间的关系](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md) 对于使用 MFC 进行有效编程至关重要。

MFC 提供窗口的某些默认功能和管理，但是，可以从 `CWnd` 派生您自己的类并使用其成员函数自定义所提供的功能。 您可以通过构造 `CWnd` 对象并调用其 [create](../mfc/reference/cwnd-class.md#create) 成员函数来创建子窗口，然后使用成员函数自定义子窗口 `CWnd` 。 可以在框架窗口中嵌入从 [CView](../mfc/reference/cview-class.md)派生的对象，如窗体视图或树视图。 并且可以通过由类 [CSplitterWnd](../mfc/reference/csplitterwnd-class.md)提供的拆分器窗格来支持文档的多个视图。

派生自 `CWnd` 类的每个对象都包含一个消息映射，您可以通过它将 Windows 消息或命令 ID 映射到您自己的处理程序。

有关 Windows 编程的常规资料是了解如何使用可封装 `CWnd` API 的 `HWND` 成员函数的合适资源。

## <a name="functions-for-operating-on-a-cwnd"></a>用于 CWnd 的函数

`CWnd` 及其 [派生的窗口类](../mfc/derived-window-classes.md) 提供构造函数、析构函数和成员函数来初始化对象、创建基础 Windows 结构并访问封装的 `HWND` 。 `CWnd` 还提供了可封装 Windows API 的成员函数，以用于发送消息、访问窗口的状态、转换坐标、更新、滚动、访问剪贴板以及许多其他任务。 大多数采用 `HWND` 参数的 Windows 窗口管理 API 都封装为 `CWnd` 的成员函数。 函数的名称及其参数保留在 `CWnd` 成员函数中。 有关封装的 Windows Api 的详细信息 `CWnd` ，请参阅 [CWnd](../mfc/reference/cwnd-class.md)类。

## <a name="cwnd-and-windows-messages"></a>CWnd 和 Windows 消息

的主要用途之一 `CWnd` 是提供用于处理 Windows 消息的接口，如 WM_PAINT 或 WM_MOUSEMOVE。 的许多成员函数 `CWnd` 都是标准消息的处理程序（以标识符开头 **afx_msg** 和前缀 "On"，如 `OnPaint` 和） `OnMouseMove` 。 [消息处理和映射](../mfc/message-handling-and-mapping.md) 详细介绍了消息和消息处理。 这些信息同样适用于框架的窗口以及您出于特殊目的自己创建的窗口。

### <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [C++ 窗口对象与 HWND 之间的关系](../mfc/relationship-between-a-cpp-window-object-and-an-hwnd.md)

- [派生的窗口类](../mfc/derived-window-classes.md)

- [创建窗口](../mfc/creating-windows.md)

- [销毁窗口对象](../mfc/destroying-window-objects.md)

- [从其 HWND 分离 CWnd](../mfc/detaching-a-cwnd-from-its-hwnd.md)

- [使用窗口对象](../mfc/working-with-window-objects.md)

- [设备上下文](../mfc/device-contexts.md)：使 Windows 绘图设备独立的对象

- [图形对象](../mfc/graphic-objects.md)：笔、画笔、字体、位图、调色板、区域

## <a name="see-also"></a>请参阅

[Windows](../mfc/windows.md)

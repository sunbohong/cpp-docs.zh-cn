---
description: 了解更多： c + + 窗口对象与 HWND 之间的关系
title: C++ 窗口对象与 HWND 之间的关系
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: bdcf52d2890265b854e3eef7854b489b47eda6a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218090"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>C++ 窗口对象与 HWND 之间的关系

窗口 *对象* 是 c + + 类的对象 `CWnd` (或程序直接创建) 派生类。 它提供并响应程序的构造函数和析构函数调用。 另一方面，Windows *窗口* 是与窗口相对应的内部 Windows 数据结构的不透明句柄，并在出现时使用系统资源。 Windows 窗口由 "窗口句柄" (`HWND`) 标识，并在 `CWnd` 通过调用类的成员函数创建对象之后创建 `Create` `CWnd` 。 此窗口可以通过程序调用或用户操作销毁。 窗口句柄存储在窗口对象的 *m_hWnd* 成员变量中。 下图显示了 c + + 窗口对象和 Windows 窗口之间的关系。 [创建 windows 中讨论](../mfc/creating-windows.md)了如何创建 windows。 销毁 [窗口在销毁窗口对象](../mfc/destroying-window-objects.md)中进行了讨论。

![CWnd 窗口对象和生成的窗口](../mfc/media/vc37fj1.gif "CWnd 窗口对象和生成的窗口") <br/>
窗口对象和 Windows 窗口

## <a name="see-also"></a>请参阅

[窗口对象](../mfc/window-objects.md)

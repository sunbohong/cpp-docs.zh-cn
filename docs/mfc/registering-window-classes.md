---
description: 了解详细信息：注册窗口类
title: 注册窗口类
ms.date: 11/04/2016
f1_keywords:
- WndProc
helpviewer_keywords:
- window classes [MFC], registering
- registry [MFC], registering classes
- AfxRegisterWndClass method [MFC]
- MFC, windows
- WinMain method [MFC], and registering window classes
- WndProc method [MFC]
- classes [MFC], registering window classes
- WinMain method [MFC]
- registering window classes [MFC]
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
ms.openlocfilehash: e31f83b691ad12d845afca6a3a5f18d9ba64b0e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218184"
---
# <a name="registering-window-classes"></a>注册窗口类

Windows 传统编程中的窗口“类”定义了可在其中创建任何数量的窗口的“类”（不是 C++ 类）的特征。 此类型的类是一个用于创建窗口的模板或模型。

## <a name="window-class-registration-in-traditional-programs-for-windows"></a>Windows 传统程序中的窗口类注册

在不带 MFC 的传统程序中，你可以将所有消息处理到窗口的 "窗口过程" 或 "" 中 `WndProc` 。 `WndProc` 通过 "窗口类注册" 过程与窗口关联。 主窗口在 `WinMain` 函数中注册，但其他窗口类可以在应用程序中的任何位置注册。 注册依赖于一种结构，该结构包含指向函数的指针以及 `WndProc` 光标、背景画笔等的规格。 在以前对函数的调用中，结构将作为参数传递，以及类的字符串名称 `RegisterClass` 。 因此，注册类可以由多个窗口共享。

## <a name="window-class-registration-in-mfc-programs"></a>MFC 程序中的窗口类注册

相反，大多数窗口类注册活动会在 MFC 框架程序中自动完成。 如果使用 MFC，则通常使用类继承的常规 C++ 语法从现有库类派生 C++ 窗口类。 框架仍使用传统的“注册类”，并且提供了若干在需要时会为您注册的标准窗口类。 可以通过调用 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 全局函数，然后将注册的类传递到的成员函数，来注册其他注册类 `Create` `CWnd` 。 正如这里所述，Windows 中的传统“注册类”不会与 C++ 类混淆。

有关详细信息，请参阅 [技术说明 1](../mfc/tn001-window-class-registration.md)。

## <a name="see-also"></a>请参阅

[创建 Windows](../mfc/creating-windows.md)

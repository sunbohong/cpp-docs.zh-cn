---
description: 了解详细信息：常规窗口创建顺序
title: 常用窗口创建序列
ms.date: 11/04/2016
helpviewer_keywords:
- sequence [MFC], window creation
- frame windows [MFC], creating
- windows [MFC], creating
- sequence [MFC]
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
ms.openlocfilehash: 78a27114ebe3ac309ea8afdc6e04df65f1df1df8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189257"
---
# <a name="general-window-creation-sequence"></a>常用窗口创建序列

创建自己的窗口（如子窗口）时，框架使用的过程与 [文档/视图创建](document-view-creation.md)中所述的过程大致相同。

MFC 提供的所有窗口类都采用 [两阶段构造](one-stage-and-two-stage-construction-of-objects.md)。 也就是说，在调用 c + + 运算符时 **`new`** ，构造函数分配并初始化 c + + 对象，但不创建相应的 Windows 窗口。 这是通过调用 window 对象的 [Create](reference/cwnd-class.md#create) 成员函数来完成的。

`Create`成员函数使 Windows 窗口并将其存储 `HWND` 在 c + + 对象的公共数据成员[m_hWnd](reference/cwnd-class.md#m_hwnd)中。 `Create` 对创建参数提供完全的灵活性。 在调用之前 `Create` ，您可能需要向全局函数 [AfxRegisterWndClass](reference/application-information-and-management.md#afxregisterwndclass) 注册一个窗口类，以便为框架设置图标和类样式。

对于框架窗口，可以使用 [LoadFrame](reference/cframewnd-class.md#loadframe) 成员函数而不是 `Create` 。 `LoadFrame` 使用较少的参数创建 Windows 窗口。 它从资源中获取许多默认值，包括框架的标题、图标、快捷键对应表和菜单。

> [!NOTE]
> 图标、快捷键对应表和菜单资源必须具有公共资源 ID （如 **IDR_MAINFRAME**）才能由 LoadFrame 加载。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [窗口对象](window-objects.md)

- [注册窗口 "类"](registering-window-classes.md)

- [销毁窗口对象](destroying-window-objects.md)

- [创建文档框架窗口](creating-document-frame-windows.md)

## <a name="see-also"></a>请参阅

[创建 Windows](creating-windows.md)

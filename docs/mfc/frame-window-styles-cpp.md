---
description: '详细了解： (c + + Frame-Window 样式) '
title: 框架窗口样式 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: 5d7b0effe4b7cea17eb0b5bd8208563ba552ba99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180338"
---
# <a name="frame-window-styles-c"></a>框架窗口样式 (C++)

你使用框架获取的框架适用于大多数程序，但你可以通过使用高级函数 [PreCreateWindow](reference/cwnd-class.md#precreatewindow) 和 MFC 全局函数 [AfxRegisterWndClass](reference/application-information-and-management.md#afxregisterwndclass)来获得更大的灵活性。 `PreCreateWindow` 是的成员函数 `CWnd` 。

如果将 **WS_HSCROLL** 和 **WS_VSCROLL** 样式应用于主框架窗口，它们将被应用到 **MDICLIENT** 窗口，以便用户可以滚动 **MDICLIENT** 区域。

如果窗口的 **FWS_ADDTOTITLE** 样式位设置 (默认情况下) ，则该视图将根据视图的文档名称告诉框架窗口要在窗口标题栏中显示的标题。

## <a name="what-do-you-want-to-know-more-about"></a>要了解有关的详细信息

- [管理 mdi 子窗口 (MDICLIENT) ](managing-mdi-child-windows.md)，mdi 框架内包含 mdi 子窗口的窗口

- [更改 MFC 创建的窗口的样式](changing-the-styles-of-a-window-created-by-mfc.md)

- [窗口样式](reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>请参阅

[框架窗口](frame-windows.md)

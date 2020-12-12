---
description: 了解详细信息：使用公用控件作为子窗口
title: 将公共控件用作子窗口
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 5a5fda2cbf8d0bf16ccb17f2766b31d24e5c0c67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263551"
---
# <a name="using-a-common-control-as-a-child-window"></a>将公共控件用作子窗口

任何一个 Windows 公共控件均可用作任何其他窗口的子窗口。 以下过程介绍如何以动态方式创建公共控件然后使用它。

### <a name="to-use-a-common-control-as-a-child-window"></a>将公共控件用作子窗口

1. 在相关类或处理程序中定义控件。

1. 使用控件的 [CWnd：： create](../mfc/reference/cwnd-class.md#create) 方法的重写创建 Windows 控件。

1. 创建控件后（如果创建控件的子类，则是在执行 `OnCreate` 处理程序的时候），可使用其成员函数操作控件。 有关方法的详细信息，请参阅 [控件](../mfc/controls-mfc.md) 上各个控件的说明。

1. 完成控件后，使用 [CWnd：:D estroywindow](../mfc/reference/cwnd-class.md#destroywindow) 销毁控件。

## <a name="see-also"></a>请参阅

[创建和使用控件](../mfc/making-and-using-controls.md)<br/>
[控件](../mfc/controls-mfc.md)

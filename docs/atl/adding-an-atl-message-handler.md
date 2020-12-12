---
description: 了解详细信息：添加 ATL 消息处理程序
title: 添加 ATL 消息处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [C++]
- ATL, windows
- message handling [C++], ATL message handler
- windows [C++], ATL
- ATL, message handlers
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
ms.openlocfilehash: 263cbcb863ee287c9b3f4650263a3fac33d7ab7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166338"
---
# <a name="adding-an-atl-message-handler"></a>添加 ATL 消息处理程序

若要将消息处理程序添加 (处理 Windows 消息的成员函数) 添加到控件，请首先选择类视图中的控件。 然后，打开 " **属性** " 窗口，选择 " **消息** " 图标，然后单击与所需消息相对应的框中的下拉控件。 这会在控件的标头文件中添加消息处理程序的声明，并在控件的 .cpp 文件中添加处理程序的主干实现。 它还将添加消息映射并添加处理程序的条目。

在 ATL 中添加消息处理程序类似于向 MFC 类添加消息处理程序。 有关详细信息，请参阅 [添加 MFC 消息处理程序](../mfc/reference/adding-an-mfc-message-handler.md) 。

以下条件仅适用于添加 ATL 消息处理程序：

- 消息处理程序遵循与 MFC 相同的命名约定。

- 新的消息映射项将添加到主消息映射中。 向导无法识别替换消息映射和链接。

## <a name="see-also"></a>请参阅

[实现窗口](../atl/implementing-a-window.md)

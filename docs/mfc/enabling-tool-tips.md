---
description: 了解详细信息：启用工具提示
title: 启用工具提示
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 677d2cc071e87f62f9bd2e700d8fdba166dfdee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290942"
---
# <a name="enabling-tool-tips"></a>启用工具提示

您可以为窗口的子控件（如窗体视图或对话框上的控件）启用工具提示支持。

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>为窗口的子控件启用工具提示

1. 为要为其提供要提供工具提示的窗口调用 `EnableToolTips`。

1. 为 [TTN_NEEDTEXT 通知](handling-ttn-needtext-notification-for-tool-tips.md) 处理程序中的每个控件提供一个字符串。 处理程序位于包含子控件（例如，窗体视图类）的窗口的消息映射中。 此处理程序应调用一个函数，该函数标识控件并设置 **pszText** 以指定工具提示控件使用的文本。

## <a name="see-also"></a>请参阅

[Windows 中不是从 CFrameWnd 派生的工具提示](tool-tips-in-windows-not-derived-from-cframewnd.md)

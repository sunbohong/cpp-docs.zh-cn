---
description: 了解详细信息：如何：使用 Message-Map 交叉引用
title: 如何：使用消息映射交叉引用
ms.date: 11/04/2016
helpviewer_keywords:
- windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
ms.openlocfilehash: 4bbc140db59a7df4abd42fdcf68b47273ec3e846
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219650"
---
# <a name="how-to-use-the-message-map-cross-reference"></a>如何：使用消息映射交叉引用

在标记为的项中 \<memberFxn> ，为派生的 [CWnd](../../mfc/reference/cwnd-class.md) 类编写你自己的成员函数。 将函数命名为您喜欢的任何名称。 其他函数，如 `OnActivate`，是 `CWnd` 类的成员函数。 如果调用这些函数，则会传递消息给 `DefWindowProc` Windows 函数。 要处理 Windows 通知消息，请重写派生类中相应的 `CWnd` 函数。 您的函数应调用基类中的重写函数使基类和 Windows 响应消息。

在所有情况下，请将函数原型放在 `CWnd` 派生的类标头中，并对消息映射条目进行编码，如下所示。

使用了以下术语：

|术语|定义|
|----------|----------------|
|id|任何用户定义的菜单项 ID（WM_COMMAND 消息）或控件 ID（子窗口通知消息）。|
|“message”和“wNotifyCode”|在 WINDOWS.H 中定义的 Windows 消息 ID。|
|nMessageVariable|包含 Windows 函数返回值的变量的名称 `RegisterWindowMessage` 。|

## <a name="see-also"></a>请参阅

[消息映射](../../mfc/reference/message-maps-mfc.md)

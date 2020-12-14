---
description: 了解有关：运行成员函数的详细信息
title: 运行成员函数
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: ae67c6b02344a65735ce06775b1d1788d1dabf2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217817"
---
# <a name="run-member-function"></a>运行成员函数

框架应用程序将大部分时间花在[CWinApp](../mfc/reference/cwinapp-class.md)类的[Run](../mfc/reference/cwinapp-class.md#run)成员函数中。 初始化后， `WinMain` 调用 `Run` 以处理消息循环。

`Run` 遍历消息循环，并检查消息队列中的可用消息。 如果有可用的消息， `Run` 则调度该消息以进行操作。 如果没有可用的消息（通常为 true），则 `Run` 调用 `OnIdle` 以执行你或框架可能需要完成的任何空闲时间处理。 如果没有要执行的消息和空闲处理，则应用程序将进行等待，直到发生某些情况。 当应用程序终止时， `Run` 调用 `ExitInstance` 。 [OnIdle 成员函数](../mfc/onidle-member-function.md)中的数字显示了消息循环中的操作序列。

消息调度取决于消息类型。 有关详细信息，请参阅 [框架中的消息和命令](../mfc/messages-and-commands-in-the-framework.md)。

## <a name="see-also"></a>请参阅

[CWinApp：应用程序类](../mfc/cwinapp-the-application-class.md)

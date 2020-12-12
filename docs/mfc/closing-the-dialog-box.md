---
description: 了解详细信息：关闭对话框
title: 关闭对话框
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], closing
- dialog boxes [MFC], closing
ms.assetid: 946f5675-c482-46a4-a5dd-34fe138ffae5
ms.openlocfilehash: 4e60bdfb1ecb6968996d6c657f0c667ad2686a56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338374"
---
# <a name="closing-the-dialog-box"></a>关闭对话框

当用户选择模式对话框中的某个按钮（通常是“确定”按钮或“取消”按钮）时，该对话框将关闭。 通过选择 "确定" 或 "取消" 按钮，Windows 将使用按钮的 ID （ **IDOK** 或 **IDCANCEL**）发送对话框对象 a **BN_CLICKED** 的控件通知消息。 `CDialog` 提供了针对以下消息的默认处理程序函数：`OnOK` 和 `OnCancel`。 默认处理程序调用 `EndDialog` 成员函数以关闭对话框窗口。 您还可以从您自己的代码中调用 `EndDialog`。 有关详细信息，请参阅 [](reference/cdialog-class.md#enddialog) `CDialog` *MFC 参考* 中类的 EndDialog 成员函数。

若要安排关闭和删除无模式对话框，请重写 `PostNcDestroy` 并对 **`delete`** 指针调用运算符 **`this`** 。 [销毁对话框](destroying-the-dialog-box.md) 说明接下来会发生的情况。

## <a name="see-also"></a>请参阅

[在 MFC 中使用对话框](life-cycle-of-a-dialog-box.md)

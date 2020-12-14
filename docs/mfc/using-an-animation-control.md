---
description: 了解更多相关信息：使用动画控件
title: 使用动画控件
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
ms.openlocfilehash: 7ef4a7b5eb005569ac2a3e3cb66cc0ed785e9299
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202712"
---
# <a name="using-an-animation-control"></a>使用动画控件

动画控件的典型用法遵循下面的模式：

- 创建滑块控件。 如果滑块控件是在对话框模板中指定的，则在创建对话框时自动进行创建。  (应在对话框类中具有对应于动画控件的 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) 成员。 ) 或者，可以使用 [create](../mfc/reference/canimatectrl-class.md#create) member 函数将控件创建为任何窗口的子窗口。

- 通过调用 [Open](../mfc/reference/canimatectrl-class.md#open) 成员函数，将 AVI 剪辑加载到动画控件中。 如果动画控件位于对话框中，则可以在对话框类的 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 函数中执行此操作。

- 通过调用 [play](../mfc/reference/canimatectrl-class.md#play) 成员函数来播放剪辑。 如果动画控件位于对话框中，则可以在对话框类的函数中执行此操作 `OnInitDialog` 。 `Play`如果动画控件具有 ACS_AUTOPLAY 样式集，则不需要调用。

- 如果要显示剪辑的某些部分或按帧播放它，请使用 `Seek` 成员函数。 若要停止正在播放的剪辑，请使用 `Stop` 成员函数。

- 如果你不打算立即销毁该控件，请通过调用成员函数从内存中删除该剪辑 `Close` 。

- 如果动画控件位于对话框中，则它和 `CAnimateCtrl` 对象将自动销毁。 否则，您需要确保正确地销毁控件和 `CAnimateCtrl` 对象。 销毁控件将自动关闭 AVI 剪辑。

## <a name="see-also"></a>请参阅

[使用 CAnimateCtrl](../mfc/using-canimatectrl.md)<br/>
[控件](../mfc/controls-mfc.md)

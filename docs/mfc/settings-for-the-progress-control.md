---
description: 了解详细信息：进度控件的设置
title: 进度控件的设置
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 0cf3caa5e7b87062b1714f8e5e350840157ff7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217063"
---
# <a name="settings-for-the-progress-control"></a>进度控件的设置

 ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) 的进度控制的基本设置是范围和当前位置。 范围表示操作的整个持续时间。 当前位置表示应用程序完成操作的进度。 对范围或位置所做的任何更改都会导致进度控件重绘其自身。

默认情况下，范围设置为 0-100，初始位置设置为0。 若要检索进度控件的当前范围设置，请使用 [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) 成员函数。 若要更改范围，请使用 [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) 成员函数。

若要设置位置，请使用 [SetPos](../mfc/reference/cprogressctrl-class.md#setpos)。 若要在不指定新值的情况下检索当前位置，请使用 [GetPos](../mfc/reference/cprogressctrl-class.md#getpos)。 例如，你可能只想查询当前操作的状态。

若要单步执行进度控件的当前位置，请使用 [StepIt](../mfc/reference/cprogressctrl-class.md#stepit)。 若要设置每个步骤的数量，请使用 [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>请参阅

[使用 CProgressCtrl](../mfc/using-cprogressctrl.md)<br/>
[控件](../mfc/controls-mfc.md)

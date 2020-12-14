---
description: 了解详细信息：数值调节钮成员函数
title: 调节钮成员函数
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 6a03ab33d29634ed85d807eb5b51edfdef310d65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216829"
---
# <a name="spin-button-member-functions"></a>调节钮成员函数

可以使用多个成员函数 ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) 。 使用这些函数可更改数值调节钮的以下特性。

- **加速** 您可以调整当用户按下箭头按钮时该位置更改的速率。 若要使用加速，请使用 [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) 和 [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) 成员函数。

- **基本** 您可以更改基本 (10 或 16) 用于显示合作者窗口标题中的位置。 若要使用基础，请使用 [GetBase](../mfc/reference/cspinbuttonctrl-class.md#getbase) 和 [SetBase](../mfc/reference/cspinbuttonctrl-class.md#setbase) 成员函数。

- **合作者窗口** 您可以动态设置合作者窗口。 若要查询或更改哪个控件是合作者窗口，请使用 [GetBuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) 和 [SetBuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) 成员函数。

- **位置** 您可以查询和更改位置。 若要直接使用位置，请使用 [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) 和 [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) 成员函数。 由于合作者控件的标题可能已更改（例如，在合作者是编辑控件的情况下），因此 `GetPos` 将检索当前标题并相应地调整位置。

- **范围** 可以更改数值调节钮的最大和最小位置。 默认情况下，最大值设置为 0，最小值设置为 100。 由于默认最大值小于默认最小值，因此箭头按钮的操作是反直觉的。 通常，您将使用 [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) 成员函数设置范围。 若要查询范围，请使用 [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange)。

## <a name="see-also"></a>请参阅

[使用 CSpinButtonCtrl](../mfc/using-cspinbuttonctrl.md)<br/>
[控件](../mfc/controls-mfc.md)

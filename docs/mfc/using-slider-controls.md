---
description: 了解详细信息：使用滑块控件
title: 使用滑块控件
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
ms.openlocfilehash: b9134d76261bf5c15bfef90260394ee6a4c760e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322655"
---
# <a name="using-slider-controls"></a>使用滑块控件

滑块控件的典型用法遵循以下模式：

- 创建滑块控件。 如果滑块控件是在对话框模板中指定的，则在创建对话框时自动进行创建。  (应在对话框类中具有对应于滑块控件的 [CSliderCtrl](../mfc/reference/csliderctrl-class.md) 成员。 ) 或者，可以使用 [create](../mfc/reference/csliderctrl-class.md#create) 成员函数将控件创建为任何窗口的子窗口。

- 调用各种 Set 成员函数来设置滑块控件的值。 可进行的更改包括设置滑块的最小和最大位置、绘制刻度线、设置选择范围以及重新定位滑块。 对于对话框中的控件，可以在对话框的 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 函数中执行此操作。

- 当用户与该控件交互时，将发送各种通知消息。 可以通过调用 [GetPos](../mfc/reference/csliderctrl-class.md#getpos) 成员函数，从控件提取滑块值。

- 在使用完该控件之后，您需要确保将其正确地销毁。 如果滑块控件在对话框中，将自动销毁该控件和 `CSliderCtrl` 对象。 否则，您需要确保正确地销毁控件和 `CSliderCtrl` 对象。

## <a name="see-also"></a>请参阅

[使用 CSliderCtrl](../mfc/using-csliderctrl.md)<br/>
[控件](../mfc/controls-mfc.md)

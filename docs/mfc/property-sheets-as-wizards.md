---
description: 了解详细信息：属性表作为向导
title: 属性表作为向导
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: 2a68a16936e8ab134bab2fe78dac0d29c125b4db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248860"
---
# <a name="property-sheets-as-wizards"></a>属性表作为向导

向导属性表的关键特征是，“下一步”或“完成”、“后退”和“取消”按钮而不是选项卡提供有导航。 在对属性表对象调用[CPropertySheet：:D omodal](../mfc/reference/cpropertysheet-class.md#domodal)之前，需要先调用[CPropertySheet：： SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode)以利用此功能。

当从一个页面移动到另一页时，用户接收相同的 [CPropertyPage：： OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) 和 [CPropertyPage：： OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) 通知。 “下一步”和“完成”按钮是手动独占控件；即，这两个按钮一次只显示其中一个。 在第一页上，应启用“下一步”按钮。 如果用户位于最后一页，则应启用“完成”按钮。 这不是由框架自动完成的。 在最后一页上必须调用 [CPropertySheet：： SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) 以实现此目的。

若要显示所有默认按钮，则必须显示“完成”按钮并移动“下一步”按钮。 然后移动“后退”按钮，以便保留其与“下一步”按钮的相对位置。

## <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>请参阅

[属性表](../mfc/property-sheets-mfc.md)

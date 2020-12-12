---
description: 了解有关以下内容的详细信息： MFC 中的属性表和属性页
title: MFC 中的属性表和属性页
ms.date: 11/04/2016
helpviewer_keywords:
- property pages [MFC], MFC
- controls [MFC], property sheets
- property sheets, MFC
- tab dialog boxes
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
ms.openlocfilehash: 93662dcf07e2810ad9f4f51d6df8341f9f6df6dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185422"
---
# <a name="property-sheets-and-property-pages-in-mfc"></a>MFC 中的属性表和属性页

属性表，也称为选项卡对话框，是包含属性页的对话框。 每个属性页都基于对话框模板资源并包含控件。 它包含在顶部有一个选项卡的页面上。 该选项卡将显示该页的名称并指示其用途。 用户单击属性表中的选项卡以选择一组控件。

使用页可以将属性表中的控件分组为有意义的集。 包含的属性表通常具有自己的几个控件。 这适用于所有页面。

属性表基于类 [CPropertySheet](../mfc/reference/cpropertysheet-class.md)。 属性页基于类 [CPropertyPage](../mfc/reference/cpropertypage-class.md)。

属性表是一种特殊类型的对话框，通常用于修改某个外部对象的属性，如视图中的当前选定内容。 属性表有三个主要部分： "包含" 对话框、一个或多个属性页（一次显示一个）以及用户单击以选择该页面的每个页面顶部的选项卡。 如果要更改多个类似的设置组或选项，属性表非常有用。 属性表以易于理解的方式对信息进行分组。

> [!NOTE]
> 使用尝试显示属性表时 `CPropertySheet::DoModal` ，系统可能会生成首次异常。 发生此异常的原因是系统尝试在创建对象之前更改对象的 [窗口样式](../mfc/reference/styles-used-by-mfc.md#window-styles) 。 有关此异常的详细信息以及如何避免或处理此异常，请参阅 [CPropertySheet：:D omodal](../mfc/reference/cpropertysheet-class.md#domodal)。

## <a name="see-also"></a>请参阅

[属性表](../mfc/property-sheets-mfc.md)

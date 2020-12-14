---
description: 了解详细信息：树控件项信息
title: 树控件项信息
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], item information
- CTreeCtrl class [MFC], item information
ms.assetid: 8dcab855-27de-49e9-95d8-f78ba963ea71
ms.openlocfilehash: ced75bdf6ed6a10e3a34536adf4af0ed1c7e0c86
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264136"
---
# <a name="tree-control-item-information"></a>树控件项信息

树控件 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 具有许多成员函数，这些函数可检索有关控件中的项的信息。 [GetItem](../mfc/reference/ctreectrl-class.md#getitem)成员函数检索与项关联的部分或全部数据。 此数据可以包括项目的文本、状态、图像、子项目计数和应用程序定义的 32 位数据值。 还有一个 [SetItem](../mfc/reference/ctreectrl-class.md#setitem) 函数，它可以设置与项关联的部分或全部数据。

[GetItemState](../mfc/reference/ctreectrl-class.md#getitemstate)、 [GetItemText](../mfc/reference/ctreectrl-class.md#getitemtext)、 [GetItemData](../mfc/reference/ctreectrl-class.md#getitemdata)和[GetItemImage](../mfc/reference/ctreectrl-class.md#getitemimage)成员函数检索项的各个特性。 其中每个函数都有一个对应的为项目设置特性的 Set 函数。

[GetNextItem](../mfc/reference/ctreectrl-class.md#getnextitem)成员函数检索具有与当前项的指定关系的树控件项。 此函数可检索项目的父级、下一或上一可见项目、第一个子项目等等。 还提供遍历树的成员函数： [GetRootItem](../mfc/reference/ctreectrl-class.md#getrootitem)、 [GetFirstVisibleItem](../mfc/reference/ctreectrl-class.md#getfirstvisibleitem)、 [GetNextVisibleItem](../mfc/reference/ctreectrl-class.md#getnextvisibleitem)、 [GetPrevVisibleItem](../mfc/reference/ctreectrl-class.md#getprevvisibleitem)、 [GetChildItem](../mfc/reference/ctreectrl-class.md#getchilditem)、 [GetNextSiblingItem](../mfc/reference/ctreectrl-class.md#getnextsiblingitem)、 [GetPrevSiblingItem](../mfc/reference/ctreectrl-class.md#getprevsiblingitem)、 [GetParentItem](../mfc/reference/ctreectrl-class.md#getparentitem)、 [GetSelectedItem](../mfc/reference/ctreectrl-class.md#getselecteditem)和 [GetDropHilightItem](../mfc/reference/ctreectrl-class.md#getdrophilightitem)。

[GetItemRect](../mfc/reference/ctreectrl-class.md#getitemrect)成员函数检索树控件项的边框。 [GetCount](../mfc/reference/ctreectrl-class.md#getcount)和[GetVisibleCount](../mfc/reference/ctreectrl-class.md#getvisiblecount)成员函数将分别检索树控件中的项计数和树控件的窗口中当前可见项的计数。 可以通过调用 [ensurevisible\](../mfc/reference/ctreectrl-class.md#ensurevisible) 成员函数来确保特定项可见。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)

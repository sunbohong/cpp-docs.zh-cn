---
description: 了解详细信息：使用树控件
title: 使用树控件
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
ms.openlocfilehash: 7b8a10acc3ee256f4b26c9988c4de7df900e1535
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143190"
---
# <a name="using-tree-controls"></a>使用树控件

树控件 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 的典型用法遵循下面的模式：

- 创建滑块控件。 如果控件是在对话框模板中指定的，或者如果使用的是 `CTreeView` ，则在创建对话框或视图时，创建是自动的。 如果要将树控件创建为某个其他窗口的子窗口，请使用 [create](../mfc/reference/ctreectrl-class.md#create) 成员函数。

- 如果希望树形控件使用图像，请通过调用 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist)来设置图像列表。 还可以通过调用 [SetIndent](../mfc/reference/ctreectrl-class.md#setindent)来更改缩进。 要执行此操作，有一个很好的时机，就 [是 (对话框中的](../mfc/reference/cdialog-class.md#oninitdialog) 控件) 或视图) 的 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (。

- 通过 `CTreeCtrl` 对每个数据项调用的 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 函数，将数据置于控件中。 `InsertItem` 返回可用于稍后引用的项的句柄，例如添加子项时。 初始化数据的一个好时机就是 `OnInitDialog` (对话框中的控件) 或 `OnInitialUpdate` 视图) 的 (。

- 当用户与该控件交互时，将发送各种通知消息。 您可以指定一个函数来处理您要处理的每个消息，方法是在控件窗口的消息映射中添加 ON_NOTIFY_REFLECT 宏，或将 ON_NOTIFY 的宏添加到您的父窗口的消息映射。 有关可能的通知的列表，请参阅本主题后面的 [树控件通知消息](../mfc/tree-control-notification-messages.md) 。

- 调用各种 Set 成员函数来设置滑块控件的值。 可以进行的更改包括设置缩进和更改与项关联的文本、图像或数据。

- 使用各种 Get 函数检查控件的内容。 您还可以使用允许您检索指定项的父项、子项和同级的句柄的函数遍历树控件的内容。 甚至可以对特定节点的子节点进行排序。

- 完成控件后，请确保它已正确销毁。 如果树控件位于对话框中或者为视图，则它和 `CTreeCtrl` 对象将自动销毁。 否则，您需要确保正确地销毁控件和 `CTreeCtrl` 对象。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)

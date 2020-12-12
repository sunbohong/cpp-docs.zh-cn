---
description: 了解有关以下内容的详细信息：与树控件通信
title: 与树控件通信
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 82ee4fe0beb65e44166b4d68ffd44923b7fe0c76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310559"
---
# <a name="communicating-with-a-tree-control"></a>与树控件通信

根据对象的创建方式，使用不同的方法来调用 [CTreeCtrl](reference/ctreectrl-class.md) 对象中的成员函数：

- 如果树控件位于对话框中，请使用你在对话框类中创建的 `CTreeCtrl` 类型的成员变量。

- 如果树控件是子窗口，请使用用于构造对象的 `CTreeCtrl` 对象（或指针）。

- 如果使用的是 `CTreeView` 对象，请使用函数 [CTreeView：： GetTreeCtrl](reference/ctreeview-class.md#gettreectrl) 获取对树控件的引用。 您可以使用此值初始化其他引用或将引用的地址分配给 `CTreeCtrl` 指针。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](using-ctreectrl.md)<br/>
[控件](controls-mfc.md)

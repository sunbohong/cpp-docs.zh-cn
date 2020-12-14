---
description: 了解详细信息：树控件项位置
title: 树控件项位置
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], item position
- item position in tree controls
- tree controls [MFC], item position
- position, CTreeCtrl items
ms.assetid: cd264344-2cf9-4d90-9ea8-c6900b6f60e7
ms.openlocfilehash: 7eeab82c48344f7e16a31b8d6962007024277dfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264060"
---
# <a name="tree-control-item-position"></a>树控件项位置

使用成员函数向树控件添加项时，将设置项的初始位置 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) `InsertItem` 。 成员函数调用指定父项的句柄和项的句柄，之后要插入新项。 第二个句柄必须标识给定父项的子项或以下值之一： `TVI_FIRST` 、 `TVI_LAST` 或 `TVI_SORT` 。

`TVI_FIRST`指定或时 `TVI_LAST` ，树控件将新项放置在给定父项的子项列表的开头或结尾。 如果 `TVI_SORT` 指定了，则树控件会根据项标签的文本，以字母顺序将新项插入到子项列表。

可以通过调用 [SortChildren](../mfc/reference/ctreectrl-class.md#sortchildren) 成员函数，将父项的子项列表按字母顺序排序。 此函数包含一个参数，该参数指定是否也按字母顺序对给定父项的所有级别的子项进行排序。

[SortChildrenCB](../mfc/reference/ctreectrl-class.md#sortchildrencb)成员函数允许根据您定义的条件对子项进行排序。 调用此函数时，需要指定一个应用程序定义的回调函数，每当需要确定两个子项的相对顺序时，树控件都可以调用此函数。 回调函数接收所比较的项的 2 32 位应用程序定义的值，以及在调用时指定的第三个32位值 `SortChildrenCB` 。

## <a name="see-also"></a>请参阅

[使用 CTreeCtrl](../mfc/using-ctreectrl.md)<br/>
[控件](../mfc/controls-mfc.md)

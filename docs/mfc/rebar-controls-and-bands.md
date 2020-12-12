---
description: 了解更多： Rebar 控件和带区
title: Rebar 控件和带区
ms.date: 11/04/2016
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
ms.openlocfilehash: 27ada3633a560ad8b5852b05bdd6330a0936fb99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248562"
---
# <a name="rebar-controls-and-bands"></a>Rebar 控件和带区

Rebar 控件的主要用途是用作子窗口、通用对话框控件、菜单、工具栏等的容器。 "带区" 的概念支持此包含。 每个 rebar 带区可以包含手柄栏、位图、文本标签和子窗口的任意组合。

类 `CReBarCtrl` 有许多成员函数，可用于检索和操作特定 rebar 带区的信息：

- [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) 检索 rebar 控件中的当前带区的数目。

- [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo) 使用指定的带区中的信息初始化 **REBARBANDINFO** 结构。 存在相应的 [SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo) 成员函数。

- [GetRect](../mfc/reference/crebarctrl-class.md#getrect) 检索指定带区的边框。

- [GetRowCount](../mfc/reference/crebarctrl-class.md#getrowcount) 检索 rebar 控件中带区的行数。

- [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex) 检索指定带区的索引。

- [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders) 检索带区的边框。

除了操作外，还提供了几个成员函数，使您可以在特定的 rebar 带区上操作。

[InsertBand](../mfc/reference/crebarctrl-class.md#insertband) 和 [DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband) 添加和删除 rebar 带区。 [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband) 和 [MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband) 影响特定 rebar 带区的当前大小。 [MoveBand](../mfc/reference/crebarctrl-class.md#moveband) 更改特定 rebar 带区的索引。 [ShowBand](../mfc/reference/crebarctrl-class.md#showband) 显示或隐藏用户的 rebar 带区。

下面的示例演示如何将工具栏带区 (*m_wndToolBar*) 添加到 (*m_wndReBar*) 的现有 rebar 控件。 通过初始化 `rbi` 结构，然后调用成员函数来描述带区 `InsertBand` ：

[!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]

## <a name="see-also"></a>请参阅

[使用 CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)

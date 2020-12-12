---
description: 了解详细信息：使用图像列表和 Rebar 控件
title: 对 Rebar 控件使用图像列表
ms.date: 11/04/2016
helpviewer_keywords:
- image lists [MFC], rebar controls
- rebar controls [MFC], image lists
ms.assetid: 1a5836ac-019a-46aa-8741-b35c3376b839
ms.openlocfilehash: ae4aa0259cbe850dbab8ef4bc04277014b39e357
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271793"
---
# <a name="using-an-image-list-with-a-rebar-control"></a>对 Rebar 控件使用图像列表

每个 rebar 带区除了别的之外还可以包含关联图像列表的图像。 以下过程详述了在 rebar 带区显示图像的必需步骤。

### <a name="to-display-images-in-a-rebar-band"></a>在 rebar 带区显示图像

1. 通过调用 [SetImageList](../mfc/reference/crebarctrl-class.md#setimagelist)并传递指向现有图像列表的指针，将图像列表附加到 rebar 控件对象。

1. 修改 **REBARBANDINFO** 结构，将图像分配给 rebar 带区：

   - 将 *fMask* 成员设置为 `RBBIM_IMAGE` ，使用按位 "或" 运算符在必要时包括其他标志。

   - 将 *iImage* 成员设置为要显示的图像的图像列表索引。

1. 使用必需信息初始化任何其余的数据成员，如包含子窗口的大小、文本和句柄。

1. 使用 [CReBarCtrl：： InsertBand](../mfc/reference/crebarctrl-class.md#insertband)的调用插入新带区)  (，同时传递 **REBARBANDINFO** 结构。

以下示例假定已将带两个图像的现有图像列表对象附加到 rebar 控件对象 (`m_wndReBar`)。 包含第一个图像的新的 rebar 带区（由 `rbi` 定义）是通过调用 `InsertBand` 添加的：

[!code-cpp[NVC_MFCControlLadenDialog#28](../mfc/codesnippet/cpp/using-an-image-list-with-a-rebar-control_1.cpp)]

## <a name="see-also"></a>请参阅

[使用 CReBarCtrl](../mfc/using-crebarctrl.md)<br/>
[控件](../mfc/controls-mfc.md)

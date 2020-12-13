---
description: 了解详细信息：将控件添加到属性表
title: 将控件添加到属性表
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: e220d08b46f1db7e09ad1f1398731ce7a98f2dc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339077"
---
# <a name="adding-controls-to-a-property-sheet"></a>将控件添加到属性表

默认情况下，属性表将为属性页、选项卡索引和“确定”、“取消”和“应用”按钮分配窗口区域。  (无模式属性表没有 "确定"、"取消" 和 "应用" 按钮。 ) 可以向属性表中添加其他控件。 例如，您可以在属性页区域右侧添加预览窗口，以便为用户显示对外部对象应用当前设置的效果。

可以在 `OnCreate` 处理程序中向属性表对话框添加控件。 容纳附加控件通常需要扩展属性表对话框的大小。 调用 **CPropertySheet：： OnCreate** 基类后，调用 [GetWindowRect](reference/cwnd-class.md#getwindowrect) 以获取当前已分配属性表窗口的宽度和高度，展开该矩形的维度，然后调用 [MoveWindow](reference/cwnd-class.md#movewindow) 以更改属性表窗口的大小。

## <a name="see-also"></a>请参阅

[属性表](property-sheets-mfc.md)<br/>
[CPropertyPage 类](reference/cpropertypage-class.md)<br/>
[CPropertySheet 类](reference/cpropertysheet-class.md)

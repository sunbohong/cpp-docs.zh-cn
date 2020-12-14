---
description: 了解详细信息：创建列表控件
title: 创建列表控件
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 5be1a9ce7a2cd8279d576dfc41e44c810c433515
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309571"
---
# <a name="creating-the-list-control"></a>创建列表控件

如何创建列表控件 ([CListCtrl](reference/clistctrl-class.md) 的) 取决于你是直接使用该控件还是使用 [CListView](reference/clistview-class.md) 类。 如果使用 `CListView` ，则框架会将视图构造为其文档/视图创建序列的一部分。 创建列表视图时，会同时创建列表控件 (这两种情况) 。 在视图的 [OnCreate](reference/cwnd-class.md#oncreate) 处理程序函数中创建控件。 在这种情况下，控件可通过调用 [GetListCtrl](reference/clistview-class.md#getlistctrl)来添加项。

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>直接在对话框中使用 CListCtrl

1. 在对话框编辑器中，将列表控件添加到对话框模板资源。 指定其控件 ID。

1. 使用 " [添加成员变量向导](../ide/adding-a-member-variable-visual-cpp.md) " 可以添加具有控件属性的类型的成员变量 `CListCtrl` 。 您可以使用此成员调用 `CListCtrl` 成员函数。

1. 使用 [类向导](reference/mfc-class-wizard.md) 可以在对话框类中映射处理程序函数，以获取需要处理的任何列表控件通知消息 (参阅将 [消息映射到](reference/mapping-messages-to-functions.md)) 的函数。

1. 在 [OnInitDialog](reference/cdialog-class.md#oninitdialog)中，设置的样式 `CListCtrl` 。 请参阅 [更改列表控件样式](changing-list-control-styles.md)。 这会确定在控件中获得的 "视图" 类型，不过以后可以更改视图。

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>在非对话框窗口中使用 CListCtrl

1. 在视图或窗口类中定义控件。

1. 调用控件的 Create 成员函数（可能在[OnInitialUpdate](reference/cview-class.md#oninitialupdate)中），该函数可能在父窗口的[OnCreate](reference/cwnd-class.md#oncreate)处理函数 (的前提下，如果要为控件) [创建](reference/clistctrl-class.md#create)子类。 设置控件的样式。

## <a name="see-also"></a>请参阅

[使用 CListCtrl](using-clistctrl.md)<br/>
[控件](controls-mfc.md)

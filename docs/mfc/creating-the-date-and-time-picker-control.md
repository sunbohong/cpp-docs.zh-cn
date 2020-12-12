---
description: 了解详细信息：创建日期和时间选取器控件
title: 创建日期和时间选择器控件
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: 0ead228e98fdcbcfe707fee88c175453808e7047
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309727"
---
# <a name="creating-the-date-and-time-picker-control"></a>创建日期和时间选择器控件

创建日期和时间选取器控件的方式取决于您使用的是对话框中的控件，还是在非对话框窗口中创建控件。

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>直接在对话框中使用 CDateTimeCtrl

1. 在对话框编辑器中，将日期和时间选取器控件添加到对话框模板资源。 指定其控件 ID。

1. 使用 "日期和时间选择器" 控件的 "属性" 对话框指定所需的任何样式。

1. 使用 " [添加成员变量向导](../ide/adding-a-member-variable-visual-cpp.md) " 可使用 Control 属性添加类型为 [CDateTimeCtrl](reference/cdatetimectrl-class.md) 的成员变量。 您可以使用此成员调用 `CDateTimeCtrl` 成员函数。

1. 使用 [类向导](reference/mfc-class-wizard.md) 可以在对话框类中为任何日期时间选取 [器控件映射](processing-notification-messages-in-date-and-time-picker-controls.md) 处理程序函数， (请参阅将 [消息映射到](reference/mapping-messages-to-functions.md)) 的函数。

1. 在 [OnInitDialog](reference/cdialog-class.md#oninitdialog)中，为对象设置任何其他样式 `CDateTimeCtrl` 。

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>在非对话框窗口中使用 CDateTimeCtrl

1. 在视图或窗口类中声明控件。

1. 调用控件的 Create 成员函数（可能在[OnInitialUpdate](reference/cview-class.md#oninitialupdate)中），该函数可能在父窗口的[OnCreate](reference/cwnd-class.md#oncreate)处理函数 (的前提下，如果要为控件) [创建](reference/ctabctrl-class.md#create)子类。 设置控件的样式。

## <a name="see-also"></a>请参阅

[使用 CDateTimeCtrl](using-cdatetimectrl.md)<br/>
[控件](controls-mfc.md)

---
description: 了解详细信息： ActiveX 控件容器：处理 ActiveX 控件中的事件
title: ActiveX 控件容器：处理 ActiveX 控件中的事件
ms.date: 09/12/2018
helpviewer_keywords:
- event handlers [MFC], ActiveX controls
- ActiveX control containers [MFC], event sinks
- event handling [MFC], ActiveX controls
- ON_EVENT macro [MFC]
- ActiveX controls [MFC], events [MFC]
- END_EVENTSINK_MAP macro, using
- events [MFC], ActiveX controls
- BEGIN_EVENTSINK_MAP macro
ms.assetid: f9c106db-052f-4e32-82ad-750646aa760b
ms.openlocfilehash: 451061467b87df82b8bca141684ea70f222edcac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271871"
---
# <a name="activex-control-containers-handling-events-from-an-activex-control"></a>ActiveX 控件容器：处理 ActiveX 控件中的事件

本文讨论如何使用 **类视图**) 中的 "**属性**" (窗口在 activex 控件容器中安装 activex 控件的事件处理程序。 事件处理程序用于接收来自特定事件的控件) 的通知，并执行某些操作以响应 (。 此通知称为 "激发" 事件。

>[!IMPORTANT]
> ActiveX 是一种不能用于新开发的旧技术。 有关取代 ActiveX 的新式技术的详细信息，请参阅 [Activex 控件](activex-controls.md)。

> [!NOTE]
> 本文使用一个名为 Container、基于对话框的 ActiveX 控件容器项目和一个名为 Circ 的嵌入控件分别作为过程和代码中的示例。

使用 **类视图**) 中的 "**属性**" 窗口中的 "事件" 按钮，可以创建可在 ActiveX 控件容器应用程序中发生的事件的映射 (。 在将事件处理程序添加到控件容器类时，此映射称为 "事件接收器映射"，由 Visual C++ 创建和维护。 使用事件映射项实现的每个事件处理程序将一个特定事件映射到一个容器事件处理程序成员函数。 当 ActiveX 控件对象激发指定的事件时，将调用此事件处理程序函数。

有关事件接收器映射的详细信息，请参阅类库 *参考* 中的 [事件接收器映射](reference/event-sink-maps.md)。

## <a name="event-handler-modifications-to-the-project"></a><a name="_core_event_handler_modifications_to_the_project"></a> 对项目的事件处理程序修改

使用 " **属性** " 窗口添加事件处理程序时，会在项目中声明和定义事件接收器映射。 以下语句将添加到控件中。在第一次添加事件处理程序时的 CPP 文件。 此代码声明对话框类的事件接收器映射 (在本例中为 `CContainerDlg`) ：

[!code-cpp[NVC_MFC_AxCont#8](codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_1.cpp)]
[!code-cpp[NVC_MFC_AxCont#9](codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_2.cpp)]

使用 " **属性** " 窗口添加事件时，会将事件映射条目 (`ON_EVENT`) 添加到事件接收器映射，并将事件处理程序函数添加到容器的实现 (。CPP) 文件。

下面的示例 `OnClickInCircCtrl` 为 Circ 控件的事件声明一个名为的事件处理程序 `ClickIn` ：

[!code-cpp[NVC_MFC_AxCont#10](codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_3.cpp)]

此外，还会将以下模板添加到 `CContainerDlg` ( 类实现。事件处理程序成员函数的 CPP) 文件：

[!code-cpp[NVC_MFC_AxCont#11](codesnippet/cpp/activex-control-containers-handling-events-from-an-activex-control_4.cpp)]

有关事件接收器宏的详细信息，请参阅类库 *参考* 中的 [事件接收器映射](reference/event-sink-maps.md)。

#### <a name="to-create-an-event-handler-function"></a>创建事件处理程序函数

1. 在类视图中，选择包含 ActiveX 控件的对话框类。 对于本示例，请使用 `CContainerDlg` 。

1. 在 **“属性”** 窗口中，单击 **“事件”** 按钮。

1. 在 " **属性** " 窗口中，选择嵌入的 ActiveX 控件的控件 ID。 对于本示例，请使用 `IDC_CIRCCTRL1` 。

   " **属性** " 窗口显示可由嵌入 ActiveX 控件触发的事件的列表。 以粗体显示的任何成员函数都已分配有处理程序函数。

1. 选择希望对话框类处理的事件。 对于本示例，请选择 **"单击"**。

1. 从右侧的下拉列表框中，选择 " **\<Add> ClickCircctrl1**"。

1. 双击类视图的新处理程序函数，跳转到实现 ( 中的事件处理程序代码。CPP) 的文件 `CContainerDlg` 。

## <a name="see-also"></a>请参阅

[ActiveX 控件容器](activex-control-containers.md)

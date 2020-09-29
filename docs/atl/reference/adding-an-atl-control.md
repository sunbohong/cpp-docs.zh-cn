---
title: 添加 ATL 控件
ms.date: 11/04/2016
helpviewer_keywords:
- ATL projects, adding controls
- controls [ATL], adding to projects
ms.assetid: 10223e7e-fdb7-4163-80c6-44aeafa8e6ce
ms.openlocfilehash: fac1efeb3d373a8324828a8b10f0570f253f6103
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499295"
---
# <a name="adding-an-atl-control"></a>添加 ATL 控件

使用此向导可将用户界面对象添加到支持所有潜在容器的接口的项目。 若要支持这些接口，必须已将项目创建为 ATL 应用程序或包含 ATL 支持的 MFC 应用程序。 您可以使用 [Atl 项目向导](../../atl/reference/atl-project-wizard.md) 创建 atl 应用程序，或 [将 atl 对象添加到 mfc 应用](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) 程序，以便为 MFC 应用程序实现 atl 支持。

## <a name="to-add-an-atl-control-to-your-project"></a>向项目添加 ATL 控件

1. 在 " **解决方案资源管理器** " 或 " [类视图](/visualstudio/ide/viewing-the-structure-of-code)中，右键单击要向其添加 ATL 简单对象的项目的名称。

1. 在快捷菜单中单击 " **添加** "，然后单击 " **添加类**"。

1. 在 " [添加类](../../ide/adding-a-class-visual-cpp.md#add-class-dialog-box) " 对话框的 "模板" 窗格中，单击 " **atl 控件**"，然后单击 " **添加** " 以显示 [atl 控件向导](../../atl/reference/atl-control-wizard.md)。

使用 **ATL 控件向导**，你可以创建三种类型的控件之一：

- 标准控件

- 复合控件

- DHTML 控件

此外，还可以通过在向导的 "**选项**" 页上选择 "**最小控制**" 来减小控件的大小并删除大多数容器未使用的接口。

## <a name="see-also"></a>请参阅

[向复合控件添加功能](../../atl/adding-functionality-to-the-composite-control.md)<br/>
[ATL COM 对象的基本知识](../../atl/fundamentals-of-atl-com-objects.md)

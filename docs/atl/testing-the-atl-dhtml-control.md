---
description: 了解详细信息：测试 ATL DHTML 控件
title: 测试 ATL DHTML 控件
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls
- DHTML controls, testing
ms.assetid: 0e4b4358-80ce-4505-8b06-ef4f30b1d1f0
ms.openlocfilehash: d9e82b609b4bb9346f3db983e9734fd732ec422f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157329"
---
# <a name="testing-the-atl-dhtml-control"></a>测试 ATL DHTML 控件

创建项目后，可以生成并测试示例控件。 在执行此操作之前，请使用 **类视图** 和 **解决方案资源管理器** 检查项目。 [标识 DHTML 控件项目的元素](../atl/identifying-the-elements-of-the-dhtml-control-project.md)中更详细地介绍了项目的元素。

## <a name="to-build-and-test-the-atl-dhtml-control"></a>生成和测试 ATL DHTML 控件

1. 生成项目。 在“生成”菜单中，单击“生成解决方案”。

1. 生成完成后，打开 " **测试容器**"。 请参阅 [使用测试容器测试属性和事件](../mfc/testing-properties-and-events-with-test-container.md) 了解有关如何访问 **测试容器** 的信息。

1. 在 **测试容器** 的 " **编辑** " 菜单中，单击 " **插入新控件**"。

1. 在 " **插入控件** " 对话框中，从列表框中选择您的控件。 请记住，其名称基于你在 ATL 控件向导中指定的短名称。 单击 **“确定”** 。

1. 检查控件。 请注意，它具有滚动条。 使用控件的句柄来调整控件的大小以激活滚动条。

1. 测试控件的按钮。 背景色更改为按钮所指示的颜色。

1. 关闭 **测试容器**。

接下来，尝试 [修改 DHTML 控件](../atl/modifying-the-atl-dhtml-control.md)。

## <a name="see-also"></a>请参阅

[支持 DHTML 控件](../atl/atl-support-for-dhtml-controls.md)

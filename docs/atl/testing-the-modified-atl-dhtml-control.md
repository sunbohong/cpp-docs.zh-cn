---
description: 了解详细信息：测试修改的 ATL DHTML 控件
title: 测试修改的 ATL DHTML 控件
ms.date: 11/06/2018
helpviewer_keywords:
- HTML controls, testing
- testing controls
- DHTML controls, testing
ms.assetid: 42316118-9433-410f-9d8a-0efcc1eff824
ms.openlocfilehash: a797eab308ad7fb8c5c7b72566ec3d57a169370b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138328"
---
# <a name="testing-the-modified-atl-dhtml-control"></a>测试修改的 ATL DHTML 控件

试用新控件，查看其工作原理。

## <a name="to-build-and-test-the-modified-control"></a>生成并测试修改后的控件

1. 重新生成项目并在 **测试容器** 中打开它。 请参阅 [使用测试容器测试属性和事件](../mfc/testing-properties-and-events-with-test-container.md) 了解有关如何访问 **测试容器** 的信息。

   调整控件的大小以显示您添加的所有按钮。

1. 通过更改 HTML 来检查插入的两个按钮。 每个按钮都带有 [修改 ATL DHTML 控件](../atl/modifying-the-atl-dhtml-control.md)： **Refresh** 和 **HelloHTML** 中标识的标签。

1. 测试两个新按钮，了解它们的工作方式。

现在，请测试不属于用户界面的方法。

1. 突出显示控件，使边框被激活。

1. 在 " **控件** " 菜单上，选择 " **调用方法**"。

   列表中标记为 " **方法名称** " 的方法是容器可调用的方法： `MethodInvoked` 和 `GoToURL` 。 所有其他方法都由 UI 控制。

1. 选择要调用的方法，然后选择 " **调用** " 以显示该方法的消息框，或导航到 `www.microsoft.com` 。

1. 在 " **调用方法** " 对话框中，选择 " **关闭**"。

若要了解有关组成 ATL DHTML 控件的各种元素和文件的详细信息，请参阅 [标识 DHTML 控件项目的元素](../atl/identifying-the-elements-of-the-dhtml-control-project.md)。

## <a name="see-also"></a>请参阅

[支持 DHTML 控件](../atl/atl-support-for-dhtml-controls.md)

---
description: 了解详细信息：创建状态栏的方法
title: 创建状态栏的方法
ms.date: 11/04/2016
helpviewer_keywords:
- CStatusBar class [MFC], vs. CStatusBarCtrl
- methods [MFC], creating status bars
- CStatusBarCtrl class [MFC], vs. CStatusBar
- CStatusBarCtrl class [MFC], creating
- methods [MFC]
- status bars [MFC], creating
ms.assetid: 9aeaf290-7099-4762-a5ba-9c26705333c9
ms.openlocfilehash: 06ae4002fdffb8ba90964b5ef488d0c115b3a0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203050"
---
# <a name="methods-of-creating-a-status-bar"></a>创建状态栏的方法

MFC 提供了两个用于创建状态栏的类： [CStatusBar](reference/cstatusbar-class.md) 和 [CStatusBarCtrl](reference/cstatusbarctrl-class.md) (，这会包装 Windows 公共控件 API) 。 `CStatusBar` 提供状态栏公共控件的所有功能，它自动与菜单和工具栏交互，并为您处理许多必需的公共控件设置和结构。但是，生成的可执行文件通常会大于使用创建的 `CStatusBarCtrl` 。

`CStatusBarCtrl` 通常会产生较小的可执行文件， `CStatusBarCtrl` 如果不想将状态栏集成到 MFC 体系结构中，则可能更倾向于使用。 如果你计划使用 `CStatusBarCtrl` 并将状态栏集成到 mfc 体系结构中，则必须特别注意将状态栏控件操作传达给 mfc。 这种通信并不难;但是，当你使用时，它是不必要的其他工作 `CStatusBar` 。

Visual C++ 提供了两种方法来利用状态栏公共控件。

- 使用创建状态栏 `CStatusBar` ，然后调用 [CStatusBar：： GetStatusBarCtrl](reference/cstatusbar-class.md#getstatusbarctrl) 以获取对成员函数的访问权限 `CStatusBarCtrl` 。

- 使用 [CStatusBarCtrl](reference/cstatusbarctrl-class.md)的构造函数创建状态栏。

任一方法都可让你访问状态栏控件的成员函数。 当您调用 `CStatusBar::GetStatusBarCtrl` 时，它将返回对 `CStatusBarCtrl` 对象的引用，以便您可以使用成员函数集。 有关[](reference/cstatusbar-class.md)使用构造和创建状态栏的信息，请参阅 CStatusBar `CStatusBar` 。

## <a name="see-also"></a>请参阅

[使用 CStatusBarCtrl](using-cstatusbarctrl.md)<br/>
[控件](controls-mfc.md)

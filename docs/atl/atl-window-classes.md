---
description: 了解详细信息： ATL 窗口类
title: ATL 窗口类
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- windows [C++], subclassing
- windows [C++], superclassing
- windows [C++], ATL
- subclassing ATL window classes
- superclassing
- superclassing, ATL
ms.assetid: 1d12b708-de3e-49d5-9e41-42fe4769fa62
ms.openlocfilehash: e8e7b8c9d8492c133c305bf46abe493d993d398c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148546"
---
# <a name="atl-window-classes"></a>ATL 窗口类

ATL 包括几个使您可以使用和实现 windows 的类。 与其他 ATL 类相同，这些类提供了一个有效的实现，不会对代码造成开销。

本节介绍 ATL 窗口类，并说明如何使用它们。

## <a name="in-this-section"></a>本节内容

[ATL 窗口类简介](../atl/introduction-to-atl-window-classes.md)<br/>
简要描述每个 ATL 窗口类，并提供指向这些类的参考材料的链接。

[使用窗口](../atl/using-a-window.md)<br/>
讨论如何使用 `CWindow` 来操作窗口。

[实现窗口](../atl/implementing-a-window.md)<br/>
讨论消息处理程序、消息映射和使用 `CWindowImpl` 。 包含有关 superclassing 和子类的详细信息。

[实现对话框](../atl/implementing-a-dialog-box.md)<br/>
讨论添加对话框类并显示代码示例的两种方法。

[使用包含的窗口](../atl/using-contained-windows.md)<br/>
讨论 ATL 中包含的窗口，这些窗口是将消息委托给容器对象的窗口，而不是在自己的类中处理它们。

[了解窗口特性](../atl/understanding-window-traits.md)<br/>
讨论 ATL 中的窗口特征类。 这些类提供了一种简单的方法，用于标准化用于创建窗口对象的样式。

## <a name="related-sections"></a>相关章节

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
提供了关于如何使用 Active Template Library 进行编程的概念性主题的链接。

[Windows 支持类](../atl/windows-support-classes.md)<br/>
列出了在 ATL 中支持 windows 和消息映射的其他 ATL 类。

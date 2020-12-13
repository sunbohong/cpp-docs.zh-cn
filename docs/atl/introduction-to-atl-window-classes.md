---
description: 了解详细信息： ATL 窗口类简介
title: ATL 窗口类简介
ms.date: 11/04/2016
helpviewer_keywords:
- window classes
ms.assetid: 503efc2c-a269-495d-97cf-3fb300d52f3d
ms.openlocfilehash: 54a9d9764450025e51f9fac368a3434ca786fe09
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152719"
---
# <a name="introduction-to-atl-window-classes"></a>ATL 窗口类简介

以下 ATL 类旨在实现和操作 windows：

- 使用[CWindow](../atl/reference/cwindow-class.md)可以将窗口句柄附加到 `CWindow` 对象。 然后调用 `CWindow` 方法以操作窗口。

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) 允许使用消息映射实现新窗口和处理消息。 可以基于新的 Windows 类、现有类的超类或现有窗口的子类创建窗口。

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) 允许实现模式对话框或无模式对话框并使用消息映射处理消息。

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) 是一个预生成的类，用于实现其消息映射包含在另一个类中的窗口。 使用可以 `CContainedWindowT` 在一个类中集中处理消息处理。

- 使用[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)可以实现一个对话框， (承载 ActiveX 控件的模式或无模式) 。

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) 允许实现具有基本功能的模式对话框。

- [CAxWindow](../atl/reference/caxwindow-class.md) 允许实现承载 ActiveX 控件的窗口。

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) 使你能够实现一个承载授权 ActiveX 控件的窗口。

除了特定的窗口类之外，ATL 还提供了若干类，旨在简化 ATL 窗口对象的实现。 这些限制如下：

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 管理新窗口类的信息。

- [CWinTraits](../atl/reference/cwintraits-class.md) 和 [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) 提供了一种简单的方法来标准化 ATL 窗口对象的特征。

## <a name="see-also"></a>请参阅

[窗口类](../atl/atl-window-classes.md)

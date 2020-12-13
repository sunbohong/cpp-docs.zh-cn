---
description: 了解更多相关信息： Windows 支持类
title: 'Windows 支持类 (ATL) '
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
ms.openlocfilehash: c88a6ef878a428581ca090e78b2fac3b5e02131d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97138055"
---
# <a name="windows-support-classes"></a>Windows 支持类

以下类为 windows 提供支持：

- [_U_MENUorID](../atl/reference/u-menuorid-class.md) 提供和的 `CreateWindow` 包装 `CreateWindowEx` 。

- [CWindow](../atl/reference/cwindow-class.md) 包含用于操作窗口的方法。 `CWindow` 是 `CWindowImpl`、`CDialogImpl` 和 `CContainedWindow` 的基类。

- [CWindowImpl](../atl/reference/cwindowimpl-class.md) 基于新的窗口类实现窗口。 还允许您为窗口划分子类或超类。

- [CDialogImpl](../atl/reference/cdialogimpl-class.md) 实现一个对话框。

- [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) 实现一个对话框，该对话框 (承载 ActiveX 控件的模式或无模式) 。

- [CSimpleDialog](../atl/reference/csimpledialog-class.md) 使用基本功能实现 (模式或无模式) 的对话框。

- [CAxWindow](../atl/reference/caxwindow-class.md) 操作承载 ActiveX 控件的窗口。

- [CAxWindow2T](../atl/reference/caxwindow2t-class.md) 提供一些方法，这些方法用于操作承载 ActiveX 控件的窗口，并且还支持承载许可的 ActiveX 控件。

- [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) 实现一个包含在另一个对象中的窗口。

- [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) 管理新窗口类的信息。

- [CDynamicChain](../atl/reference/cdynamicchain-class.md) 支持消息映射的动态链接。

- [CMessageMap](../atl/reference/cmessagemap-class.md) 允许对象向其他对象公开其消息映射。

- [CWinTraits](../atl/reference/cwintraits-class.md) 提供了一种简单的方法来标准化 ATL 窗口对象的特征。

- [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) 提供用于创建窗口的窗口样式和扩展样式的默认值。 使用逻辑 "或" 运算符将这些值添加到创建窗口期间提供的值。

## <a name="related-articles"></a>相关文章

[ATL 窗口类](../atl/atl-window-classes.md)

[ATL 教程](../atl/active-template-library-atl-tutorial.md)

## <a name="see-also"></a>请参阅

[类概述](../atl/atl-class-overview.md)<br/>
[消息映射宏](../atl/reference/message-map-macros-atl.md)<br/>
[窗口类宏](../atl/reference/window-class-macros.md)

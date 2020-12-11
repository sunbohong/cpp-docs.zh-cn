---
description: 了解详细信息：使用窗口
title: '使用窗口 (ATL) '
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
ms.openlocfilehash: fb9f1e03a27ad8b637da30eacbd100daf920cdb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157275"
---
# <a name="using-a-window"></a>使用窗口

类 [CWindow](../atl/reference/cwindow-class.md) 允许使用窗口。 将窗口附加到 `CWindow` 对象后，可以调用 `CWindow` 方法来操作窗口。 `CWindow` 还包含将对象转换为 HWND 的 HWND 运算符 `CWindow` 。 因此，您可以将 `CWindow` 对象传递到需要窗口句柄的任何函数。 您可以轻松地混合 `CWindow` 方法调用和 Win32 函数调用，而无需创建任何临时对象。

由于 `CWindow` 只有两个数据成员 (的窗口句柄和默认维度) ，因此不会对代码造成开销。 此外，许多 `CWindow` 方法只是包装相应的 Win32 API 函数。 通过使用 `CWindow` ，HWND 成员将自动传递到 Win32 函数。

除了直接使用之外 `CWindow` ，还可以从其派生以向类添加数据或代码。 ATL 本身从 `CWindow` ： [CWindowImpl](../atl/implementing-a-window.md)、 [CDialogImpl](../atl/implementing-a-dialog-box.md)和 [CContainedWindowT](../atl/using-contained-windows.md)派生了三个类。

## <a name="see-also"></a>请参阅

[窗口类](../atl/atl-window-classes.md)

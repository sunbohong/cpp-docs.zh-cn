---
description: 了解详细信息： TN070： MFC 窗口类名称
title: TN070：MFC 窗口类名称
ms.date: 11/04/2016
helpviewer_keywords:
- window class names [MFC]
- TN070 [MFC]
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
ms.openlocfilehash: 963f343f480a5805a3c1ec3cf5499583a17535ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214515"
---
# <a name="tn070-mfc-window-class-names"></a>TN070：MFC 窗口类名称

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

MFC 窗口使用可反映窗口功能的动态创建的类名。 MFC 动态生成框架窗口、视图以及由应用程序生成的弹出式窗口的类名。 MFC 应用程序生成的对话框和控件具有上述窗口类的 Windows 提供的类名。

可以通过注册自己的窗口类并在 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)的重写中使用它来替换动态提供的类名。 其 MFC 提供的类名适合下列两种形式之一：

```
Afx:%x:%x
Afx:%x:%x:%x:%x:%x
```

替换字符的十六进制数字 `%x` 将从 [WNDCLASS](/windows/win32/api/winuser/ns-winuser-wndclassw) 结构中的数据填充。 MFC 使用此方法，以便多个需要完全相同的 **WNDCLASS** 结构的 c + + 类可以共享同一个已注册的窗口类。 与大多数简单的 Win32 应用程序不同，MFC 应用程序只有一个 **WNDPROC**，因此你可以轻松共享 **WNDCLASS** 结构以节省时间和内存。 上面显示的 `%x` 字符的可替换值如下所示：

- **WNDCLASS.hInstance**

- **WNDCLASS.style**

- **WNDCLASS.hCursor**

- **WNDCLASS.hbrBackground**

- **WNDCLASS.hIcon**

`Afx:%x:%x`当 **hCursor**、 **HbrBackground** 和 **hIcon** 均 **为 NULL** 时，将使用第一个窗体 () 。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)<br/>
[TN020： ID 命名和编号约定](../mfc/tn020-id-naming-and-numbering-conventions.md)

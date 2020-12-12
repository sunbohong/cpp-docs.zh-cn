---
description: 了解有关以下方面的详细信息：服务器：实现 In-Place 框架窗口
title: 服务器：实现就地框架窗口
ms.date: 09/09/2019
helpviewer_keywords:
- frame windows [MFC], implementing
- OLE server applications [MFC], frame windows
- servers, in-place frame windows
- frame windows [MFC], in-place
- in-place frame windows
ms.assetid: 09bde4d8-15e2-4fba-8d14-9b954d926b92
ms.openlocfilehash: 859a31bf107162aea6adb4d40ccf7b7b87f485b5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217349"
---
# <a name="servers-implementing-in-place-frame-windows"></a>服务器：实现就地框架窗口

本文介绍如果您不使用应用程序向导创建服务器应用程序，则在可视编辑服务器应用程序中实现就地框架窗口时必须执行的操作。 您可以使用应用程序向导生成的应用程序或随 Visual C++ 提供的示例中的现有就地框架窗口类，而不是按照本文中所述的过程进行操作。

#### <a name="to-declare-an-in-place-frame-window-class"></a>声明就地框架窗口类

1. 从 `COleIPFrameWnd` 派生就地框架窗口类。

   - 在类头文件中使用 DECLARE_DYNCREATE 宏。

   - 在类实现中使用 IMPLEMENT_DYNCREATE 宏 ( .cpp) 文件。 这使得此类的对象由框架创建。

1. 在框架窗口类中声明 `COleResizeBar` 成员。 这在您需要在服务器应用程序中支持就地重设大小时是必需的。

   `OnCreate`使用[类向导](reference/mfc-class-wizard.md))  (声明消息处理程序，并 `Create` 为您的成员调用（ `COleResizeBar` 如果已定义）。

1. 如果您有一个工具栏，请在框架窗口类中声明 `CToolBar` 成员。

   当服务器处于就地活动状态时，请重写 `OnCreateControlBars` 成员函数以创建工具栏。 例如：

   [!code-cpp[NVC_MFCOleServer#1](../mfc/codesnippet/cpp/servers-implementing-in-place-frame-windows_1.cpp)]

   请参阅下面步骤 5 中对此代码的讨论。

1. 在主 .cpp 文件中包含此就地框架窗口类的标头文件。

1. 在应用程序类的 `InitInstance` 中，调用文档模板对象的 `SetServerInfo` 函数以指定要在打开和就地编辑中使用的资源和就地框架窗口。

语句中的函数调用序列将 **`if`** 从服务器提供的资源创建工具栏。 此时，工具栏是容器的窗口层次结构的一部分。 由于此工具栏派生自 `CToolBar`，因此它会将其消息传递给其所有者 - 容器应用程序的框架窗口，除非您更改所有者。 这是必需调用 `SetOwner` 的原因。 此调用会将命令将发送到的窗口更改为服务器的就地框架窗口，从而使消息传递到服务器。 这使服务器响应其提供的工具栏上的操作。

工具栏位图的 ID 应与服务器应用程序中定义的其他就地资源相同。 有关详细信息，请参阅 [菜单和资源：服务器添加](../mfc/menus-and-resources-server-additions.md) 。

有关详细信息，请参阅类库 *参考* 中的 [COleIPFrameWnd](../mfc/reference/coleipframewnd-class.md)、 [COleResizeBar](../mfc/reference/coleresizebar-class.md)和 [CDocTemplate：： SetServerInfo](../mfc/reference/cdoctemplate-class.md#setserverinfo) 。

## <a name="see-also"></a>请参阅

[服务器](../mfc/servers.md)<br/>
[服务器：实现服务器](../mfc/servers-implementing-a-server.md)<br/>
[服务器：实现服务器文档](../mfc/servers-implementing-server-documents.md)<br/>
[服务器：服务器项](../mfc/servers-server-items.md)

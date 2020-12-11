---
description: 了解详细信息：拖放框架窗口中的文件
title: 拖放框架窗口中的文件
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], files
- drag and drop [MFC], File Manager
- Windows Explorer [MFC]
- File Manager drag and drop support [MFC]
- files [MFC], drag and drop
- frame windows [MFC], dragging and dropping files in
- drag and drop [MFC], Windows Explorer
ms.assetid: 85560fe9-121b-4105-bd7b-216b966e19fa
ms.openlocfilehash: dafbeca8b74ee07c80315c15ab93097977125d89
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159942"
---
# <a name="dragging-and-dropping-files-in-a-frame-window"></a>拖放框架窗口中的文件

框架窗口管理与文件资源管理器或文件管理器的关系。

通过在成员函数的重写中添加几个初始化调用 `CWinApp` `InitInstance` （如 [CWinApp：应用程序类](cwinapp-the-application-class.md)中所述），可以使框架窗口间接打开从文件资源管理器或文件管理器中拖放到框架窗口中的文件。 请参阅 [文件管理器拖放](special-cwinapp-services.md)。

## <a name="see-also"></a>请参阅

[使用框架窗口](using-frame-windows.md)

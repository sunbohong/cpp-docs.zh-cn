---
description: 了解详细信息：窗口过程入口点
title: 窗口过程入口点
ms.date: 11/04/2016
helpviewer_keywords:
- state management, window procedures
- MFC, managing state data
- window procedure entry points
- entry points, window procedures
ms.assetid: a6b46a7f-6e42-45f2-9ae6-82e19fc57148
ms.openlocfilehash: 2c2e5dc5d37a2e6f187e694d39205c4cd95b3810
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214476"
---
# <a name="window-procedure-entry-points"></a>窗口过程入口点

为了保护 MFC 窗口过程，模块将与特定窗口过程实现静态链接。 当模块与 MFC 链接时，链接操作将自动发生。 此窗口过程使用 AFX_MANAGE_STATE 宏来正确设置有效的模块状态，然后调用，进而 `AfxWndProc` 委托给 `WindowProc` 适当的派生对象的成员函数 `CWnd` 。

## <a name="see-also"></a>请参阅

[管理 MFC 模块的状态数据](../mfc/managing-the-state-data-of-mfc-modules.md)

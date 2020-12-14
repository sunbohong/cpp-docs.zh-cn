---
description: 了解更多：标准命令和窗口 Id
title: 标准命令和窗口 ID
ms.date: 11/04/2016
helpviewer_keywords:
- standard command and Window IDs
ms.assetid: 0424805c-fff8-4531-8f0c-15cfb13aa612
ms.openlocfilehash: 9f5a6b59d9451d749a48443bddf3560d2702bfe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218896"
---
# <a name="standard-command-and-window-ids"></a>标准命令和窗口 ID

Microsoft 基础类库定义了 Afxres.h 中的很多标准命令和窗口 ID。 这些 Id 最常用于资源编辑器和 [类向导](mfc-class-wizard.md) 中，用于将消息映射到处理程序函数。 所有标准命令都具有 **ID_** 前缀。 例如，使用菜单编辑器时，通常会将 "文件打开" 菜单项绑定到标准 ID_FILE_OPEN 命令 ID。

对于大多数标准命令，应用程序代码不需要引用命令 ID，因为框架本身在) 的主框架类中通过消息映射来处理命令 (`CWinThread` 、、、 `CWinApp` `CView` `CDocument` 等。

除了标准命令 Id 以外，还定义了其他一些标准 Id，这些 Id 具有 **AFX_ID** 的前缀。 这些 Id 包括标准窗口 Id (前缀      **AFX_IDW_**) 、字符串 id (前缀 **AFX_IDS_**) 和其他一些类型。

程序员很少使用以 **AFX_ID** 前缀开头的 id，但在重写同时引用 **AFX_ID** 的框架函数时，可能需要引用这些 id。

ID 在此引用中不单独记录。 有关详细信息，请查看技术说明 [20](../../mfc/tn020-id-naming-and-numbering-conventions.md)、 [21](../../mfc/tn021-command-and-message-routing.md)和 [22](../../mfc/tn022-standard-commands-implementation.md)中的详细信息。

> [!NOTE]
> 标头文件 Afxres.h 间接包含在 Afxwin.h 中。 您必须将以下语句显式包含在应用程序的资源脚本 (.rc) 文件中：

[!code-cpp[NVC_MFC_Utilities#47](../../mfc/codesnippet/cpp/standard-command-and-window-ids_1.h)]

## <a name="see-also"></a>请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)

---
description: 了解详细信息：命令 Id
title: 命令 ID
ms.date: 11/04/2016
helpviewer_keywords:
- command IDs, MFC
- command IDs
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
ms.openlocfilehash: bba3b8b342b4d2e0c9492f9d0f3100a5d8f9e7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159981"
---
# <a name="command-ids"></a>命令 ID

命令只通过其命令 ID 进行完全描述， (在 **WM_COMMAND** message) 中进行编码。 此 ID 分配给生成命令的用户界面对象。 通常，Id 是为其分配到的用户界面对象的功能命名的。

例如，可以为 "编辑" 菜单中的 "全部清除" 项分配 ID，如 **ID_EDIT_CLEAR_ALL**。 类库预定义一些 Id，特别是对于框架处理自身的命令，例如 **ID_EDIT_CLEAR_ALL** 或 **ID_FILE_OPEN**。 你将自行创建其他命令 Id。

在 "Visual C++ 菜单编辑器" 中创建自己的菜单时，最好遵循类库的命名约定，如 **ID_FILE_OPEN** 所示。 [标准命令](standard-commands.md) 说明类库定义的标准命令。

## <a name="see-also"></a>请参阅

[用户界面对象和命令 Id](user-interface-objects-and-command-ids.md)

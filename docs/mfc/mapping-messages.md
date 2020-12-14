---
description: 了解详细信息：映射消息
title: 映射消息
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], about message maps
- mappings [MFC], commands
- commands [MFC], mapping
- command mapping [MFC]
- message handling [MFC], connecting to handler functions
- commands [MFC], connecting to handler functions
- mappings [MFC], messages
- messages [MFC], mapping
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
ms.openlocfilehash: 34d100a7ae527acc9f5520474e75b486b2f6276c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280789"
---
# <a name="mapping-messages"></a>映射消息

每个可以接收消息或命令的框架类都有自己的“消息映射”。 框架使用消息映射来将消息和命令连接到其处理程序函数。 派生自类 `CCmdTarget` 的所有类都可拥有消息映射。 其他文章详细解释了消息映射并说明了其使用方式。

尽管名称为 "消息映射"，但消息映射会同时处理消息和命令（ [消息类别](message-categories.md)中列出的所有三类消息。

## <a name="see-also"></a>请参阅

[框架中的消息和命令](messages-and-commands-in-the-framework.md)

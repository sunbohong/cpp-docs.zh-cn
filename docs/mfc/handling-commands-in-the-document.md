---
description: 了解有关以下内容的详细信息：处理文档中的命令
title: 处理文档中的命令
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: 4d8252cb16eee0e1c5c802e5839ec925a7879cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248887"
---
# <a name="handling-commands-in-the-document"></a>处理文档中的命令

您的文档类还可以处理由菜单项、工具栏按钮或快捷键生成的某些命令。 默认情况下， `CDocument` 使用序列化处理 "文件" 菜单上的 "保存" 和 "另存为" 命令。 其他影响数据的命令也可能由文档的成员函数处理。 例如，在自由曲线程序中，class `CScribDoc` 为 "编辑全部清除" 命令提供了一个处理程序，用于删除当前存储在文档中的所有数据。 文档可以具有消息映射，但与视图不同，文档无法处理标准 Windows 消息，只会 **WM_COMMAND** 消息或 "命令"。

## <a name="see-also"></a>请参阅

[使用文档](using-documents.md)

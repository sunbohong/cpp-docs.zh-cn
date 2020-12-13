---
description: 了解详细信息： NMAKE 错误 U1056
title: NMAKE 错误 U1056
ms.date: 11/04/2016
f1_keywords:
- U1056
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
ms.openlocfilehash: beb7814d2e29665e1f92c7ef1e8dadbd66af5d63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330373"
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE 错误 U1056

无法找到命令处理器

命令处理程序不在 **COMSPEC** 或 **path** 环境变量中指定的路径中。

执行命令时，NMAKE 使用 COMMAND.COM 或 CMD.EXE 作为命令处理器。 它首先在 **COMSPEC** 中设置的路径中查找命令处理器。 如果 **COMSPEC** 不存在，NMAKE 会搜索 **PATH** 中指定的目录。

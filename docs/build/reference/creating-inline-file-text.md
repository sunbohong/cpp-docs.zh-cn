---
description: 了解详细信息：创建内联文件文本
title: 创建内联文件文本
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: 849273fff4ca0853e4589a38096cbb067c380aae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196849"
---
# <a name="creating-inline-file-text"></a>创建内联文件文本

内联文件是临时的或永久的。

## <a name="syntax"></a>语法

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>备注

在命令后的第一行中指定 *inlinetext* 。 用双尖括号标记结尾 ( # A2) 在单独行的开头。 此文件包含分隔括号前面的所有 *inlinetext* 。 *Inlinetext* 可以具有宏展开和替换，但不能包含指令或生成文件注释。 空格、制表符和换行符按原义处理。

临时文件在会话期间存在，并可由其他命令重复使用。 指定在右尖括号 **后面保留，** 以在 NMAKE 会话后保留文件;未命名的文件将保留在磁盘上，并生成文件名。 为临时文件指定 **NOKEEP** 或 nothing。 **KEEP** 和 **NOKEEP** 不区分大小写。

## <a name="see-also"></a>请参阅

[生成文件中的内联文件](inline-files-in-a-makefile.md)

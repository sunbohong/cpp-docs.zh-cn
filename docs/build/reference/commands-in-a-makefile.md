---
description: 了解有关以下内容的详细信息：生成文件中的命令
title: 生成文件中的命令
ms.date: 11/04/2016
helpviewer_keywords:
- commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
ms.openlocfilehash: a4f3c6d3cc9b5d567548d7b3f2bd7679d492ebf0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179078"
---
# <a name="commands-in-a-makefile"></a>生成文件中的命令

描述块或推理规则指定在依赖项过期时要运行的命令块。 在运行命令之前，NMAKE 显示每个命令，除非/S **。无提示**， **！使用 CMDSWITCHES** 或 \@ 。 如果说明块后面没有命令块，NMAKE 将查找匹配推理规则。

命令块包含一个或多个命令，每个命令都在其自己的行上。 依赖项或规则与命令块之间不能出现空行。 但是，只包含空格或制表符的行可以显示;该行被解释为 null 命令，不发生错误。 在命令行之间允许使用空行。

命令行以一个或多个空格或制表符开头。 后跟换行符的反斜杠 ( \ ) 在命令中被解释为空格;在行尾使用反斜杠将命令继续到下一行。 如果有任何其他字符（包括空格或制表符）跟随反斜杠，NMAKE 会按字面解释反斜杠。

前面带有分号 (; ) 可以出现在依赖项行或推理规则上，不管命令块是否如下：

```
project.obj : project.c project.h ; cl /c project.c
```

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

[命令修饰符](command-modifiers.md)

[文件名部分语法](filename-parts-syntax.md)

[生成文件中的内联文件](inline-files-in-a-makefile.md)

## <a name="see-also"></a>请参阅

[NMAKE 参考](nmake-reference.md)

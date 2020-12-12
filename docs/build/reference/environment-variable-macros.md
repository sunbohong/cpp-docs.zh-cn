---
description: 了解详细信息： Environment-Variable 宏
title: 环境变量宏
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
ms.openlocfilehash: b7beaf8f3e98ea7447d798041f7531ed5da671ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192585"
---
# <a name="environment-variable-macros"></a>环境变量宏

NMAKE 继承会话开始之前存在的环境变量的宏定义。 如果变量是在操作系统环境中设置的，则可将其作为 NMAKE 宏提供。 继承的名称将转换为大写。 在预处理之前发生继承。 使用/E 选项可使从环境变量继承的宏替代生成文件中具有相同名称的任何宏。

环境变量宏可在会话中重新定义，这将更改相应的环境变量。 还可以通过 SET 命令更改环境变量。 不过，使用 SET 命令更改会话中的环境变量不会更改对应的宏。

例如：

```
PATH=$(PATH);\nonesuch

all:
    echo %%PATH%%
```

在此示例中，更改 `PATH` 了相应的环境变量， `PATH` 并将其附加 `\nonesuch` 到你的路径。

如果环境变量定义为在生成文件中语法不正确的字符串，则不会创建宏，也不会生成任何警告。 如果变量的值包含美元符号 ($) ，NMAKE 会将其解释为宏调用的开头。 使用宏可能导致意外的行为。

## <a name="see-also"></a>请参阅

[特殊 NMAKE 宏](special-nmake-macros.md)

---
description: 了解详细信息： Module-Definition 语句的规则
title: 模块定义语句的规则
ms.date: 11/04/2016
f1_keywords:
- .def
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
ms.openlocfilehash: bca1f279a9a93690edeaabc2264d1cfe869b3e80
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224993"
---
# <a name="rules-for-module-definition-statements"></a>模块定义语句的规则

以下语法规则适用于 .def 文件中的所有语句。 适用于特定语句的其他规则与每个语句一起介绍。

- 语句、属性关键字和用户指定的标识符区分大小写。

- 长文件名包含空格或分号 (; ) 必须用引号括起来 ( ") 。

- 使用一个或多个空格、制表符或换行符将语句关键字与参数隔开，并将语句彼此分开。 冒号 (：指定参数的 ) 或等号 (=) 用零个或多个空格、制表符或换行符括起来。

- 如果使用了 **NAME** 或 **LIBRARY** 语句，则必须在所有其他语句之前。

- **节** 和 **导出** 语句可以在 .def 文件中多次出现。 每个语句可以采用多个规范，必须用一个或多个空格、制表符或换行符分隔。 语句关键字必须在第一个规范之前出现一次，并且可以在每个附加规范之前重复。

- 许多语句具有等效的链接命令行选项。 有关更多详细信息，请参阅相应链接选项的说明。

- .Def 文件中的注释由分号 (; 每个注释行的开头 ) 指定。 注释不能与语句共享一行，但它可以在多行语句中的规范之间出现。  (**节** 和 **导出** 为多行语句。 ) 

- 用基数10或十六进制指定数值参数。

- 如果字符串参数与 [保留字](reserved-words.md)匹配，则必须用双引号将其引起来 ( ") 。

## <a name="see-also"></a>请参阅

[模块定义 (。.Def) 文件](module-definition-dot-def-files.md)

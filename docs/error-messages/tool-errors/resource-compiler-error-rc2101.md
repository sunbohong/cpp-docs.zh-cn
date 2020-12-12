---
description: 了解更多：资源编译器错误 RC2101
title: 资源编译器错误 RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: bed2490f48f40c94724fa249f7722a290cf8d9b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164128"
---
# <a name="resource-compiler-error-rc2101"></a>资源编译器错误 RC2101

预处理后的 RC 文件中的指令无效

资源编译器文件包含 **#pragma** 指令。

将 **#ifndef** 预处理器指令与资源编译器在处理包含文件时定义的 RC_INVOKED 常数一起使用。 将 **#pragma** 指令放在定义 RC_INVOKED 常数时未处理的代码块中。 块中的代码仅由 C/c + + 编译器处理，而不是由资源编译器处理。 下面的示例代码演示了此方法：

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** 预处理器指令在中没有意义。RC 文件。 **#Include** 预处理器指令经常在中使用。RC 文件以包含头文件 (Microsoft 提供的基于项目的自定义标头文件或标准头文件，其中一项产品) 。 其中一些包含文件包含 **#pragma** 指令。 因为标头文件可以包含一个或多个其他标头文件，所以包含有问题的 **#pragma** 指令的文件可能不会立即被察觉。

**#Ifndef** RC_INVOKED 技术可以控制在基于项目的头文件中包含头文件。

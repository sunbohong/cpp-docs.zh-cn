---
description: 了解详细信息：生成文件预处理中的表达式
title: 生成文件预处理中的表达式
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
ms.openlocfilehash: 9b30900db493a2a87e0527e6f3c062185bb4ab43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200788"
---
# <a name="expressions-in-makefile-preprocessing"></a>生成文件预处理中的表达式

**！如果** 或 **！否则，如果** `constantexpression` 包含整数常量，则 (以十进制或 C 语言表示法) 、字符串常量或命令。 使用括号将表达式分组。 表达式使用 C 样式的带符号长整数算法;数字采用32位的补码形式，范围为-2147483648 到2147483647。

表达式可以使用作用于常量值的运算符，从命令、字符串、宏和文件系统路径中退出代码。

## <a name="what-do-you-want-to-know-more-about"></a>你想进一步了解什么？

[生成文件预处理运算符](makefile-preprocessing-operators.md)

[在预处理中执行程序](executing-a-program-in-preprocessing.md)

## <a name="see-also"></a>请参阅

[生成文件预处理](makefile-preprocessing.md)

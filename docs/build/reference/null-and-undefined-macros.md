---
description: 了解更多： Null 和未定义的宏
title: null 宏和未定义的宏
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
ms.openlocfilehash: 639afda727f1ebb1f4d7d602ed7cf01d6c914a33
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209719"
---
# <a name="null-and-undefined-macros"></a>null 宏和未定义的宏

Null 和未定义的宏均展开为空字符串，但在预处理表达式中考虑定义为空字符串的宏。 若要将宏定义为空字符串，请在命令行或命令文件中的等号 (=) 后面不指定空格或制表符，并将 null 字符串或定义括在双引号 ( "" ) 。 若要取消定义宏，请使用 **！UNDEF。** 有关详细信息，请参阅 [Makefile 预处理指令](makefile-preprocessing-directives.md)。

## <a name="see-also"></a>请参阅

[定义 NMAKE 宏](defining-an-nmake-macro.md)

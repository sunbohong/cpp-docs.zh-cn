---
description: 了解详细信息：定义宏的位置
title: 定义宏的位置
ms.date: 11/04/2016
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
ms.openlocfilehash: b5fc7d6e1fd8247816993929791bf734596d00e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259196"
---
# <a name="where-to-define-macros"></a>定义宏的位置

在命令行、命令文件、生成文件或 Tools.ini 文件中定义宏。

在生成文件或 Tools.ini 文件中，每个宏定义都必须出现在单独的行上，并且不能以空格或制表符开头。将忽略等号周围的空格或制表符。 所有 [字符串字符](defining-an-nmake-macro.md) 都是文本，包括环绕引号和嵌入空格。

在命令行或命令文件中，空格和制表符分隔参数，不能用等号括起来。 如果 `string` 有嵌入的空格或制表符，请将字符串本身或整个宏用双引号引起来， ( "" ) 。

## <a name="see-also"></a>请参阅

[定义 NMAKE 宏](defining-an-nmake-macro.md)

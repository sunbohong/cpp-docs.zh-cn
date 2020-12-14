---
description: 了解详细信息：生成文件中的特殊字符
title: 生成文件中的特殊字符
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, special characters
- makefiles, special characters
- special characters, in NMAKE macros
- macros, special characters
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
ms.openlocfilehash: 22b8f6dd82191c88a23eaf1dabb551d468293a42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224668"
---
# <a name="special-characters-in-a-makefile"></a>生成文件中的特殊字符

若要将 NMAKE 特殊字符用作文字字符，请在该字符前面放置一个插入符号 (^) 。 NMAKE 忽略在其他字符之前的插入符号。 特殊字符为：

`:  ;  #  (  )  $  ^  \  {  }  !  @  —`

带引号的字符串内的插入符号 (^) 被视为文本插入符号字符。 行末尾的插入符号在字符串或宏中插入文本换行符。

在宏中， \\) 后跟换行符的反斜杠 (将替换为空格。

在命令中，百分比符号 (% ) 为文件说明符。 若要在命令中按原义表示%，请指定一个双百分号 (%% ) 替换单个命令。 在其他情况下，NMAKE 会按原义解释单个%，但它始终将双精度百分比解释为单个%。 因此，若要表示文本%%，请指定三个百分号、%%% 或四个百分号，%%%%。

若要在命令中使用美元符号 ($) 作为文本字符，请指定两个美元符号 ($ $) 。 此方法还可以在 ^ $ works 的其他情况下使用。

## <a name="see-also"></a>请参阅

[生成文件的内容](contents-of-a-makefile.md)

---
description: 了解更多：宏中的特殊字符
title: 宏内的特殊字符
ms.date: 11/04/2016
helpviewer_keywords:
- special characters, in NMAKE macros
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
ms.openlocfilehash: 569aedbc474f660894b723f9356355e2360a4e61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224655"
---
# <a name="special-characters-in-macros"></a>宏内的特殊字符

在定义指定注释后，数字符号 ( # ) 。 若要在宏中指定文本数字符号，请使用 ^)  (^，如 ^ # 中所示。

美元符号 ($) 指定宏调用。 若要指定文本 $，请使用 $ $。

若要将定义扩展到新行，请用反斜杠结束行 (\\) 。 调用宏时，反斜杠和换行符被替换为空格。 若要在行尾指定一个文本反斜杠，请在其前面加上一个插入符号 (^) ，或在其后面跟上注释说明符 ( # ) 。

若要指定文本换行字符，请使用插入符号 (^) 结束行，如下所示：

```
CMDS = cls^
dir
```

## <a name="see-also"></a>请参阅

[定义 NMAKE 宏](defining-an-nmake-macro.md)

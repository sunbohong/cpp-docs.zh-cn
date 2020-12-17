---
description: 详细了解：字符序列
title: 字符序列
ms.date: 11/04/2016
ms.assetid: 1e6961a9-150e-4c13-b427-9af4b6a1fb7a
ms.openlocfilehash: ac5642371389047bd8ce3a83e02dc13802167dc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305073"
---
# <a name="character-sequences"></a>字符序列

**ANSI 3.8.2** 源文件字符序列的映射

预处理器语句使用的字符集和源文件语句相同，只不过转义序列不受支持。

因此，若要指定包含文件的路径，请仅使用一个反斜杠：

```
#include "path1\path2\myfile"
```

在源代码中，需要两个反斜杠：

```
fil = fopen( "path1\\path2\\myfile", "rt" );
```

## <a name="see-also"></a>请参阅

[预处理指令](../c-language/preprocessing-directives.md)

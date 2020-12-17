---
description: 详细了解：读取范围
title: 读取范围
ms.date: 11/04/2016
ms.assetid: 99de29ce-ab14-46f4-97e1-2081fd996b53
ms.openlocfilehash: afb1ff0f25360de7c47663279bf6f54dd7ca6a48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309116"
---
# <a name="reading-ranges"></a>读取范围

**ANSI 4.9.6.2**：短划线 (-) 字符的解释，该字符既不是 `fscanf` 函数的 % [ 转换的扫描表中的第一个字符，也不是该表中的最后一个字符

下面的行

```
fscanf( fileptr, "%[A-Z]", strptr);
```

将 A-Z 范围内的任意数目的字符读取到 `strptr` 指向的字符串中。

## <a name="see-also"></a>请参阅

[库函数](../c-language/library-functions.md)

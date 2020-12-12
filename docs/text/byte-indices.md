---
description: 了解详细信息：字节索引
title: 字节索引
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 5ee4b2cb8611893c71f5c6597e619cc73e2848ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187554"
---
# <a name="byte-indices"></a>字节索引

使用以下提示：

- 在字符串中使用 bytewise 索引会引发类似于指针操作所引起的问题。 请考虑以下示例，该示例将扫描字符串以查找反斜杠字符：

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   这可能会索引尾字节，而不是前导字节，因此它可能不指向 `character` 。

- 使用 [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) 函数解决上述问题：

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   此索引会正确地索引到前导字节，因此是 `character` 。 `_mbclen`函数确定字符的大小 (1 或2字节) 。

## <a name="see-also"></a>请参阅

[MBCS 编程提示](../text/mbcs-programming-tips.md)<br/>
[字符串中的最后一个字符](../text/last-character-in-a-string.md)

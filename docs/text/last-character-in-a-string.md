---
description: 了解更多：字符串中的最后一个字符
title: 字符串中的最后一个字符
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 10ab90614509508b9667c29ccf166ddaf784a92e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207236"
---
# <a name="last-character-in-a-string"></a>字符串中的最后一个字符

使用以下提示：

- 在许多情况下，尾字节范围重叠 ASCII 字符集。 对于 (小于 32) 的任何控制字符，可以安全地使用 bytewise 扫描。

- 请考虑以下代码行，这可能会检查字符串中的最后一个字符是否是反斜杠字符：

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   由于不 `strlen` 能识别 MBCS，因此它将返回多字节字符串中的字节数，而不是字符数。 另请注意，在某些代码页中 (932，例如) ，" \\ " (0x5c) 是有效的尾字节 (`sz` 是一个 C 字符串) 。

   一种可能的解决方案是以这种方式重写代码：

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   此代码使用 MBCS 函数 `_mbsrchr` 和 `_mbsinc` 。 由于这些函数可识别 MBCS，因此它们可以区分 " \\ " 字符和尾字节 " \\ "。 如果字符串中的最后一个字符为 null ( "\ 0" ) ，则代码会执行一些操作。

## <a name="see-also"></a>请参阅

[MBCS 编程提示](../text/mbcs-programming-tips.md)<br/>
[字符赋值](../text/character-assignment.md)

---
description: 了解详细信息：递增和递减指针
title: 递增和递减指针
ms.date: 11/04/2016
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
ms.openlocfilehash: 3c333c11c5a0b68bf013dbd374eb1cc4e5f00abc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207314"
---
# <a name="incrementing-and-decrementing-pointers"></a>递增和递减指针

使用以下提示：

- 指向前导字节，而不是尾字节。 具有指向尾字节的指针通常是不安全的。 通常，向前扫描字符串而不是相反。

- 有指针增量/减量函数和宏可用于整个字符：

    ```cpp
    sz1++;
    ```

    变为：

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc`和 `_mbsdec` 函数以单元的方式正确递增和递减 `character` ，而不考虑字符大小。

- 对于减量，需要一个指向字符串开头的指针，如下所示：

    ```cpp
    sz2--;
    ```

    变为：

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   或者，头指针可能是字符串中的有效字符，例如：

    ```cpp
    sz2Head < sz2
    ```

   您必须具有指向已知的有效前导字节的指针。

- 为了更快地调用，你可能需要维护一个指向前一个字符的指针 `_mbsdec` 。

## <a name="see-also"></a>请参阅

[MBCS 编程提示](../text/mbcs-programming-tips.md)<br/>
[字节索引](../text/byte-indices.md)

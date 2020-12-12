---
description: 了解更多相关信息：字符比较
title: 字符比较
ms.date: 11/04/2016
helpviewer_keywords:
- comparing characters
- MBCS [C++], character comparison
- characters [C++], comparing
ms.assetid: 18846e44-3e6e-40c4-9b42-3153fb15db20
ms.openlocfilehash: 0e00e087074a70145f1a73694293edc3c522d69f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297000"
---
# <a name="character-comparison"></a>字符比较

使用以下提示：

- 将已知前导字节与 ASCII 字符进行比较可以正常工作：

    ```cpp
    if( *sz1 == 'A' )
    ```

- 比较两个未知字符需要使用 Mbstring.h 中定义的其中一个宏：

    ```cpp
    if( !_mbccmp( sz1, sz2) )
    ```

   这可确保比较双字节字符的两个字节是否相等。

## <a name="see-also"></a>请参阅

[MBCS 编程提示](../text/mbcs-programming-tips.md)<br/>
[缓冲区溢出](../text/buffer-overflow.md)

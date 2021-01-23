---
description: 详细了解 pragma Microsoft c/c + + 中的 strict_gs_check 指令
title: strict_gs_check pragma
ms.date: 01/22/2021
f1_keywords:
- strict_gs_check
- strict_gs_check_CPP
helpviewer_keywords:
- strict_gs_check pragma
- pragma, strict_gs_check
no-loc:
- pragma
ms.openlocfilehash: 4a224c42dc30227e5bd9a7142c807f7cebc34614
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713150"
---
# <a name="strict_gs_check-no-locpragma"></a>`strict_gs_check` pragma

这 pragma 提供了增强的安全检查。

## <a name="syntax"></a>语法

> **`#pragma strict_gs_check(`** [ **`push,`** ] { **`on`** | **`off`** } **`)`**\
> **`#pragma strict_gs_check( pop )`**

## <a name="remarks"></a>注解

指示编译器在函数堆栈中插入随机 Cookie 以帮助检测基于堆栈的缓冲区溢出的某些类别。 默认情况下， **`/GS`** 编译器选项不为所有函数插入 cookie。 有关详细信息，请参阅[ `/GS` (缓冲区安全检查) ](../build/reference/gs-buffer-security-check.md)。

使用进行编译， **`/GS`** 启用 **`strict_gs_check`** 。

pragma在公开给可能有害的数据的代码模块中使用此代码。 **`strict_gs_check`** 非常 pragma 有效，适用于可能不需要这种防御的函数，但经过了优化，可以最大程度地降低其对生成的应用程序性能的影响。

即使使用这种情况 pragma ，也应该尽力编写安全的代码。 也就是说，请确保代码没有缓冲区溢出。 **`strict_gs_check`** 可能会保护应用程序不受代码中保留的缓冲区溢出的保护。

## <a name="example"></a>示例

在此示例中，当我们将数组复制到本地数组时，会发生缓冲区溢出。 使用编译此代码时 **`/GS`** ，不会在堆栈中插入 cookie，因为数组数据类型是一个指针。 添加将 **`strict_gs_check`** pragma 强制堆栈 cookie 进入函数堆栈中。

```cpp
// pragma_strict_gs_check.cpp
// compile with: /c

#pragma strict_gs_check(on)

void ** ReverseArray(void **pData,
                     size_t cData)
{
    // **_ This buffer is subject to being overrun!! _*_
    void _pReversed[20];

    // Reverse the array into a temporary buffer
    for (size_t j = 0, i = cData; i ; --i, ++j)
        // *** Possible buffer overrun!! ***
            pReversed[j] = pData[i];

    // Copy temporary buffer back into input/output buffer
    for (size_t i = 0; i < cData ; ++i)
        pData[i] = pReversed[i];

    return pData;
}
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)\
[`/GS` (缓冲区安全检查) ](../build/reference/gs-buffer-security-check.md)

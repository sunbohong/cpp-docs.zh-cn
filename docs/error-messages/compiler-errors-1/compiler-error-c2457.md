---
description: 了解更多：编译器错误 C2457
title: 编译器错误 C2457
ms.date: 11/04/2016
f1_keywords:
- C2457
helpviewer_keywords:
- C2457
ms.assetid: 347e169d-23ad-434f-8836-5b09b53980ff
ms.openlocfilehash: 1fea5192b97e280a38f674a67b0bf739041ffe97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332368"
---
# <a name="compiler-error-c2457"></a>编译器错误 C2457

> "*宏*"：预定义的宏不能出现在函数体的外部

尝试在全局空间中使用预定义的宏，如 [&#95;&#95;函数&#95;&#95;](../../preprocessor/predefined-macros.md)。

## <a name="example"></a>示例

下面的示例生成 C2457，并显示正确的用法：

```cpp
// C2457.cpp
#include <stdio.h>

__FUNCTION__;   // C2457, cannot be global

int main()
{
    printf_s("\n%s", __FUNCTION__);   // OK
}
```

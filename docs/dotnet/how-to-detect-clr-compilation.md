---
description: 了解详细信息：如何：检测/clr 编译
title: 如何：检测-clr 编译
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, detecting /clr
- /clr compiler option [C++], detecting use of
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
ms.openlocfilehash: 25cd241a08f79bcae629c05fb3c7982a387120ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175711"
---
# <a name="how-to-detect-clr-compilation"></a>如何：检测 /clr 编译

使用 `_MANAGED` 或 `_M_CEE` 宏查看是否使用 **/clr** 编译模块。 有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)。

有关宏的详细信息，请参阅 [预定义的宏](../preprocessor/predefined-macros.md)。

## <a name="example"></a>示例

```cpp
// detect_CLR_compilation.cpp
// compile with: /clr
#include <stdio.h>

int main() {
   #if (_MANAGED == 1) || (_M_CEE == 1)
      printf_s("compiling with /clr\n");
   #else
      printf_s("compiling without /clr\n");
   #endif
}
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)

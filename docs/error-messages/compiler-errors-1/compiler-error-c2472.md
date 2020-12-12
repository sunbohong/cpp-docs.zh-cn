---
description: 了解更多：编译器错误 C2472
title: 编译器错误 C2472
ms.date: 11/04/2016
f1_keywords:
- C2472
helpviewer_keywords:
- C2472
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
ms.openlocfilehash: a1d4d668c1e7151771a2df85e888384c6c3ea028
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164492"
---
# <a name="compiler-error-c2472"></a>编译器错误 C2472

> 无法在托管代码中生成 "*function*"： "*message*";使用/clr 进行编译以生成混合映像

## <a name="remarks"></a>备注

当在纯公共语言运行库 (CLR) 环境中使用托管代码不支持的类型时，将出现此错误。 请使用 **/clr** 进行编译以解决该错误。

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

## <a name="example"></a>示例

下面的示例生成 C2472。

```cpp
// C2472.cpp
// compile with: /clr:pure
// C2472 expected

#include <cstdlib>

int main()
{
   int * __ptr32 p32;
   int * __ptr64 p64;

   p32 = (int * __ptr32)malloc(4);
   p64 = p32;
}
```

## <a name="see-also"></a>请参阅

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

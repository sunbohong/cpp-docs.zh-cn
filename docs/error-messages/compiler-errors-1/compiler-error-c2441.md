---
description: 了解更多：编译器错误 C2441
title: 编译器错误 C2441
ms.date: 11/04/2016
f1_keywords:
- C2441
helpviewer_keywords:
- C2441
ms.assetid: ffbd6573-777a-48dd-892f-5cf4a758dcab
ms.openlocfilehash: d7a6073be821fcd2717caae258c5b3f397fb3f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189725"
---
# <a name="compiler-error-c2441"></a>编译器错误 C2441

> "*variable*"：使用 __declspec (处理) 声明的符号必须是/clr： pure 模式中的常量

## <a name="remarks"></a>备注

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

默认情况下，变量位于 **/clr： pure** 下的每个应用程序域中。 `__declspec(process)`如果在一个应用程序域中修改并读取另一个应用程序域中的，则在 **/clr： pure** 下标记的变量容易出现错误。

因此，编译器强制每个进程变量 **`const`** 在 **/clr： pure** 下，使其仅在所有应用程序域中都是只读的。

有关详细信息，请参阅 [process](../../cpp/process.md) and [/Clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="example"></a>示例

下面的示例生成 C2441。

```cpp
// C2441.cpp
// compile with: /clr:pure /c
__declspec(process) int i;   // C2441
__declspec(process) const int j = 0;   // OK
```

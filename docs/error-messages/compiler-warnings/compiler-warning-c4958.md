---
description: 了解更多：编译器警告 C4958
title: 编译器警告 C4958
ms.date: 11/04/2016
f1_keywords:
- C4958
helpviewer_keywords:
- C4958
ms.assetid: e79b9e9c-d572-4a3a-a3b6-60962b70864a
ms.openlocfilehash: 1a6260a441b619923e8c2ddf8c7a5d891a3c3844
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314797"
---
# <a name="compiler-warning-c4958"></a>编译器警告 C4958

> "*operation*"：指针算法是不可验证的

## <a name="remarks"></a>备注

使用指针算法将产生不可验证的映像。

有关详细信息，请参阅 [纯代码和可验证代码 (c + +/cli) ](../../dotnet/pure-and-verifiable-code-cpp-cli.md)。

**/Clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

此警告作为错误发出，可通过 [warning](../../preprocessor/warning.md) 杂注或 [/wd](../../build/reference/compiler-option-warning-level.md) 编译器选项禁用该警告。

## <a name="example"></a>示例

下面的示例生成 C4958：

```cpp
// C4958.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )
using namespace System;

int main( ) {
   Int32 arr[] = new Int32[10];
   Int32* p = &arr[0];
   p++;   // C4958
}
```

编译器使用指针算法实现数组操作。 因此，不可验证本机数组；请改用 CLR 数组。 有关详细信息，请参阅 [数组](../../extensions/arrays-cpp-component-extensions.md)。

下面的示例生成 C4958：

```cpp
// C4958b.cpp
// compile with: /clr:safe
// #pragma warning( disable : 4958 )

int main() {
   int array[5];
   array[4] = 0;   // C4958
}
```

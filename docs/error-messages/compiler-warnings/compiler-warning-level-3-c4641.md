---
description: 详细了解：编译器警告 (等级 3) C4641
title: 编译器警告（等级 3）C4641
ms.date: 11/04/2016
f1_keywords:
- C4641
helpviewer_keywords:
- C4641
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
ms.openlocfilehash: 4b1111075b4cf375ef102899f0971773080f33ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332171"
---
# <a name="compiler-warning-level-3-c4641"></a>编译器警告（等级 3）C4641

XML 文档注释含有不明确的交叉引用。

编译器无法明确解析引用。 若要解决此警告，请指定使引用明确所需的参数信息。

有关更多信息，请参见 [XML Documentation](../../build/reference/xml-documentation-visual-cpp.md)。

## <a name="example"></a>示例

下面的示例生成 C4641。

```cpp
// C4641.cpp
// compile with: /W3 /doc /clr /c

/// <see cref="f" />   // C4641
// try the following line instead
// /// <see cref="f(int)" />
public ref class GR {
public:
   void f( int ) {}
   void f( char ) {}
};
```

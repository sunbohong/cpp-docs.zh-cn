---
description: 了解更多：编译器错误 C2261
title: 编译器错误 C2261
ms.date: 11/04/2016
f1_keywords:
- C2261
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
ms.openlocfilehash: c5156a240696f9021613b54cf7013e9372a13b45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134610"
---
# <a name="compiler-error-c2261"></a>编译器错误 C2261

"string"：程序集引用无效且无法解析

值无效。

<xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 用于指定友元程序集。 例如，如果 a.dll 想要将 b.dll 指定为友元程序集，则需要在 a.dll) ： InternalsVisibleTo ( "b" ) 中指定 (。 然后，运行时允许 b.dll 访问 a.dll (除了私有类型) 以外的所有内容。

有关指定友元程序集时的正确语法的详细信息，请参阅 [友元程序集 (c + +) ](../../dotnet/friend-assemblies-cpp.md)。

## <a name="example"></a>示例

下面的示例生成 C2261。

```cpp
// C2261.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("a,a,a")];   // C2261
[assembly: InternalsVisibleTo("a.a")];   // OK
[assembly: InternalsVisibleTo("a")];   // OK
```

---
description: 了解详细信息： how to：指定 out 参数
title: 如何：指定 out 参数
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- function parameters
- out parameters
ms.assetid: 02862448-603c-4e9d-a5c5-b45fe38446e3
ms.openlocfilehash: b43930557b4bdfd22bf902a6d9adf95eb8ba4d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286333"
---
# <a name="how-to-specify-an-out-parameter"></a>如何：指定 out 参数

此示例演示如何将函数参数指定为 `out` 参数，以及如何从 c # 程序调用该函数。

`out`使用在 c + + 中指定参数 <xref:System.Runtime.InteropServices.OutAttribute> 。

## <a name="example"></a>示例

此示例的第一部分创建 c + + DLL。 它定义一个类型，该类型包含具有参数的函数 `out` 。

```cpp
// cpp_out_param.cpp
// compile with: /LD /clr
using namespace System;
public value struct TestStruct {
   static void Test([Runtime::InteropServices::Out] String^ %s) {
      s = "a string";
   }
};
```

此源文件是使用上一个示例中创建的 c + + 组件的 c # 客户端。

```csharp
// cpp_out_param_2.cs
// compile with: /reference:cpp_out_param.dll
using System;
class TestClass {
   public static void Main() {
      String t;
      TestStruct.Test(out t);
      System.Console.WriteLine(t);
   }
}
```

```Output
a string
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)

---
description: 了解详细信息：如何：在/clr 编译中使用本机类型
title: 如何：在 clr 编译中使用本机类型
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
ms.openlocfilehash: 8e8479bb64166faec841d9d69ce38b3e8e57e048
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286275"
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>如何：在 /clr 编译中使用本机类型

可以在 **/clr** 编译中定义本机类型，并在程序集中使用该本机类型。 但是，本机类型将不可用于引用的元数据。

每个程序集都必须包含它将使用的每个本机类型的定义。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="examples"></a>示例

此示例将创建一个定义和使用本机类型的组件。

```cpp
// use_native_type_in_clr.cpp
// compile with: /clr /LD
public struct NativeClass {
   static int Test() { return 98; }
};

public ref struct ManagedClass {
   static int i = NativeClass::Test();
   void Test() {
      System::Console::WriteLine(i);
   }
};
```

此示例定义了一个使用组件的客户端。 请注意，访问本机类型是错误的，除非它是在编译单位中定义的。

```cpp
// use_native_type_in_clr_2.cpp
// compile with: /clr
#using "use_native_type_in_clr.dll"
// Uncomment the following 3 lines to resolve.
// public struct NativeClass {
//    static int Test() { return 98; }
// };

int main() {
   ManagedClass x;
   x.Test();

   System::Console::WriteLine(NativeClass::Test());   // C2653
}
```

## <a name="see-also"></a>请参阅

[使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)

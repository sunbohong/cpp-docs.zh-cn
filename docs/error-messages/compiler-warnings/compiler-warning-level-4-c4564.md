---
description: 详细了解：编译器警告 (级别 4) C4564
title: 编译器警告（等级 4）C4564
ms.date: 11/04/2016
f1_keywords:
- C4564
helpviewer_keywords:
- C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
ms.openlocfilehash: 112d1d20d34619d7a39d20c7fcd5f21584730cef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255166"
---
# <a name="compiler-warning-level-4-c4564"></a>编译器警告（等级 4）C4564

类 "class" 的方法 "method" 定义了不受支持的默认参数 "parameter"

编译器检测到有一个或多个参数具有默认值的方法。 调用方法时，将忽略参数 (s) 的默认值;显式指定这些参数的值。 如果未显式指定这些参数的值，c + + 编译器将生成错误。

给定以下 .dll Visual Basic 创建，这将允许方法参数上的默认参数：

```vb
' C4564.vb
' compile with: vbc /t:library C4564.vb
Public class TestClass
   Public Sub MyMethod (a as Integer, _
                        Optional c as Integer=1)
   End Sub
End class
```

下面的 c + + 示例使用使用创建的 .dll Visual Basic

```cpp
// C4564.cpp
// compile with: /clr /W4 /WX
#using <C4564.dll>

int main() {
   TestClass ^ myx = gcnew TestClass();   // C4564
   myx->MyMethod(9);
   // try the following line instead, to avoid an error
   // myx->MyMethod(9, 1);
}
```

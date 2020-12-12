---
description: 了解详细信息：编译器警告 (等级 1) C4944
title: 编译器警告（等级 1）C4944
ms.date: 11/04/2016
f1_keywords:
- C4944
helpviewer_keywords:
- C4944
ms.assetid: e2905eb1-2e3b-4fab-a48b-c0cae0fd997f
ms.openlocfilehash: 8feff4072bec649761e14dbd74a74e7023f810cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328013"
---
# <a name="compiler-warning-level-1-c4944"></a>编译器警告（等级 1）C4944

“symbol”：无法从“assembly1”导入符号，因为当前范围内已存在“symbol”

在源代码文件中定义了符号，然后 #using 语句引用了也已定义该符号的程序集。 程序集中的符号将被忽略。

## <a name="examples"></a>示例

下面的示例使用一个名为 ClassA 类型创建了一个组件。

```csharp
// C4944.cs
// compile with: /target:library
// C# source code to create a dll
public class ClassA {
   public int i;
}
```

以下示例生成 C4944。

```cpp
// C4944b.cpp
// compile with: /clr /W1
class ClassA {
public:
   int u;
};

#using "C4944.dll"   // C4944 ClassA also defined C4944.dll

int main() {
   ClassA * x = new ClassA();
   x->u = 9;
   System::Console::WriteLine(x->u);
}
```

---
description: 详细了解：编译器警告 (等级 3) C4638
title: 编译器警告（等级 3）C4638
ms.date: 08/27/2018
f1_keywords:
- C4638
helpviewer_keywords:
- C4638
ms.assetid: 2c07923a-e103-4e40-bd11-fdfed428a5ec
ms.openlocfilehash: fc771004ebbfeef436a456523e2e2fc87382a291
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338571"
---
# <a name="compiler-warning-level-3-c4638"></a>编译器警告（等级 3）C4638

> XML 文档注释目标：引用未知符号 "*symbol*"

## <a name="remarks"></a>备注

编译器无法解析符号 (*symbol*)。 该符号在编译中必须有效。

## <a name="example"></a>示例

下面的示例生成 C4638：

```cpp
// C4638.cpp
// compile with: /clr /doc /LD /W3
using namespace System;

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary> Text </summary>
   /// <see cref="aSymbolThatAppearsNowhereInMyProject"/>
   // Try the following line instead:
   // /// <see cref="System::Console::WriteLine"/>
   void MyMethod() {}
};   // C4638
```

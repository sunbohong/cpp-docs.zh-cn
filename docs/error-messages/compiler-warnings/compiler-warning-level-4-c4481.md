---
description: 详细了解：编译器警告 (级别 4) C4481
title: 编译器警告（等级 4）C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: 463df18090a4f6f632a80543576db4cb9048e754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251292"
---
# <a name="compiler-warning-level-4-c4481"></a>编译器警告（等级 4）C4481

使用了非标准扩展：重写说明符 "关键字"

使用的关键字不是 c + + 标准中的一个，例如，在/clr 下运行的一个重写说明符。  有关详细信息，请参阅

- [/cgthreads（公共语言运行时编译）](../../build/reference/clr-common-language-runtime-compilation.md)

- [重写说明符](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>示例

下面的示例生成 C4481。

```cpp
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```

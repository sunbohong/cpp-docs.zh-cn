---
description: 详细了解：编译器警告 (级别 4) C4239
title: 编译器警告（等级 4）C4239
ms.date: 11/04/2016
f1_keywords:
- C4239
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
ms.openlocfilehash: 635795392b5544f4985305a02e8534188c049224
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334858"
---
# <a name="compiler-warning-level-4-c4239"></a>编译器警告（等级 4）C4239

使用了非标准扩展： "token"：从 "type" 转换为 "type"

C + + 标准不允许此类型转换，但此处允许它作为扩展。 此警告后面紧跟至少一个说明违反语言规则的说明。

## <a name="examples"></a>示例

下面的示例生成 C4239。

```cpp
// C4239.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

void func(void) {
   C & rC = C();   // C4239
   const C & rC2 = C();   // OK
   rC2;
}
```

不严格允许从整型转换为枚举类型。

下面的示例生成 C4239。

```cpp
// C4239b.cpp
// compile with: /W4 /c
enum E { value };
struct S {
   E e : 2;
} s = { 5 };   // C4239
// try the following line instead
// } s = { (E)5 };
```

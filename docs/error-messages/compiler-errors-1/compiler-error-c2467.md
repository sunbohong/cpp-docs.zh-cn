---
description: 了解更多：编译器错误 C2467
title: 编译器错误 C2467
ms.date: 11/04/2016
f1_keywords:
- C2467
helpviewer_keywords:
- C2467
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
ms.openlocfilehash: fd5227e451208d848d631550da33999a4ebae8dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333814"
---
# <a name="compiler-error-c2467"></a>编译器错误 C2467

匿名 "用户定义类型" 的声明非法

已声明嵌套的用户定义类型。 使用 ANSI 兼容性选项（ ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 启用）编译 C 源代码时出现错误。

下面的示例生成 C2467：

```c
//C2467.c
// compile with: /Za
int main() {
   struct X {
      union { int i; };   // C2467, nested declaration
   };
}
```

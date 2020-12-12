---
description: 详细了解：编译器警告 (级别 4) C4205
title: 编译器警告（等级 4）C4205
ms.date: 11/04/2016
f1_keywords:
- C4205
helpviewer_keywords:
- C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
ms.openlocfilehash: d4a9250ad84f45a9e2ce40e6f103904ce7f8722e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173228"
---
# <a name="compiler-warning-level-4-c4205"></a>编译器警告（等级 4）C4205

使用了非标准扩展：函数范围内的静态函数声明

利用 Microsoft extension (/Ze) ， **`static`** 可以在另一个函数内声明函数。 函数被赋予全局范围。

## <a name="example"></a>示例

```c
// C4205.c
// compile with: /W4
void func1()
{
   static int func2();  // C4205
};

int main()
{
}
```

此类初始化在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中无效。

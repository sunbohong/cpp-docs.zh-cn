---
description: 详细了解：编译器警告 (级别 4) C4201
title: 编译器警告（等级 4）C4201
ms.date: 11/04/2016
f1_keywords:
- C4201
helpviewer_keywords:
- C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
ms.openlocfilehash: 739e09750f8f051ee0fd380fbb25858e620c70a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206716"
---
# <a name="compiler-warning-level-4-c4201"></a>编译器警告（等级 4）C4201

使用了非标准扩展：无号结构/联合

在 "Microsoft extension (/Ze) 中，可以指定一个不包含声明符的结构作为另一个结构或联合的成员。 在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 下，这些结构会生成错误。

## <a name="example"></a>示例

```cpp
// C4201.cpp
// compile with: /W4
struct S
{
   float y;
   struct
   {
      int a, b, c;  // C4201
   };
} *p_s;

int main()
{
}
```

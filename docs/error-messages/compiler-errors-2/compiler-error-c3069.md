---
description: 了解更多：编译器错误 C3069
title: 编译器错误 C3069
ms.date: 11/04/2016
f1_keywords:
- C3069
helpviewer_keywords:
- C3069
ms.assetid: ca94291b-2bb4-4e3f-9acf-534234b83513
ms.openlocfilehash: cc56ded4f14e137b9f5bf28681fb319a650f363a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341134"
---
# <a name="compiler-error-c3069"></a>编译器错误 C3069

“operator”: 不允许用于枚举类型

CLR 枚举不支持运算符。  有关详细信息，请参阅 [如何：在 c + +/cli 中定义和使用枚举](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C3069：

```cpp
// C3069.cpp
// compile with: /clr
enum struct E { e1 };
enum F { f1 };

int main() {
   E e = E::e1;
   bool tf;
   tf = !e;   // C3069

   // supported for native enums
   F f = f1;
   tf = !f;
}
```

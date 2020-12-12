---
description: 了解更多：编译器错误 C3063
title: 编译器错误 C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: 304359e34b6cbae07d2f901db02c6e5ed04e373c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281699"
---
# <a name="compiler-error-c3063"></a>编译器错误 C3063

运算符 "operator"：所有操作数必须具有相同的枚举类型

对枚举器使用运算符时，两个操作数必须是枚举类型。 有关详细信息，请参阅 [如何：在 c + +/cli 中定义和使用枚举](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C3063，并演示如何修复此问题：

```cpp
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

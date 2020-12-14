---
description: 了解更多：编译器错误 C3154
title: 编译器错误 C3154
ms.date: 11/04/2016
f1_keywords:
- C3154
helpviewer_keywords:
- C3154
ms.assetid: 78005c74-eaaf-4ac2-88ae-6c25d01a302a
ms.openlocfilehash: c43800aba54431041b13e70d9e94c80d98d8ee84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203973"
---
# <a name="compiler-error-c3154"></a>编译器错误 C3154

省略号之前应为 "，"。 参数数组函数不支持非逗号分隔的省略号。

未正确声明可变参数函数。

有关详细信息，请参阅 [变量参数列表 ( (c + +/cli) ) ](../../extensions/variable-argument-lists-dot-dot-dot-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C3154。

```cpp
// C3154.cpp
// compile with: /clr
ref struct R {
   void Func(int ... array<int> ^);   // C3154
   void Func2(int i, ... array<int> ^){}   // OK
   void Func3(array<int> ^){}   // OK
   void Func4(... array<int> ^){}   // OK
};

int main() {
   R ^ r = gcnew R;
   r->Func4(1,2,3);
}
```

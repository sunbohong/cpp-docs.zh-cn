---
description: 详细了解：编译器警告 (级别 4) C4263
title: 编译器警告（等级 4）C4263
ms.date: 11/04/2016
f1_keywords:
- C4263
helpviewer_keywords:
- C4263
ms.assetid: daabb05d-ab56-460f-ab6c-c74d222ef649
ms.openlocfilehash: 7b7eb7fdf8e66ab5d09c8dc0f9511d3c88162084
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339147"
---
# <a name="compiler-warning-level-4-c4263"></a>编译器警告（等级 4）C4263

"function"：成员函数不重写任何基类虚拟成员函数

类函数定义与基类中的虚函数具有相同的名称，但不是相同的参数数目或类型。 这有效地隐藏了基类中的虚函数。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4263：

```cpp
// C4263.cpp
// compile with: /W4
#pragma warning(default:4263)
#pragma warning(default:4264)
class B {
public:
   virtual void func();
};

class D : public B {
   void func(int);   // C4263
};

int main() {
}
```

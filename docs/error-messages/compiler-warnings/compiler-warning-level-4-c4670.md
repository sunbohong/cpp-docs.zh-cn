---
description: 详细了解：编译器警告 (级别 4) C4670
title: 编译器警告（等级 4）C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: c1d0f81f10fe63882987d660e4b9099f4ff895ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134025"
---
# <a name="compiler-warning-level-4-c4670"></a>编译器警告（等级 4）C4670

“identifier”：该基类不可访问

要在块中引发的对象的指定基类 **`try`** 不可访问。 不能实例化引发的对象。 检查基类继承了正确的访问说明符。

下面的示例生成 C4670：

```cpp
// C4670.cpp
// compile with: /EHsc /W4
class A
{
};

class B : /* public */ A
{
} b;   // inherits A with private access by default

int main()
{
    try
    {
       throw b;   // C4670
    }
    catch( B )
    {
    }
}
```

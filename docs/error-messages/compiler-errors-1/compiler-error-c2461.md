---
description: 了解更多：编译器错误 C2461
title: 编译器错误 C2461
ms.date: 11/04/2016
f1_keywords:
- C2461
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
ms.openlocfilehash: 788c8e475bd38b829ca8426137569a5d8a083f18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341823"
---
# <a name="compiler-error-c2461"></a>编译器错误 C2461

> "*class*"：构造函数语法缺少形参

类的构造函数未指定任何形参。 构造函数的声明必须指定形参列表。 列表可以为空。

若要解决此问题，请在 *class*：:**类* 的声明后面添加一对括号。

## <a name="example"></a>示例

下面的示例演示如何修复 C2461：

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```

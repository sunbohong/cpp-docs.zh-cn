---
description: 了解更多：编译器错误 C3394
title: 编译器错误 C3394
ms.date: 11/04/2016
f1_keywords:
- C3394
helpviewer_keywords:
- C3394
ms.assetid: 4e025d79-27ba-43c8-b0d9-839ecef98126
ms.openlocfilehash: ea805ef8ff9bf6e19498135ae6fcd9ba7e3ff9e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313354"
---
# <a name="compiler-error-c3394"></a>编译器错误 C3394

constraint 子句有语法错误：应为类型却发现“identifier”

约束格式不正确。  有关详细信息，请参阅[泛型类型参数的约束 (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md)。

## <a name="example"></a>示例

下面的示例生成 C3394：

```cpp
// C3394.cpp
// compile with: /clr /c
ref class MyClass {};
ref class R {
   generic<typename T>
   where T : static   // C3394
   // try the following line instead
   // where T : MyClass
   void f() {}
};
```

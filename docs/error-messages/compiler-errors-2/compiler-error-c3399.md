---
description: 了解更多：编译器错误 C3399
title: 编译器错误 C3399
ms.date: 11/04/2016
f1_keywords:
- C3399
helpviewer_keywords:
- C3399
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
ms.openlocfilehash: a950857e88c5cfcad50ac2efb064af4d7a5c0cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316422"
---
# <a name="compiler-error-c3399"></a>编译器错误 C3399

“type”：创建泛型参数的实例时无法提供变量

当指定 `gcnew()` 约束时，指定约束类型将具有无参数的构造函数。 因此，尝试实例化此类型并传递参数是错误的。

有关详细信息，请参阅有关 [c + +/cli)  (泛型类型参数的约束 ](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) 。

## <a name="example"></a>示例

以下示例生成 C3399。

```cpp
// C3399.cpp
// compile with: /clr /c
generic <class T>
where T : gcnew()
void f() {
   T t = gcnew T(1);   // C3399
   T t2 = gcnew T();   // OK
}
```

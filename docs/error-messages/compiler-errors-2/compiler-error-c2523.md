---
description: 了解更多：编译器错误 C2523
title: 编译器错误 C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: c9907742903cf4c13364d6ac63bb561b52e02232
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151159"
---
# <a name="compiler-error-c2523"></a>编译器错误 C2523

"class：： ~ identifier"：析构函数/终结器标记不匹配

析构函数的名称必须是前面带有颚化符 () 的类名 `~` 。 构造函数和析构函数是唯一与类同名的成员。

下面的示例生成 C2523：

```cpp
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```

---
description: 了解更多：编译器错误 C3883
title: 编译器错误 C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 216cfdc6385f12ff565eca581068ac5625a09044
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274419"
---
# <a name="compiler-error-c3883"></a>编译器错误 C3883

"var"： initonly 静态数据成员必须已初始化

使用 [initonly](../../dotnet/initonly-cpp-cli.md) 标记的变量未正确初始化。

下面的示例生成 C3883：

```cpp
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

以下示例演示了可能的解决方法：

```cpp
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

下面的示例演示如何在静态构造函数中初始化：

```cpp
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```

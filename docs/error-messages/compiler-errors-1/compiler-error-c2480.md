---
description: 了解更多：编译器错误 C2480
title: 编译器错误 C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 0c7f73b7e1aa205d38577602b93907309935b216
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316539"
---
# <a name="compiler-error-c2480"></a>编译器错误 C2480

"identifier"： "thread" 只对静态范围的数据项有效

不能将 `thread` 属性与自动变量、非静态数据成员、函数参数或函数声明或定义一起使用。

`thread`仅对全局变量、静态数据成员和局部静态变量使用特性。

下面的示例生成 C2480：

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```

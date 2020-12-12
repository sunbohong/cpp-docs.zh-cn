---
description: 了解更多：编译器错误 C2504
title: 编译器错误 C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 2a2269d750673a912096b497c10a9b112c23207c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213021"
---
# <a name="compiler-error-c2504"></a>编译器错误 C2504

"class"：未定义基类

声明基类，但从未定义过。  可能的原因：

1. 缺少包含文件。

1. 外部基类未通过 [extern](../../cpp/extern-cpp.md)声明。

下面的示例生成 C2504：

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

还行

```
class C{};
class D : public C {};
```

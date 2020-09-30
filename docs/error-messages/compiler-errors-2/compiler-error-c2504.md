---
title: 编译器错误 C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 0860f4b860b370f96c2c29046b090d5b205c63ba
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509395"
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

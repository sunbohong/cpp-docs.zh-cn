---
description: 了解更多：编译器错误 C2757
title: 编译器错误 C2757
ms.date: 11/04/2016
f1_keywords:
- C2757
helpviewer_keywords:
- C2757
ms.assetid: 421f102f-8a32-4d47-a109-811ddf2c909d
ms.openlocfilehash: e0be0f2a4c8dc5a5646400cbd0fa99e343ea82d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336180"
---
# <a name="compiler-error-c2757"></a>编译器错误 C2757

"symbol"：具有此名称的符号已存在，因此不能将此名称用作命名空间名称

当前编译中用作命名空间标识符的符号已在引用的程序集中使用。

下面的示例生成 C2757：

```cpp
// C2757a.cpp
// compile with: /clr /LD
public ref class Nes {};
```

然后，

```cpp
// C2757b.cpp
// compile with: /clr /c
#using <C2757a.dll>

namespace Nes {    // C2757
// try the following line instead
// namespace Nes2 {
   public ref class X {};
}
```

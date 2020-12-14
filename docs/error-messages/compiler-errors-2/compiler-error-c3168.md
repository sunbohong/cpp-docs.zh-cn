---
description: 了解更多：编译器错误 C3168
title: 编译器错误 C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: a6b9708ebb9c7fe3d9d6be7d73c24b92b1e8c6eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242244"
---
# <a name="compiler-error-c3168"></a>编译器错误 C3168

"type"：枚举的基础类型非法

为类型指定的基础类型 **`enum`** 无效。 基础类型必须是 c + + 类型或相应的 CLR 类型。

下面的示例生成 C3168：

```cpp
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```

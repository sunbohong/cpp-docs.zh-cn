---
description: 了解更多：编译器错误 C2390
title: 编译器错误 C2390
ms.date: 11/04/2016
f1_keywords:
- C2390
helpviewer_keywords:
- C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
ms.openlocfilehash: 91539cea6ed89c02734c08f068f3d6474283dfa9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337592"
---
# <a name="compiler-error-c2390"></a>编译器错误 C2390

"identifier"：不正确的存储类 "说明符"

存储类对于全局范围的标识符无效。 默认存储类用于代替无效类。

可能的解决方法：

- 如果该标识符是一个函数，则使用存储来声明它 **`extern`** 。

- 如果标识符是形参或局部变量，则使用自动存储来声明它。

- 如果该标识符是全局变量，请在不使用存储类的情况下声明它 (自动存储) 。

## <a name="example"></a>示例

- 下面的示例生成 C2390：

```cpp
// C2390.cpp
register int i;   // C2390

int main() {
   register int j;   // OK
}
```

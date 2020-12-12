---
description: 了解更多：编译器错误 C2433
title: 编译器错误 C2433
ms.date: 11/04/2016
f1_keywords:
- C2433
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
ms.openlocfilehash: 67d7a0f34ef988c6d67a720a2af2d2fa493b2bf2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189946"
---
# <a name="compiler-error-c2433"></a>编译器错误 C2433

"identifier"：不允许在数据声明中使用 "修饰符"

**`friend`**、 **`virtual`** 和 **`inline`** 修饰符不能用于数据声明。

## <a name="example"></a>示例

下面的示例生成 C2433。

```cpp
// C2433.cpp
class C{};

int main() {
   inline C c;   // C2433
}
```

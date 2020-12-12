---
description: 了解更多：编译器错误 C2153
title: 编译器错误 C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: 0b5ded0908f3c12033f1c2b3b034b41b52e847cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181288"
---
# <a name="compiler-error-c2153"></a>编译器错误 C2153

十六进制常量必须至少有一个十六进制数字

十六进制常量0x、0X 和 \x 无效。 至少一个十六进制数字必须在 x 或 X 之后。

下面的示例生成 C2153：

```cpp
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```

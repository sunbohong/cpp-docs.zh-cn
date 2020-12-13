---
description: 了解更多：编译器错误 C2117
title: 编译器错误 C2117
ms.date: 11/04/2016
f1_keywords:
- C2117
helpviewer_keywords:
- C2117
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
ms.openlocfilehash: 0e0d84a73d5f36f3014aa07d51b9701276a6e071
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335249"
---
# <a name="compiler-error-c2117"></a>编译器错误 C2117

"identifier"：数组界限溢出

数组的初始值设定项太多：

- 数组元素和初始值设定项在大小和数量上不匹配。

- 字符串中的空终止符无空格。

下面的示例生成 C2117：

```cpp
// C2117.cpp
int main() {
   char abc[4] = "abcd";   // C2117
   char def[4] = "abd";   // OK
}
```

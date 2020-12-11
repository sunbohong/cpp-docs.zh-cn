---
description: 了解详细信息：编译器警告 (等级 1) C4129
title: 编译器警告 (等级 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: 27ae487016a5d9a60a95e4715261ec5ba9171db4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155275"
---
# <a name="compiler-warning-level-1-c4129"></a>编译器警告 (等级 1) C4129

"character"：无法识别的字符转义序列

`character`以下 \\ 字符或字符串常量中的反斜杠 () 未被识别为有效的转义序列。 反斜杠将被忽略且不打印。 打印反斜杠后的字符。

若要打印单个反斜杠，请指定 () 双反斜杠 \\ \\ 。

2.13.2 部分中的 c + + 标准讨论了转义序列。

下面的示例生成 C4129：

```cpp
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```

---
description: 了解更多：编译器错误 C2601
title: 编译器错误 C2601
ms.date: 11/04/2016
f1_keywords:
- C2601
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
ms.openlocfilehash: 373ba519633034ddf63889eb82cd71dccfa4a743
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119991"
---
# <a name="compiler-error-c2601"></a>编译器错误 C2601

"function"：本地函数定义是非法的

代码尝试在函数内定义函数。

或者，在 C2601 错误位置之前，你的源代码中可能有一个额外的大括号。

下面的示例生成 C2601：

```cpp
// C2601.cpp
int main() {
   int i = 0;

   void funcname(int j) {   // C2601
      j++;
   }
}
```

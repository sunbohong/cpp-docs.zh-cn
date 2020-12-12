---
description: 了解更多：编译器错误 C2470
title: 编译器错误 C2470
ms.date: 11/04/2016
f1_keywords:
- C2470
helpviewer_keywords:
- C2470
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
ms.openlocfilehash: 90a57f02022044aca7b4062ea287eae213c26f74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164505"
---
# <a name="compiler-error-c2470"></a>编译器错误 C2470

"function"：看起来像函数定义，但没有参数列表;跳过明显体

缺少函数定义的参数列表。

下面的示例生成 C2470：

```cpp
// C2470.cpp
int MyFunc {};  // C2470
void MyFunc2() {};  //OK

int main(){
   MyFunc();
   MyFunc2();
}
```

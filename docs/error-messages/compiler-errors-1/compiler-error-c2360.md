---
description: 了解更多：编译器错误 C2360
title: 编译器错误 C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: c71a82816edfacede51a5774fec5e90560d964a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136456"
---
# <a name="compiler-error-c2360"></a>编译器错误 C2360

"identifier" 的初始化被 "case" 标签跳过

`identifier`可以在语句中跳过的初始化 **`switch`** 。 不能跳过带有初始值设定项的声明，除非该声明括在块中。  (除非在块中声明，否则在语句结束之前，该变量在范围内 **`switch`** 。 ) 

下面的示例生成 C2360：

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

可能的解决方法：

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```

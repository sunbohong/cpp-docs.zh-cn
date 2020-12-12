---
description: 了解更多：编译器错误 C2361
title: 编译器错误 C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: 53ca69daf347d23bb27e214556a74c70c1e53725
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328317"
---
# <a name="compiler-error-c2361"></a>编译器错误 C2361

"default" 标签跳过 "identifier" 的初始化

`identifier`可以在语句中跳过的初始化 **`switch`** 。 不能跳过带有初始值设定项的声明，除非该声明括在块中。  (除非在块中声明，否则在语句结束之前，该变量在范围内 **`switch`** 。 ) 

下面的示例生成 C2361：

```cpp
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

可能的解决方法：

```cpp
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```

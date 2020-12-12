---
description: 了解更多：编译器错误 C2628
title: 编译器错误 C2628
ms.date: 11/04/2016
f1_keywords:
- C2628
helpviewer_keywords:
- C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
ms.openlocfilehash: 876e96bfb406262c150807e4e95f14dd5b7177d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123560"
---
# <a name="compiler-error-c2628"></a>编译器错误 C2628

"type1" 后跟 "type2" 是非法的 (您是否忘记了 ";"？) 

可能缺少分号。

下面的示例生成 C2628：

```cpp
// C2628.cpp
class CMyClass {}
int main(){}   // C2628 error
```

可能的解决方法：

```cpp
// C2628b.cpp
class CMyClass {};
int main(){}
```

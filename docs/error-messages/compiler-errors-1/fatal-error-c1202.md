---
title: 错误 C1202
ms.date: 11/04/2016
f1_keywords:
- C1202
helpviewer_keywords:
- C1202
ms.assetid: c859adb8-17a7-4fa1-a1f3-5820b7bf3849
ms.openlocfilehash: 64e0ee6a98d7005bb2b15833f88c31d593b5b5c2
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686556"
---
# <a name="fatal-error-c1202"></a>错误 C1202

递归类型或函数依赖项上下文太复杂

模板定义为递归，或者超出复杂性限制。

## <a name="examples"></a>示例

下面的示例生成 C1202。

```cpp
// C1202.cpp
// processor: x86 IPF
template<int n>
class Factorial : public Factorial<n-1>  {   // C1202
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};
Factorial<7> facSeven;
```

可能的解决方法。

```cpp
// C1202b.cpp
// compile with: /c
template<int n>
class Factorial : public Factorial<n-1> {
public:
   operator int () {
      return Factorial <n-1>::operator int () * n;
   }
};

template <>
class Factorial<0> {
public:
   operator int () {
      return 1;
   }
};

Factorial<7> facSeven;
```

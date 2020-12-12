---
description: 了解更多：编译器错误 C2474
title: 编译器错误 C2474
ms.date: 11/04/2016
f1_keywords:
- C2474
helpviewer_keywords:
- C2474
ms.assetid: 64e6c61e-6e77-480e-bcf0-b30a2fc482ac
ms.openlocfilehash: adbfce63a5a8d97707bfb8e73dfda265f5d5e328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164401"
---
# <a name="compiler-error-c2474"></a>编译器错误 C2474

“keyword”: 缺少相邻的分号，可能是关键字或标识符。

编译器需要找到一个分号，因此不能确定你的意图。 增加一个分号以解决此问题。

## <a name="example"></a>示例

以下示例生成 C2474。

```cpp
// C2474.cpp
// compile with: /clr /c

ref class A {
   ref class B {}
   property int i;   // C2474 error
};

// OK
ref class B {
   ref class D {};
   property int i;
};

ref class E {
   ref class F {} property;
   int i;
};
```

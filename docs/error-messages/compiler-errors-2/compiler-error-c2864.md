---
description: 了解更多：编译器错误 C2864
title: 编译器错误 C2864
ms.date: 10/04/2019
f1_keywords:
- C2864
helpviewer_keywords:
- C2864
ms.assetid: d0ca2ad9-90a6-4aef-8511-98a3b414c102
ms.openlocfilehash: 763e70fd3ac988cca94f71feeab975e8b8630402
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305359"
---
# <a name="compiler-error-c2864"></a>编译器错误 C2864

> "*member name*"：具有类内初始值设定项的静态数据成员必须具有非易失性常量整型

## <a name="remarks"></a>备注

若要初始化 **`static`** 已定义为 **`volatile`** 、非或非整型的数据成员 **`const`** ，请使用成员定义语句。 它们不能在声明中初始化。

## <a name="example"></a>示例

此示例生成 C2864：

```cpp
// C2864.cpp
// compile with: /c
class B  {
private:
   int a = 3;   // OK
   static int b = 3;   // C2864
   volatile static int c = 3;   // C2864
   volatile static const int d = 3;   // C2864
   static const long long e = 3;   // OK
   static const double f = 3.33;   // C2864
};
```

此示例演示如何修复 C2864：

```cpp
// C2864b.cpp
// compile with: /c
class C  {
private:
   int a = 3;
   static int b; // = 3; C2864
   volatile static int c; // = 3; C2864
   volatile static const int d; // = 3; C2864
   static const long long e = 3;
   static const double f; // = 3.33; C2864
};

// Initialize static volatile, non-const, or non-integral
// data members when defined, not when declared:
int C::b = 3;
volatile int C::c = 3;
volatile const int C::d = 3;
const double C::f = 3.33;
```

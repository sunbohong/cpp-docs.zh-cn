---
description: 了解更多：编译器错误 C3194
title: 编译器错误 C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 7513b9d4964b6eb0024c3b51480f188243bf2637
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174034"
---
# <a name="compiler-error-c3194"></a>编译器错误 C3194

"member"：值类型不能具有赋值运算符

需要编译器自动调用的特殊成员函数，例如复制构造函数或复制赋值运算符，在值类中不受支持。

## <a name="example"></a>示例

下面的示例生成 C3194。

```cpp
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```

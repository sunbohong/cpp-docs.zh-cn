---
description: 了解更多：编译器错误 C3831
title: 编译器错误 C3831
ms.date: 11/04/2016
f1_keywords:
- C3831
helpviewer_keywords:
- C3831
ms.assetid: a125d8dc-b75a-4ea0-b6c7-fe7b119dba25
ms.openlocfilehash: ba3d1e7f6dfc2670307e510ee6eb13fa6277bc1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311807"
---
# <a name="compiler-error-c3831"></a>编译器错误 C3831

"member"： "class" 不能有钉住的数据成员或返回钉住指针的成员函数

[pin_ptr (c + +/cli) ](../../extensions/pin-ptr-cpp-cli.md) 未正确使用。

## <a name="example"></a>示例

下面的示例生成 C3831：

```cpp
// C3831a.cpp
// compile with: /clr
ref class Y
{
public:
   int i;
};

ref class X
{
   pin_ptr<int> mbr_Y;   // C3831
   int^ mbr_Y2;   // OK
};

int main() {
   Y y;
   pin_ptr<int> p = &y.i;
}
```

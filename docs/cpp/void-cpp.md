---
description: '了解详细信息： void (c + +) '
title: void (C++)
ms.date: 11/04/2016
f1_keywords:
- void_cpp
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
ms.openlocfilehash: e49dfa03e289cdbace50a24cf6854d25c51b3426
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213346"
---
# <a name="void-c"></a>void (C++)

当用作函数返回类型时， **`void`** 关键字指定函数不返回值。 用于函数的参数列表时， **`void`** 指定该函数不采用任何参数。 在指针的声明中使用时， **`void`** 指定指针为 "通用"。

如果指针的类型为 **void \* *_，则指针可指向未使用 _* `const` 或关键字声明的任何变量** **`volatile`** 。 不能取消引用 **void \** _ 指针，除非将其强制转换为另一种类型。 _*Void \**_ 指针可以转换为任何其他类型的数据指针。

_ *`void`* * 指针可指向函数，但不能指向 c + + 中的类成员。

不能声明类型的变量 **`void`** 。

## <a name="example"></a>示例

```cpp
// void.cpp
void vobject;   // C2182
void *pv;   // okay
int *pint; int i;
int main() {
   pv = &i;
   // Cast optional in C required in C++
   pint = (int *)pv;
}
```

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)<br/>
[内置类型](../cpp/fundamental-types-cpp.md)

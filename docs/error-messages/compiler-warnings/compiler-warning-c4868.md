---
description: 详细了解：编译器警告 (级别 4) C4868
title: 编译器警告 C4868
ms.date: 10/26/2017
f1_keywords:
- C4868
helpviewer_keywords:
- C4868
ms.assetid: fc6aa7e5-34dd-4ec2-88bd-16e430361dc7
ms.openlocfilehash: 66b6673dc1981351aa25a7ce6c0b9bc30bdf82c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315005"
---
# <a name="compiler-warning-level-4-c4868"></a>编译器警告 (等级 4) C4868

> "_文件_ (*Line_number*) " 编译器在大括号内初始值设定项列表中不能强制执行从左到右的计算顺序

将按从左到右的顺序计算大括号内初始值设定项列表的元素。 在以下两种情况下，编译器无法保证此顺序：第一种情况是，某些元素是按值传递的对象;第二种情况是，在编译时 `/clr` ，某些元素是对象的字段或是数组元素。 当编译器无法保证从左向右计算时，它会发出警告 C4868。

对于 Visual Studio 2015 Update 2 完成的编译器一致性工作，可生成此警告。 在 Visual Studio 2015 Update 2 之前编译的代码现在可以生成 C4868。

默认情况下，此警告处于关闭状态。 使用 `/Wall` 可激活此警告。

若要解决此警告，请首先考虑是否需要对初始值设定项列表元素进行从左到右的计算，例如，当计算元素时，可能会产生与顺序相关的副作用。 在许多情况下，计算元素的顺序不会有明显的影响。

如果计算顺序必须是从左向右的，请考虑是否可以改为按引用传递元素 **`const`** 。 诸如这样的更改将消除以下代码示例中的警告。

## <a name="example"></a>示例

此示例生成 C4868，并演示如何修复此问题：

```cpp
// C4868.cpp
// compile with: /c /Wall
#include <cstdio>

class HasCopyConstructor
{
public:
    int x;

    HasCopyConstructor(int x): x(x) {}

    HasCopyConstructor(const HasCopyConstructor& h): x(h.x)
    {
        printf("Constructing %d\n", h.x);
    }
};

class TripWarning4868
{
public:
    // note that taking "HasCopyConstructor" parameters by-value will trigger copy-construction.
    TripWarning4868(HasCopyConstructor a, HasCopyConstructor b) {}

    // This variation will not trigger the warning:
    // TripWarning4868(const HasCopyConstructor& a, const HasCopyConstructor& b) {}
};

int main()
{
    HasCopyConstructor a{1};
    HasCopyConstructor b{2};

    // the warning will indicate the below line, the usage of the braced initializer list.
    TripWarning4868 warningOnThisLine{a, b};
};
```

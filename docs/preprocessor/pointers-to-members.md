---
description: 详细了解 pragma Microsoft c/c + + 中的 pointers_to_members 指令
title: pointers_to_members pragma
ms.date: 01/22/2021
f1_keywords:
- pointers_to_members_CPP
- vc-pragma.pointers_to_members
helpviewer_keywords:
- class members, pointers to
- pragma, pointers_to_members
- members, pointers to
- pointers_to_members pragma
no-loc:
- pragma
ms.openlocfilehash: 7f2ca20b70d477e66a38d2a57e489d64c4179191
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713371"
---
# <a name="pointers_to_members-no-locpragma"></a>`pointers_to_members` pragma

**C++ 专用**

指定指向类成员的指针是否可以在其关联类定义之前声明。 用于控制指针大小，以及解释指针所需的代码。

## <a name="syntax"></a>语法

> **`#pragma pointers_to_members(`***指针声明*[ **`,`** *最常见表示形式*]**`)`**

## <a name="remarks"></a>注解

您可以 **`pointers_to_members`** pragma 使用 [ `/vmb` `/vmg` 或](../build/reference/vmb-vmg-representation-method.md)编译器选项或 [继承关键字](../cpp/inheritance-keywords.md)将放置在您的源文件中。

*指针声明* 参数用于指定是否已在关联的函数定义之前或之后声明指向成员的指针。 *指针声明* 参数是以下两个符号之一：

| 参数 | 注释 |
|--------------|--------------|
| **`full_generality`** | 生成安全的（有时并非最佳）代码。 如果在 **`full_generality`** 关联的类定义之前声明指向成员的任何指针，则使用。 此参数始终使用由 *最常见的表示形式* 参数指定的指针表示形式。 等效于 **`/vmg`** 。 |
| **`best_case`** | 使用指向成员的所有指针的最佳大小写表示形式生成安全的最佳代码。 要求在声明指向类成员的指针之前定义此类。 默认值为 **`best_case`** 。 |

*最常见的表示形式* 参数指定最小的指针表示形式，编译器可以安全地使用该表示形式引用指向翻译单元中某个类的成员的任何指针。 参数可以是以下值之一：

| 参数 | 注释 |
|--------------|--------------|
| **`single_inheritance`** | 最常规的表示形式为单一继承（指向成员函数的指针）。 如果类定义（已为其声明指向成员的指针）的继承模型为多重继承或虚拟继承，则会导致出现错误。 |
| **`multiple_inheritance`** | 最常规的表示形式为多重继承（指向成员函数的指针）。 如果类定义（已为其声明指向成员的指针）的继承模型为虚拟继承，则会导致出现错误。 |
| **`virtual_inheritance`** | 最常规的表示形式为虚拟继承（指向成员函数的指针）。 绝不会导致出现错误。 **`virtual_inheritance`** 使用时的默认参数 `#pragma pointers_to_members(full_generality)` 。 |

> [!CAUTION]
> 建议你将 **`pointers_to_members`** pragma 仅放在要影响的源代码文件中，并且仅在任何指令后放置 `#include` 。 这种做法降低了 pragma 将影响其他文件的风险，并且你将不小心为同一变量、函数或类名指定多个定义。

## <a name="example"></a>示例

```cpp
//   Specify single-inheritance only
#pragma pointers_to_members( full_generality, single_inheritance )
```

**结束 C++ 专用**

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

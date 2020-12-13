---
description: 了解详细信息： Run-Time 类型信息
title: 运行时类型信息
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
ms.openlocfilehash: 1cba6ffbb46899ace6d5f1d233e077603a0c1c4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340432"
---
# <a name="run-time-type-information"></a>运行时类型信息

运行时类型信息 (RTTI) 是一种允许在程序执行过程中确定对象的类型的机制。 RTTI 已添加到 C++ 语言中，因为许多类库供应商将自行实现此功能。 这会导致库之间出现不兼容的情况。 因此，显而易见的是，需要语言级别的对运行时类型信息的支持。

为了清楚起见，此 RTTI 的讨论几乎完全是针对指针展开的。 但讨论的概念也适用于引用。

有三个针对运行时类型信息的 C++ 语言元素：

- [Dynamic_cast](../cpp/dynamic-cast-operator.md)运算符。

   用于多态类型的转换。

- [Typeid](../cpp/typeid-operator.md)运算符。

   用于标识对象的确切类型。

- [Type_info](../cpp/type-info-class.md)类。

   用于保存由运算符返回的类型信息 **`typeid`** 。

## <a name="see-also"></a>请参阅

[强制转换](../cpp/casting.md)

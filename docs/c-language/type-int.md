---
description: 详细了解：int 类型
title: int 类型
ms.date: 11/04/2016
helpviewer_keywords:
- int data type
- type int
- portability [C++], type int
- signed integers
ms.assetid: 0067ce9a-281e-491a-ae63-632952981e13
ms.openlocfilehash: e6ec94877dad3dd49bb5e9b11f77ceb2a734ab1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242757"
---
# <a name="type-int"></a>int 类型

`signed int` 或 `unsigned int` 项的大小是特定计算机上的标准整数大小。 例如，在 16 位操作系统中，`int` 类型通常是 16 位（或 2 字节）。 在 32 位操作系统中，`int` 类型通常是 32 位（或 4 字节）。 因此，`int` 类型与 `short int` 或 `long int` 类型等效，`unsigned int` 类型与 `unsigned short` 或 `unsigned long` 类型等效，具体视目标环境而定。 除非另有规定，否则 `int` 类型都表示带符号值。

类型说明符 `int` 和 `unsigned int`（或简写为 `unsigned`）定义了 C 语言的某些功能（例如，`enum` 类型）。 在这种情况下，特定实现的 `int` 和 `unsigned int` 的定义决定了实际存储。

**Microsoft 专用**

带符号整数以 2 的补数的形式表示。 最高有效位保留符号：1 表示负数，0 表示正数和零。 值的范围在 [C 和 C++ 整数限制](../c-language/cpp-integer-limits.md)中给定（摘自 LIMITS.H 头文件）。

**结束 Microsoft 专用**

> [!NOTE]
> `int` 和 `unsigned int` 类型说明符在 C 程序中广泛使用，因为它们可便于特定计算机以对自己最高效的方式处理整数值。 不过，由于 `int` 和 `unsigned int` 类型的大小不同，因此依赖特定 `int` 大小的程序可能无法移植到其他计算机中。 为了提高程序的可移植性，可以使用带 `sizeof` 运算符（如 [`sizeof` 运算符](../c-language/sizeof-operator-c.md)中所述）的表达式，而不是硬编码的数据大小。

## <a name="see-also"></a>请参阅

[基本类型的存储](../c-language/storage-of-basic-types.md)

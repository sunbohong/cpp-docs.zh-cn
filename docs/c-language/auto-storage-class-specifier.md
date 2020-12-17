---
description: 详细了解：`auto` 存储类说明符
title: auto 存储类说明符
ms.date: 11/04/2016
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
ms.openlocfilehash: a20e599ca7189548f92a78ff378e3b5f9f202b3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97279854"
---
# <a name="auto-storage-class-specifier"></a>`auto` 存储类说明符

`auto` 存储类说明符声明具有本地生存期的自动变量。 `auto` 变量只在声明它的代码块中可见。 `auto` 变量的声明可包含初始值设定项，如[初始化](../c-language/initialization.md)中所述。 由于包含 `auto` 存储类的变量不会自动初始化，因此应在声明这些变量时显式初始化它们，或在代码块的语句中将初始值赋给它们。 未初始化的 `auto` 变量的值是未定义的。 （如果给定了初始值设定项，则每次 `auto` 或 `register` 存储类的局部变量进入范围时都会被初始化。）

内部 `static` 变量（具有局部或块范围的静态变量）可以使用任何外部项或 `static` 项的地址进行初始化，但不能使用另一个 `auto` 项的地址进行初始化，因为 `auto` 项的地址不是常数。

## <a name="see-also"></a>请参阅

[`auto` 关键字](../cpp/auto-cpp.md)

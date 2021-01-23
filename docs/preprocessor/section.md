---
description: 详细了解 pragma Microsoft c/c + + 中的节指令
title: 区 pragma
ms.date: 01/22/2021
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragma, section
- section pragma
no-loc:
- pragma
ms.openlocfilehash: 8bd55bbba65480b7345376059489d8aef945ab34
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713228"
---
# <a name="section-no-locpragma"></a>`section` pragma

在 OBJ 文件中创建一个节。

## <a name="syntax"></a>语法

> **`#pragma section( "`***节名称* **`"`**[ **`,`** *特性*]**`)`**

## <a name="remarks"></a>注解

术语 " *段* " 和 " *节* " 在本文中具有相同的含义。

定义某个节后，它将对编译的其余部分保持有效。 但是，必须使用 [`__declspec(allocate)`](../cpp/allocate.md) ，否则部分中将不会有任何内容。

*节名称* 是一个必选参数，该参数将成为节的名称。 该名称不得与任何标准节名称发生冲突。 [`/SECTION`](../build/reference/section-specify-section-attributes.md)有关创建节时不应使用的名称的列表，请参阅。

*属性* 是一个可选参数，它由一个或多个以逗号分隔的属性组成，以将其分配给部分。 可能的 *属性* 包括：

| Attribute | 说明 |
|--|--|
| **`read`** | 允许对数据进行读取操作。 |
| **`write`** | 允许对数据进行写入操作。 |
| **`execute`** | 允许执行代码。 |
| **`shared`** | 在所有加载图像的进程之间共享该节。 |
| **`nopage`** | 将节标记为不可分页。 适用于 Win32 设备驱动程序。 |
| **`nocache`** | 将该节标记为不可缓存。 适用于 Win32 设备驱动程序。 |
| **`discard`** | 将节标记为可放弃。 适用于 Win32 设备驱动程序。 |
| **`remove`** | 将该节标记为不驻留内存。 对于 (仅限 V *x* D) 的虚拟设备驱动程序。 |

如果未指定任何属性，则该节具有 **`read`** 和 **`write`** 属性。

## <a name="example"></a>示例

在此示例中，第一部分 pragma 标识了节及其属性。 整数 `j` 不会放入， `mysec` 因为它不是使用声明的 `__declspec(allocate)` 。 而是 `j` 转到数据部分。 整数 `i` `mysec` 由于其 `__declspec(allocate)` 存储类特性而进入。

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

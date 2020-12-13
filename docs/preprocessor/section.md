---
description: 了解详细信息：节杂注
title: section 杂注
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: f4a719c60fd5bdf4f8e8841aab88f82c30b92a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342278"
---
# <a name="section-pragma"></a>section 杂注

在 .obj 文件中创建一个节。

## <a name="syntax"></a>语法

> **#pragma 部分 (** "*节名*" [ **，** *特性* ] **)**

## <a name="remarks"></a>备注

术语 " *段* " 和 " *节* " 在本文中具有相同的含义。

一旦节被定义，它将对编译的其余部分保持有效。 但是，必须使用 [__declspec (分配) ](../cpp/allocate.md)，否则部分中将不会有任何内容。

*节名称* 是一个必选参数，该参数将成为节的名称。 该名称不得与任何标准节名称发生冲突。 有关创建节时不应使用的名称的列表，请参阅 [/SECTION](../build/reference/section-specify-section-attributes.md) 。

*属性* 是一个可选参数，它由一个或多个以逗号分隔的属性组成，以将其分配给部分。 可能的 *属性* 包括：

|特性|描述|
|-|-|
|**读取**|允许对数据进行读取操作。|
|**写入**|允许对数据进行写入操作。|
|**execute**|允许执行代码。|
|**共享**|在所有加载图像的进程之间共享该节。|
|**nopage**|将节标记为不可分页。 适用于 Win32 设备驱动程序。|
|**nocache**|将该节标记为不可缓存。 适用于 Win32 设备驱动程序。|
|**去除**|将节标记为可放弃。 适用于 Win32 设备驱动程序。|
|**remove**|将该节标记为不驻留内存。 对于 (仅限 V *x* D) 的虚拟设备驱动程序。|

如果未指定任何属性，则该节具有 **读取** 和 **写入** 特性。

## <a name="example"></a>示例

在此示例中，第一个节杂注标识了节及其特性。 `j`不会将整数置于， `mysec` 因为它不是使用声明的 `__declspec(allocate)` 。 而是 `j` 转到数据部分。 整数 `i` 将进入 `mysec` 作为其 `__declspec(allocate)` 存储类特性的结果。

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

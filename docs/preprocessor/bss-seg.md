---
description: 详细了解 pragma Microsoft c/c + + 中的 bss_seg 指令
title: bss_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragma, bss_seg
- bss_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 380d3c465145c3409e86ea6e76cd0b41890574fa
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713085"
---
# <a name="bss_seg-no-locpragma"></a>`bss_seg` pragma

指定将未初始化的变量存储在对象 ( .obj) 文件中的 (段) 部分。

## <a name="syntax"></a>语法

> **`#pragma bss_seg(`** ["*节名*" [ **`,`** "*节类*"]] **`)`**\
> **`#pragma bss_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *标识符*] [ **`,`** "*节名*" [ **`,`** "*节类*"]]**`)`**

### <a name="parameters"></a>Parameters

**`push`**\
 (可选) 将记录置于内部编译器堆栈上。 **`push`** 可以具有 *标识符* 和 *节名称*。

**`pop`**\
 (可选) 从内部编译器堆栈的顶部移除记录。 **`pop`** 可以具有 *标识符* 和 *节名称*。 使用标识符只需使用一个命令即可弹出多个记录 **`pop`** 。  *节名称* 成为 pop 后的活动 BSS 部分名称。

*identifier*\
与一起使用时 (可选) **`push`** ，为内部编译器堆栈上的记录指定名称。 当与一起使用时 **`pop`** ，指令将从内部堆栈中弹出记录，直到删除 *标识符* 。 如果在内部堆栈上找不到 *标识符* ，则不会弹出任何内容。

*"节名"*\
 (可选) 部分的名称。 当与一起使用时 **`pop`** ，将弹出堆栈，并且 *节名称* 成为活动的 BSS 部分名称。

*"section 类"*\
 (Optional) 被忽略，但包含它是为了兼容早于版本2.0 的 Microsoft c + + 版本。

## <a name="remarks"></a>注解

对象文件中的 *部分* 是作为一个单元加载到内存中的已命名数据块。 *BSS 部分* 是包含未初始化的数据的部分。 在本文中，术语 " *段* " 和 " *节* " 的含义相同。

**`bss_seg`** pragma 指令告诉编译器将未初始化的所有数据项从翻译单元放入名为 "*节名*" 的 BSS 部分。 在某些情况下，使用 **`bss_seg`** 可以通过将未初始化的数据分组到一个部分来缩短加载时间。 默认情况下，用于对象文件中未初始化数据的 BSS 部分的名称为 `.bss` 。 **`bss_seg`** pragma 不带 *节名称* 参数的指令将未初始化的后续数据项的 BSS 部分名称重置为 `.bss` 。

使用分配的数据 **`bss_seg`** pragma 不会保留有关其位置的任何信息。

有关不应用于创建部分的名称的列表，请参阅 [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

你还可以为初始化的数据指定部分 ([`data_seg`](../preprocessor/data-seg.md)) 、函数 ([`code_seg`](../preprocessor/code-seg.md)) 和 const 变量 ([`const_seg`](../preprocessor/const-seg.md)) 。

您可以使用 [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) 应用程序查看对象文件。 Visual Studio 随附每个受支持的目标体系结构的 DUMPBIN 版本。

## <a name="example"></a>示例

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

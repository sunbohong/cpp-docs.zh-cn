---
description: 详细了解 pragma Microsoft c/c + + 中的 data_seg 指令
title: data_seg pragma
ms.date: 01/22/2021
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragma, data_seg
no-loc:
- pragma
ms.openlocfilehash: cd0dac6961a642b8ed2bd5d485712d259d828a64
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713683"
---
# <a name="data_seg-no-locpragma"></a>`data_seg` pragma

指定数据段 (段) ，其中初始化的变量存储在对象 ( .obj) 文件中。

## <a name="syntax"></a>语法

> **`#pragma data_seg(`** ["*节名*" [ **`,`** "*节类*"]] **`)`**\
> **`#pragma data_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *标识符*] [ **`,`** "*节名*" [ **`,`** "*节类*"]]**`)`**

### <a name="parameters"></a>Parameters

**`push`**\
 (可选) 将记录置于内部编译器堆栈上。 **`push`** 可以具有 *标识符* 和 *节名称*。

**`pop`**\
 (可选) 从内部编译器堆栈的顶部移除记录。 **`pop`** 可以具有 *标识符* 和 *节名称*。 使用标识符只需使用一个命令即可弹出多个记录 **`pop`** 。  *节名称* 成为 pop 后面的活动数据部分名称。

*identifier*\
与一起使用时 (可选) **`push`** ，为内部编译器堆栈上的记录指定名称。 当与一起使用时，将在 **`pop`** 删除 *标识符* 之前弹出内部堆栈。 如果在内部堆栈上找不到 *标识符* ，则不会弹出任何内容。

*标识符* 允许使用单个命令弹出多个记录 **`pop`** 。

*"节名"*\
 (可选) 部分的名称。 当与一起使用时 **`pop`** ，将弹出堆栈，并且 *节名称* 成为活动数据部分名称。

*"section 类"*\
 (Optional) 被忽略，但包含它是为了兼容早于版本2.0 的 Microsoft c + + 版本。

## <a name="remarks"></a>注解

对象文件中的 *部分* 是作为一个单元加载到内存中的已命名数据块。 *数据部分* 是包含初始化的数据的部分。 在本文中，术语 " *段* " 和 " *节* " 的含义相同。

已初始化的变量的 .obj 文件中的默认部分是 `.data` 。 未初始化的变量被视为初始化为零，并存储在中 `.bss` 。

**`data_seg`** pragma 指令指示编译器将翻译单元中的所有初始化数据项放入名为 *节名称* 的数据节。 默认情况下，用于对象文件中初始化数据的数据部分命名为 `.data` 。 未初始化的变量被视为初始化为零，并存储在中 `.bss` 。 **`data_seg`** pragma 不带 *节名称* 参数的指令会将后续初始化数据项的数据节名称重置为 `.data` 。

使用分配 **`data_seg`** 的数据不会保留有关其位置的任何信息。

有关不应用于创建部分的名称的列表，请参阅 [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

你还可以为常量变量指定 ([`const_seg`](../preprocessor/const-seg.md)) 、未初始化的数据 ([`bss_seg`](../preprocessor/bss-seg.md)) 和函数 ([`code_seg`](../preprocessor/code-seg.md)) 的部分。

您可以使用 [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) 应用程序查看对象文件。 Visual Studio 随附每个受支持的目标体系结构的 DUMPBIN 版本。

## <a name="example"></a>示例

```cpp
// pragma_directive_data_seg.cpp
int h = 1;                     // stored in .data
int i = 0;                     // stored in .bss
#pragma data_seg(".my_data1")
int j = 1;                     // stored in .my_data1

#pragma data_seg(push, stack1, ".my_data2")
int l = 2;                     // stored in .my_data2

#pragma data_seg(pop, stack1)   // pop stack1 off the stack
int m = 3;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

---
description: 详细了解 pragma Microsoft c/c + + 中的 code_seg 指令
title: code_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.code_seg
helpviewer_keywords:
- pragma, code_seg
- code_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 0547c745fe5d22be3684e83e0dcc2c73e13e8edc
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713097"
---
# <a name="code_seg-no-locpragma"></a>`code_seg` pragma

指定将函数存储在对象 ( .obj) 文件中的 (段) 文本部分。

## <a name="syntax"></a>语法

> **`#pragma code_seg(`** ["*节名*" [ **`,`** "*节类*"]] **`)`**\
> **`#pragma code_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *标识符*] [ **`,`** "*节名*" [ **`,`** "*节类*"]]**`)`**

### <a name="parameters"></a>Parameters

**`push`**\
 (可选) 将记录置于内部编译器堆栈上。 **`push`** 可以具有 *标识符* 和 *节名称*。

**`pop`**\
 (可选) 从内部编译器堆栈的顶部移除记录。 **`pop`** 可以具有 *标识符* 和 *节名称*。 使用标识符只需使用一个命令即可弹出多个记录 **`pop`** 。  *节名称* 成为 pop 后面的活动文本部分名称。

*identifier*\
与一起使用时 (可选) **`push`** ，为内部编译器堆栈上的记录指定名称。 当与一起使用时 **`pop`** ，指令将从内部堆栈中弹出记录，直到删除 *标识符* 。 如果在内部堆栈上找不到 *标识符* ，则不会弹出任何内容。

"*节名*" \
 (可选) 部分的名称。 当与一起使用时 **`pop`** ，将弹出堆栈，并且 *节名称* 将成为活动文本部分名称。

"*section 类*" \
 (Optional) 被忽略，但包含它是为了兼容早于版本2.0 的 Microsoft c + + 版本。

## <a name="remarks"></a>注解

对象文件中的 *部分* 是作为一个单元加载到内存中的已命名数据块。 *文本部分* 是包含可执行代码的部分。 在本文中，术语 " *段* " 和 " *节* " 的含义相同。

**`code_seg`** pragma 指令指示编译器将翻译单元中的所有后续对象代码放入名为 "*节名*" 的文本部分。 默认情况下，用于对象文件中的函数的文本部分命名为 `.text` 。 **`code_seg`** pragma 不带 *节名称* 参数的指令会将后续对象代码的文本部分名称重置为 `.text` 。

**`code_seg`** pragma 指令不控制为实例化模板生成的对象代码的位置。 它也不控制由编译器隐式生成的代码，如特殊成员函数。 若要控制该代码，建议改为使用 [`__declspec(code_seg(...))`](../cpp/code-seg-declspec.md) 特性。 它使您能够控制所有对象代码的放置，包括编译器生成的代码。

有关不应用于创建部分的名称的列表，请参阅 [`/SECTION`](../build/reference/section-specify-section-attributes.md) 。

您还可以为初始化的数据指定部分 ([`data_seg`](../preprocessor/data-seg.md)) 、未初始化的数据 ([`bss_seg`](../preprocessor/bss-seg.md)) 和 const 变量 ([`const_seg`](../preprocessor/const-seg.md)) 。

您可以使用 [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) 应用程序查看对象文件。 Visual Studio 随附每个受支持的目标体系结构的 DUMPBIN 版本。

## <a name="example"></a>示例

此示例演示如何使用 **code_seg** pragma 指令来控制对象代码的放置位置：

```cpp
// pragma_directive_code_seg.cpp
void func1() {                  // stored in .text
}

#pragma code_seg(".my_data1")
void func2() {                  // stored in my_data1
}

#pragma code_seg(push, r1, ".my_data2")
void func3() {                  // stored in my_data2
}

#pragma code_seg(pop, r1)      // stored in my_data1
void func4() {
}

int main() {
}
```

## <a name="see-also"></a>另请参阅

[`code_seg (__declspec)`](../cpp/code-seg-declspec.md)\
[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

---
description: 了解详细信息： const_seg 杂注
title: const_seg 杂注
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
ms.openlocfilehash: 596f44a030aa6c09824d5798e54a3b126ce34544
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261198"
---
# <a name="const_seg-pragma"></a>const_seg 杂注

指定将 [const](../cpp/const-cpp.md) 变量存储在对象 ( .obj) 文件中的 (段) 部分。

## <a name="syntax"></a>语法

> **#pragma const_seg (** ["*节名*" [ **，** "*节类*"]] **)**\
> **#pragma const_seg (** {**推送**  |  **pop** } [ **，** *标识符*] [ **，** "*节名*" [ **，** "*部分类*"]] **)**

### <a name="parameters"></a>parameters

**请求**\
 (可选) 将记录置于内部编译器堆栈上。 **推送** 可以具有 *标识符* 和 *节名称*。

**弹出**\
 (可选) 从内部编译器堆栈的顶部移除记录。 **Pop** 可以具有 *标识符* 和 *节名称*。 使用 *标识符* 只需使用一个 **pop** 命令即可弹出多个记录。 *节名称* 成为 pop 后面的活动常量部分名称。

*identifier*\
与 **push** 一起使用时 (可选) ，为内部编译器堆栈上的记录指定一个名称。 当与 **pop** 一起使用时，指令将从内部堆栈中弹出记录，直到删除 *标识符* 。 如果在内部堆栈上找不到 *标识符* ，则不会弹出任何内容。

"*节名*" \
 (可选) 部分的名称。 当与 **pop** 一起使用时，将弹出堆栈，并且 *节名称* 将成为活动常量部分名称。

"*section 类*" \
 (Optional) 被忽略，但包含它是为了兼容早于版本2.0 的 Microsoft c + + 版本。

## <a name="remarks"></a>备注

对象文件中的 *部分* 是作为一个单元加载到内存中的已命名数据块。 *常量部分* 是包含常量数据的部分。 在本文中，术语 " *段* " 和 " *节* " 的含义相同。

**Const_seg** 杂注指令通知编译器将翻译单元中的所有常量数据项放入名为 "*节名*" 的常量部分。 变量的对象文件中的默认部分 **`const`** 是 `.rdata` 。 某些 **`const`** 变量（如标量）将自动内联到代码流中。 内联代码不显示在中 `.rdata` 。 不带 *节名* 参数 **const_seg** 杂注指令将后续数据项的节名称重置 **`const`** 为 `.rdata` 。

如果在中定义了需要动态初始化的对象 `const_seg` ，则结果将是未定义的行为。

有关不应用于创建部分的名称的列表，请参阅 [/SECTION](../build/reference/section-specify-section-attributes.md)。

您还可以为初始化的数据 ([data_seg](../preprocessor/data-seg.md)) 、未初始化的数据 ([bss_seg](../preprocessor/bss-seg.md))  (和函数指定 [节 code_seg) ](../preprocessor/code-seg.md) 。

您可以使用 [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) 应用程序查看对象文件。 Visual Studio 随附每个受支持的目标体系结构的 DUMPBIN 版本。

## <a name="example"></a>示例

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

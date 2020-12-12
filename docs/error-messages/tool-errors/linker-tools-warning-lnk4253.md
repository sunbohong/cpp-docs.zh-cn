---
description: 了解详细信息：链接器工具警告 LNK4253
title: 链接器工具警告 LNK4253
ms.date: 11/04/2016
f1_keywords:
- LNK4253
helpviewer_keywords:
- LNK4253
ms.assetid: ec7433a9-aa9c-495a-a9f2-075e7bc3e7bc
ms.openlocfilehash: 764d7698da8d724842b8387c9c4356bfce951079
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244480"
---
# <a name="linker-tools-warning-lnk4253"></a>链接器工具警告 LNK4253

部分 "section1" 未合并到 "section2";已合并到 "section3"

链接器检测到多个冲突的合并请求。 链接器将忽略其中一个请求。

遇到了 **/merge** 选项或指令时， `from` 由于上一个 **/merge** 选项或指令 (或由于链接器) 的隐式合并，该节已合并到其他部分。

若要解析 LNK4253，请删除其中一个合并请求。

面向 x86 计算机和 Windows CE 目标 (ARM、MIPS、SH4 和 Thumb) 与 Visual C++ 一起提供。CRT 部分现在为只读。 如果代码依赖于以前的行为 (。CRT 部分是读/写) ，你可能会看到意外的行为。

有关详细信息，请参阅

- [/MERGE (合并部分) ](../../build/reference/merge-combine-sections.md)

- [注释 (C/C++)](../../preprocessor/comment-c-cpp.md)

## <a name="example"></a>示例

在下面的示例中，将指示链接器 `.rdata` 两次合并节，而不是不同的部分。 下面的示例生成 LNK4253。

```cpp
// LNK4253.cpp
// compile with: /W1 /link /merge:.rdata=text2
// LNK4253 expected
#pragma comment(linker, "/merge:.rdata=.text")
int main() {}
```

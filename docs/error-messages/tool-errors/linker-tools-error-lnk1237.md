---
description: 了解详细信息：链接器工具错误 LNK1237
title: 链接器工具错误 LNK1237
ms.date: 11/04/2016
f1_keywords:
- LNK1237
helpviewer_keywords:
- LNK1237
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
ms.openlocfilehash: ba6a0d23eea4d8d555115950fcd54a5e4f6a8bde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193977"
---
# <a name="linker-tools-error-lnk1237"></a>链接器工具错误 LNK1237

在代码生成过程中，编译器引入了对用/GL 编译的模块 "module" 中定义的符号 "symbol" 的引用

在代码生成过程中，编译器不应引入以后解析 **为编译后** 的定义的符号。 `symbol` 是一个符号，该符号已引入，稍后解析为使用 **/gl** 编译的定义。

有关详细信息，请参阅 [/GL（全程序优化）](../../build/reference/gl-whole-program-optimization.md)。

若要解析 LNK1237，请不要使用 **/gl** 编译符号，也不要使用 [/INCLUDE (强制符号引用)](../../build/reference/include-force-symbol-references.md) 强制引用符号。

## <a name="example"></a>示例

下面的示例生成 LNK1237。 若要解决此错误，请不要在 LNK1237_a .cpp 中初始化数组，并将 **/include： __chkstk** 添加到 link 命令。

```cpp
// LNK1237_a.cpp
int main() {
   char c[5000] = {0};
}
```

```cpp
// LNK1237_b.cpp
// compile with: /GS- /GL /c LNK1237_a.cpp
// processor: x86
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)
extern "C" void _chkstk(size_t s) {}
```

---
description: 了解详细信息：链接器工具警告 LNK4224
title: 链接器工具警告 LNK4224
ms.date: 11/04/2016
f1_keywords:
- LNK4224
helpviewer_keywords:
- LNK4224
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
ms.openlocfilehash: 35cae5c46b91493a40d4d52650f781010f6d6379
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327911"
---
# <a name="linker-tools-warning-lnk4224"></a>链接器工具警告 LNK4224

> 不再支持 *选项*，掉

## <a name="remarks"></a>备注

指定和忽略了无效的过时链接器选项。

例如，如果/comment 指令出现在 .obj 中，则可能会发生 LNK4224。/Comment 指令将通过 [注释 (C/c + +) ](../../preprocessor/comment-c-cpp.md) 杂注添加，使用不推荐使用的 exestr 选项。 使用 dumpbin [/all](../../build/reference/all.md) 查看 .obj 文件中的链接器指令。

如果可能，请修改 .obj 的源，并删除杂注。 如果忽略此警告，则可能是使用 **/clr： pure** 编译的可执行文件不会按预期运行。 **/Clr： pure** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

## <a name="example"></a>示例

下面的示例生成 LNK4224。

```cpp
// LNK4224.cpp
// compile with: /c /Zi
// post-build command: link LNK4224.obj /debug /debugtype:map
int main () {
   return 0;
}
```

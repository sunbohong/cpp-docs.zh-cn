---
title: 编译器警告（等级 1）C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: 38a05c04181efb95ec3e7549c40056b8d223e128
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90685549"
---
# <a name="compiler-warning-level-1-c4744"></a>编译器警告（等级 1）C4744

"var" 在 "file1" 和 "file2" 中具有不同的类型： "type1" 和 "type2"

在两个文件中引用或定义的外部变量在这些文件中具有不同的类型。  若要解决此问题，请使类型定义相同，或者更改其中一个文件中的变量名称。

仅在用/GL 编译文件时发出 C4744  有关详细信息，请参阅 [/GL（全程序优化）](../../build/reference/gl-whole-program-optimization.md)。

> [!NOTE]
> C4744 通常在 C (不是 c + +) 文件中出现，因为在 c + + 中，变量名称是使用类型信息修饰的。  如果下面的示例 () 编译为 c + +，则会出现链接器错误 LNK2019。

## <a name="examples"></a>示例

此示例包含第一个定义。

```c
// C4744.c
// compile with: /c /GL
int global;
```

下面的示例生成 C4744。

```c
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```

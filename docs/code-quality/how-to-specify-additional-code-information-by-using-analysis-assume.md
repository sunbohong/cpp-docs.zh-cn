---
description: 详细了解如何使用 _Analysis_assume_ 指定其他代码信息。
title: 使用 _Analysis_assume_ 代码分析提示
ms.date: 12/16/2020
ms.topic: conceptual
f1_keywords:
- _Analysis_assume_
helpviewer_keywords:
- _Analysis_assume_
ms.openlocfilehash: f4244a896d4334cb6c5e857e63b39be0cd53b08b
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645119"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume_"></a>如何使用指定其他代码信息 `_Analysis_assume_`

您可以为 C/c + + 代码的代码分析工具提供提示，以帮助分析过程并减少警告。 若要提供其他信息，请使用以下 function 宏：

`_Analysis_assume( expr )`

*`expr`* -假定为 true 的任何表达式。

代码分析工具假定表达式所表示的条件 *`expr`* 在函数显示的点处为 true。 并且，在 *`expr`* 被更改之前（例如，通过赋值给变量），它将保持为 true。

> [!NOTE]
> `_Analysis_assume_` 不会影响代码优化。 在代码分析工具外部， `_Analysis_assume_` 定义为 "无操作"。

## <a name="example"></a>示例

下面的代码使用 `_Analysis_assume_` 来更正代码分析警告 [C6388](../code-quality/c6388.md)：

```cpp
#include <windows.h>
#include <codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume_(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>另请参阅

- [__assume](../intrinsics/assume.md)

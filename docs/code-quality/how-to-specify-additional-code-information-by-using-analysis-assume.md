---
description: 了解有关详细信息，请参阅如何：使用 _Analysis_assume 指定其他代码信息
title: 使用 _Analysis_assume 代码分析提示
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
ms.openlocfilehash: 1960fae929f1bd0ffbac4979b76541fd0d396e42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151549"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume"></a>如何：使用 _Analysis_assume 指定其他代码信息

您可以为 C/c + + 代码的代码分析工具提供提示，以帮助分析过程并减少警告。 若要提供其他信息，请使用以下函数：

`_Analysis_assume(`  `expr`  `)`

`expr` -假定为 true 的任何表达式。

代码分析工具假定表达式所表示的条件在函数显示的点处为 true，并在更改表达式（例如，通过赋值给变量时）时保持为 true。

> [!NOTE]
> `_Analysis_assume` 不会影响代码优化。 在代码分析工具外部， `_Analysis_assume` 定义为 "无操作"。

## <a name="example"></a>示例

下面的代码使用 `_Analysis_assume` 来更正代码分析警告 [C6388](../code-quality/c6388.md)：

```cpp
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>请参阅

- [__assume](../intrinsics/assume.md)

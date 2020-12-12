---
description: '了解详细信息：复合语句 (块) '
title: 复合语句（块）
ms.date: 11/04/2016
f1_keywords:
- '}'
- '{'
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
ms.openlocfilehash: 7defb11a30466949d5a9ca5e86ca1e865fbfe4fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318008"
---
# <a name="compound-statements-blocks"></a>复合语句（块）

复合语句由零个或多个括在大括号中的语句组成 (**{}**) 。 可以在任何期望语句出现的位置使用复合语句。 复合语句通常称为“块”。

## <a name="syntax"></a>语法

```
{ [ statement-list ] }
```

## <a name="remarks"></a>备注

下面的示例使用复合语句作为语句的 *语句* 部分 **`if`** (参阅 [if 语句](../cpp/if-else-statement-cpp.md) 获取有关语法) 的详细信息：

```cpp
if( Amount > 100 )
{
    cout << "Amount was too large to handle\n";
    Alert();
}
else
{
    Balance -= Amount;
}
```

> [!NOTE]
> 由于声明是一个语句，因此声明可以是 *语句列表* 中的语句之一。 因此，复合语句内声明的名称（而不是显式声明为静态的名称）具有局部范围和（对于对象）生存期。 有关名称和本地范围的处理的详细信息，请参阅 [作用域](../cpp/scope-visual-cpp.md) 。

## <a name="see-also"></a>请参阅

[C + + 语句概述](../cpp/overview-of-cpp-statements.md)

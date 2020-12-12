---
description: '了解详细信息： Charizing 运算符 ( # @ ) '
title: 字符化运算符 (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 6d04aa24c75153957bd6fd09824f4e94e36fd38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300861"
---
# <a name="charizing-operator-"></a>字符化运算符 (#@)

**Microsoft 专用**

charizing 运算符只能与宏的自变量一起使用。 如果 `#@` 在宏的定义中的形参前面加上实参，则在展开宏时，实参将括在单引号中并被视为一个字符。 例如：

```cpp
#define makechar(x)  #@x
```

导致以下语句

```cpp
a = makechar(b);
```

扩展为

```cpp
a = 'b';
```

单引号字符 (`'`) 不能与 charizing 运算符一起使用。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[预处理器运算符](../preprocessor/preprocessor-operators.md)

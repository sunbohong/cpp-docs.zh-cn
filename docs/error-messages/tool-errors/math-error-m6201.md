---
description: 了解详细信息：数学错误 M6201
title: 数学错误 M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 03588b7eed580b95cb263f6e4d71f5a793f4d392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244311"
---
# <a name="math-error-m6201"></a>数学错误 M6201

"function"： _DOMAIN 错误

给定函数的参数超出了该函数的合法输入值的域。

## <a name="example"></a>示例

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

此错误将调用函数 `_matherr` ，其函数名称、参数的参数和错误类型。 您可以重写此 `_matherr` 函数，以自定义对某些运行时浮点算术错误的处理。

---
description: 了解详细信息： STACKSIZE
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: b5d52bccc09979084b9023d380e86fe90e4def32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230336"
---
# <a name="stacksize"></a>STACKSIZE

设置堆栈的大小（以字节为单位）。

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>备注

设置堆栈的等效方法是使用 [堆栈分配](stack-stack-allocations.md) (/STACK) 选项。 有关 *保留* 和参数的详细信息，请参阅有关该选项的文档 `commit` 。

此选项对 Dll 不起作用。

## <a name="see-also"></a>请参阅

[Module-Definition 语句的规则](rules-for-module-definition-statements.md)

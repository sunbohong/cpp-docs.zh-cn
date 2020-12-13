---
description: 详细了解：编译器警告 (级别 4) C4235
title: 编译器警告（等级 4）C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 011586efb311cab1da5cd4452bbbc03a942a5045
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334883"
---
# <a name="compiler-warning-level-4-c4235"></a>编译器警告（等级 4）C4235

使用了非标准扩展：此体系结构不支持关键字 "关键字"

编译器不支持所使用的关键字。

此警告会自动提升为错误。 如果要修改此行为，请使用 [#pragma 警告](../../preprocessor/warning.md)。 例如，若要使 C4235 成为第2级警告，请使用以下代码行

```cpp
#pragma warning(2:4235)
```

在源代码文件中。

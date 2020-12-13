---
description: 详细了解：编译器警告 (级别 4) C4233
title: 编译器警告（等级 4）C4233
ms.date: 10/25/2017
f1_keywords:
- C4233
helpviewer_keywords:
- C4233
ms.assetid: 9aa51fc6-8ef3-43b5-bafb-c9333cf60de3
ms.openlocfilehash: 3e797bcefeaeee615014ea8e0bd109e4cf4ffbef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344011"
---
# <a name="compiler-warning-level-4-c4233"></a>编译器警告（等级 4）C4233

> 使用了非标准扩展：仅在 c + + 中 *支持关键字关键字*，而不支持 c

编译器将源代码编译为 C 而不是 c + +，而使用的关键字只在 c + + 中有效。 如果源文件的扩展名为 .c 或使用 [/tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md)，则编译器会将源文件编译为 c。

此警告会自动提升为错误。 如果要修改此行为，请使用 [#pragma 警告](../../preprocessor/warning.md)。 例如，若要将 C4233 添加到第4级警告问题，请将以下代码行添加到源代码文件中：

```cpp
#pragma warning(4:4233)
```

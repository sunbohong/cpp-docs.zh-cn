---
description: 详细了解：编译器警告 (级别 4) C4234
title: 编译器警告（等级 4）C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 98a3f5bc2c13dec3822342a669f7c9de3dc452fc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334899"
---
# <a name="compiler-warning-level-4-c4234"></a>编译器警告（等级 4）C4234

使用了非标准扩展：保留 "关键字" 关键字供将来使用

编译器尚未实现所使用的关键字。

此警告会自动提升为错误。 如果要修改此行为，请使用 [#pragma 警告](../../preprocessor/warning.md)。 例如，若要使 C4234 成为第4级警告问题，

```cpp
#pragma warning(2:4234)
```

在源代码文件中。

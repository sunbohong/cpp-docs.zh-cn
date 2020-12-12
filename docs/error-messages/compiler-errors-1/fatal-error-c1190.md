---
description: 了解详细信息：严重错误 C1190
title: 错误 C1190
ms.date: 11/04/2016
f1_keywords:
- C1190
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
ms.openlocfilehash: e351a04d548816999d61973276203d34745c0a75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123599"
---
# <a name="fatal-error-c1190"></a>错误 C1190

托管目标代码需要“/clr”选项

你当前使用的是 CLR 构造，但未指定 **/clr**。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

下面的示例生成 C1190：

```cpp
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```

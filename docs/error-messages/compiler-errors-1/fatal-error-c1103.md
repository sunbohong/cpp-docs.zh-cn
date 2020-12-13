---
description: 了解详细信息：严重错误 C1103
title: 错误 C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: 7e49d4f4420fc202f54a580c194244d24a4d181c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144919"
---
# <a name="fatal-error-c1103"></a>错误 C1103

导入 progid 时遇到错误：“message”

导入类型库时编译器检测到问题。  例如，你不能使用 progid 指定类型库，同时还指定 `no_registry`。

有关详细信息，请参阅 [#import 指令](../../preprocessor/hash-import-directive-cpp.md)。

下面的示例生成 C1103：

```cpp
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```

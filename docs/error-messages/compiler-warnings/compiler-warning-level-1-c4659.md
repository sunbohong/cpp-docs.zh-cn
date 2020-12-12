---
description: 了解详细信息：编译器警告 (等级 1) C4659
title: 编译器警告（等级 1）C4659
ms.date: 11/04/2016
f1_keywords:
- C4659
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
ms.openlocfilehash: 05ec1e088e00b184ba083b6b197afc6041707449
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318803"
---
# <a name="compiler-warning-level-1-c4659"></a>编译器警告（等级 1）C4659

\#pragma "pragma"：使用保留段 "段" 时出现未定义的行为，请使用 #pragma 注释 (链接器 ... ) 

使用 .drectve 选项将选项传递到链接器。 改为使用杂注 [注释](../../preprocessor/comment-c-cpp.md) 传递链接器选项。

```cpp
// C4659.cpp
// compile with: /W1 /LD
#pragma code_seg(".drectve")   // C4659
```

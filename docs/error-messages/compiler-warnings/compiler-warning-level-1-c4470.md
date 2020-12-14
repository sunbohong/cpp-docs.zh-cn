---
description: 了解详细信息：编译器警告 (等级 1) C4470
title: 编译器警告（等级 1）C4470
ms.date: 11/04/2016
f1_keywords:
- C4470
helpviewer_keywords:
- C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
ms.openlocfilehash: 6fe01782fbd2151175bc1da59afa8bd73fa5648d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310973"
---
# <a name="compiler-warning-level-1-c4470"></a>编译器警告（等级 1）C4470

在/clr 下忽略了浮点控制杂注

Float 控件杂注：

- [fenv_access](../../preprocessor/fenv-access.md)

- [float_control](../../preprocessor/float-control.md)

- [fp_contract](../../preprocessor/fp-contract.md)

在 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)下不起作用。

下面的示例生成 C4470：

```cpp
// C4470.cpp
// compile with: /clr /W1 /LD
#pragma float_control(except, on)   // C4470
```

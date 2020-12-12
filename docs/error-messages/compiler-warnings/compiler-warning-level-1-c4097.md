---
description: 了解详细信息：编译器警告 (等级 1) C4097
title: 编译器警告（等级 1）C4097
ms.date: 11/04/2016
f1_keywords:
- C4097
helpviewer_keywords:
- C4097
ms.assetid: 2525be51-fac2-43b2-b57c-3bbf1a2268f7
ms.openlocfilehash: 77c9cf9afd3601597418e6151518c6ced4a472c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272267"
---
# <a name="compiler-warning-level-1-c4097"></a>编译器警告（等级 1）C4097

杂注参数应是“restore”或者“off”

给杂注传递了无效的值。

下面的示例生成 C4097：

```cpp
// C4097.cpp
// compile with: /W1
#pragma runtime_checks("",test)   // C4097
// try the following line instead
// #pragma runtime_checks("",off)

int main() {
}
```

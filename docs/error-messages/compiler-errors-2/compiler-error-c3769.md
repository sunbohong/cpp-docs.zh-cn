---
description: 了解更多：编译器错误 C3769
title: 编译器错误 C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 5ed980ed75997637a59c6f2a0f864a20297e9a97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291696"
---
# <a name="compiler-error-c3769"></a>编译器错误 C3769

"type"：嵌套类不能与直接封闭类同名

嵌套类不能与直接封闭类具有相同的名称。

## <a name="example"></a>示例

下面的示例生成 C3769。

```cpp
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```

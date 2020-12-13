---
description: 了解更多：编译器错误 C3295
title: 编译器错误 C3295
ms.date: 11/04/2016
f1_keywords:
- C3295
helpviewer_keywords:
- C3295
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
ms.openlocfilehash: 55fab24088690f5d5bb92da0cc55442bcebeed01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144620"
---
# <a name="compiler-error-c3295"></a>编译器错误 C3295

“#pragma pragma”只能在全局范围或命名空间范围上使用

部分杂注不能在函数中使用。  有关详细信息，请参阅 [Pragma 指令和 __Pragma 关键字](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 。

## <a name="example"></a>示例

以下示例生成 C3295。

```cpp
// C3295.cpp
int main() {
   #pragma managed   // C3295
}
```

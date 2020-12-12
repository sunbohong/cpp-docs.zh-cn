---
description: 了解详细信息：编译器警告 (等级 1) C4006
title: 编译器警告（等级 1）C4006
ms.date: 11/04/2016
f1_keywords:
- C4006
helpviewer_keywords:
- C4006
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
ms.openlocfilehash: 1d0b38e2ac3d224f26a0a52ac2d7f2343a1f955d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335979"
---
# <a name="compiler-warning-level-1-c4006"></a>编译器警告（等级 1）C4006

\#undef 应为标识符

`#undef` 指令未指定要取消定义的标识符。 指令被忽略。 若要解决此警告，请确保指定一个标识符。 以下示例生成 C4006：

```cpp
// C4006.cpp
// compile with: /W1
#undef   // C4006

// try..
// #undef TEST

int main() {
}
```

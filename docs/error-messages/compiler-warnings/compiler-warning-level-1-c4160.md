---
description: 了解详细信息：编译器警告 (等级 1) C4160
title: 编译器警告（等级 1）C4160
ms.date: 08/27/2018
f1_keywords:
- C4160
helpviewer_keywords:
- C4160
ms.assetid: a9610cb7-cac4-4a74-8b4e-049030ebb92b
ms.openlocfilehash: afb9a0a30376a0e0b1c59b89e98a131ab5889017
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267191"
---
# <a name="compiler-warning-level-1-c4160"></a>编译器警告（等级 1）C4160

> #<a name="pragma-pop--did-not-find-previously-pushed-identifier-identifier"></a>pragma (pop,... ) ：找不到先前推送的标识符 "*identifier*"

## <a name="remarks"></a>备注

源代码中的 pragma 语句试图弹出尚未入栈的标识符。 要避免此警告，请确保要弹出的标识符已正确入栈。

## <a name="example"></a>示例

下面的示例生成 C4160，并演示如何修复此问题：

```cpp
// C4160.cpp
// compile with: /W1
#pragma pack(push)

#pragma pack(pop, id)   // C4160
// use identifier when pushing to resolve the warning
// #pragma pack(push, id)

int main() {
}
```

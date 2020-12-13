---
description: 了解更多：编译器错误 C3363
title: 编译器错误 C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: b746a4c1e220ee05f96f3f2ceae524d5747550d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335031"
---
# <a name="compiler-error-c3363"></a>编译器错误 C3363

“type”：“typeid”只能应用于类型

[typeid](../../extensions/typeid-cpp-component-extensions.md) 运算符未正确使用。

## <a name="example"></a>示例

下面的示例生成 C3363。

```cpp
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```

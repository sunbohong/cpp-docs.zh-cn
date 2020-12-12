---
description: 了解详细信息：编译器警告 (等级 1) C4178
title: 编译器警告（等级 1）C4178
ms.date: 11/04/2016
f1_keywords:
- C4178
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
ms.openlocfilehash: 87876a70f638c3c8d98c20a3297482d317256d78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266749"
---
# <a name="compiler-warning-level-1-c4178"></a>编译器警告（等级 1）C4178

对于 switch 表达式的类型而言，case 常量“constant”过大

表达式中的 case 常量不 **`switch`** 符合向其分配的类型。

## <a name="example"></a>示例

```cpp
// C4178.cpp
// compile with: /W1
int main()
{
    int i;  // maximum size of unsigned long int is 4294967295
    switch( i )
    {
        case 4294967295:   // OK
            break;
        case 4294967296:   // C4178
            break;
    }
}
```

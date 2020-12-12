---
description: 了解详细信息：编译器警告 (等级 1) C4550
title: 编译器警告（等级 1）C4550
ms.date: 11/04/2016
f1_keywords:
- C4550
helpviewer_keywords:
- C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
ms.openlocfilehash: 8edb7744f522312933bcf9d273982e591918dac2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265969"
---
# <a name="compiler-warning-level-1-c4550"></a>编译器警告（等级 1）C4550

表达式计算结果为缺少参数列表的函数

指向函数的取消引用的指针缺少参数列表。

## <a name="example"></a>示例

```cpp
// C4550.cpp
// compile with: /W1
bool f()
{
   return true;
}

typedef bool (*pf_t)();

int main()
{
   pf_t pf = f;
   if (*pf) {}  // C4550
   return 0;
}
```

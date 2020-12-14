---
description: 了解详细信息：编译器警告 (等级 1) C4286
title: 编译器警告（等级 1）C4286
ms.date: 11/04/2016
f1_keywords:
- C4286
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
ms.openlocfilehash: 52a17f66c20efc52f3d12da3a9cfbd041e5f262d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311768"
---
# <a name="compiler-warning-level-1-c4286"></a>编译器警告（等级 1）C4286

"type1"：由基类 ( "type2" 捕获行号上 ) 

指定的异常类型由上一个处理程序处理。 第二个 catch 的类型派生自第一个的类型。 基类捕获派生类的异常的异常。

## <a name="example"></a>示例

```cpp
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```

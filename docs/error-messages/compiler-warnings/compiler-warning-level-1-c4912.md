---
description: 了解详细信息：编译器警告 (等级 1) C4912
title: 编译器警告（等级 1）C4912
ms.date: 11/04/2016
f1_keywords:
- C4912
helpviewer_keywords:
- C4912
ms.assetid: ba1f1a66-8c20-4792-9ac8-43e49f729ae2
ms.openlocfilehash: 85300716894f9c69815bf40ebb7d93ee29d8684b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291436"
---
# <a name="compiler-warning-level-1-c4912"></a>编译器警告（等级 1）C4912

“attribute”：在嵌套 UDT 上，特性有未定义的行为

可以忽略应用于嵌套 UDT（用户定义的类型，这可能为 typedef、union 或 struct）的特性。

下面的代码演示了将如何生成此警告：

```cpp
// C4912.cpp
// compile with: /W1
#include <windows.h>
[emitidl, module(name="xx")];

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface IMy
{
};

[coclass, default(IMy), appobject, uuid("00000000-0000-0000-0000-000000000001")]
class CMy : public IMy
{
   [export, v1_enum] typedef enum myEnum { k3_1 = 1, k3_2 = 2 } myEnumv;   // C4912
};
int main()
{
}
```

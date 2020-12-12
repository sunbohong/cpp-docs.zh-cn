---
description: 了解更多：编译器错误 C2569
title: 编译器错误 C2569
ms.date: 11/04/2016
f1_keywords:
- C2569
helpviewer_keywords:
- C2569
ms.assetid: 092bed1e-f631-436c-9586-7750629f6fac
ms.openlocfilehash: bf6b0670cfd90cadc939010a75f9faa9c7c25c30
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209030"
---
# <a name="compiler-error-c2569"></a>编译器错误 C2569

"EnumOrUnion"：枚举/联合不能用作基类

如果必须从指定的联合或枚举派生类型，请将联合或枚举更改为类或结构。

下面的示例生成 C2569：

```cpp
// C2569.cpp
// compile with: /c
union ubase {};
class cHasPubUBase : public ubase {};   // C2569
// OK
struct sbase {};
class cHasPubUBase : public sbase {};
```

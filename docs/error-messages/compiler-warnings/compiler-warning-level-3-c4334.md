---
description: 详细了解：编译器警告 (等级 3) C4334
title: 编译器警告（等级 3）C4334
ms.date: 11/04/2016
f1_keywords:
- C4334
helpviewer_keywords:
- C4334
ms.assetid: d845857f-bc95-4faf-a079-626a0cf935ba
ms.openlocfilehash: 3c7a84efc3c98779c5b50dc1b3fb28e687f856eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344024"
---
# <a name="compiler-warning-level-3-c4334"></a>编译器警告（等级 3）C4334

"operator"：32位移位的结果被隐式转换为64位 (是否需要64位移位？ ) 

32位移位的结果被隐式转换为64位，并且编译器怀疑需要64位移位。  若要解决此警告，请使用64位 shift，或将移位结果显式转换为64位。

## <a name="example"></a>示例

下面的示例生成 C4334。

```cpp
// C4334.cpp
// compile with: /W3 /c
void SetBit(unsigned __int64 *p, int i) {
   *p |= (1 << i);   // C4334
   *p |= (1i64 << i);   // OK
}
```

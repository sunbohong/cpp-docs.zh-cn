---
description: 了解更多：编译器错误 C3126
title: 编译器错误 C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 7084359ae0be412ccb36e9a634cc72848f1c8daa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345454"
---
# <a name="compiler-error-c3126"></a>编译器错误 C3126

无法在托管类型 "type" 的内部定义联合 "union"

不能在托管类型内定义联合。

下面的示例生成 C3126：

```cpp
// C3126_2.cpp
// compile with: /clr /c
ref class Test
{
   union x
   {   // C3126
      int a;
      int b;
   };
};
```

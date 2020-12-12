---
description: 了解更多：编译器错误 C2364
title: 编译器错误 C2364
ms.date: 11/04/2016
f1_keywords:
- C2364
helpviewer_keywords:
- C2364
ms.assetid: 4f550571-94b5-42ca-84cb-663fecbead44
ms.openlocfilehash: 56d774a3ba681ec8cb3ab7bcf491766e30d6ba6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194866"
---
# <a name="compiler-error-c2364"></a>编译器错误 C2364

"type"：自定义特性的非法类型

自定义特性的命名参数仅限于编译时常量。 例如，整型类型 (int、char 等 ) 、System：： Type ^ 和 System：： Object ^。

## <a name="example"></a>示例

下面的示例生成 C2364。

```cpp
// c2364.cpp
// compile with: /clr /c
using namespace System;

[attribute(AttributeTargets::All)]
public ref struct ABC {
public:
   // Delete the following line to resolve.
   ABC( Enum^ ) {}   // C2364
   ABC( int ) {}   // OK
};
```

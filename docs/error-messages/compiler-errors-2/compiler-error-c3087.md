---
description: 了解更多：编译器错误 C3087
title: 编译器错误 C3087
ms.date: 11/04/2016
f1_keywords:
- C3087
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
ms.openlocfilehash: 0700f10711610e09a797c647e0e107a3ef41f115
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116361"
---
# <a name="compiler-error-c3087"></a>编译器错误 C3087

“named_argument”：对“attribute”的调用已将此成员初始化

在同一值的未命名参数所在的特性快中指定了已命名参数。 仅指定一个已命名或未命名参数。

## <a name="example"></a>示例

下面的示例生成 C3087。

```cpp
// C3087.cpp
// compile with: /c
[idl_quote("quote1", text="quote2")];   // C3087
[idl_quote(text="quote3")];   // OK
[idl_quote("quote4")];   // OK
```

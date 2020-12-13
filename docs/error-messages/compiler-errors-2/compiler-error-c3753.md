---
description: 了解更多：编译器错误 C3753
title: 编译器错误 C3753
ms.date: 11/04/2016
f1_keywords:
- C3753
helpviewer_keywords:
- C3753
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
ms.openlocfilehash: a6a427001d1d9f0cfbcb1994e996208ee9ef2e2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340159"
---
# <a name="compiler-error-c3753"></a>编译器错误 C3753

不允许使用泛型属性

泛型参数列表只能出现在托管类、结构或函数上。

有关详细信息，请参阅 [泛型](../../extensions/generics-cpp-component-extensions.md) 和 [属性](../../extensions/property-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3753。

```cpp
// C3753.cpp
// compile with: /clr /c
ref struct A {
   generic <typename T>
   property int i;   // C3753 error
};
```

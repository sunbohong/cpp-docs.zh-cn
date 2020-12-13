---
description: 了解更多：编译器错误 C2891
title: 编译器错误 C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: e546340d0ba035da50dd36b18b870b565b6e1bc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337434"
---
# <a name="compiler-error-c2891"></a>编译器错误 C2891

"parameter"：无法获取模板参数的地址

你无法获取模板参数的地址，除非它是左值。 类型参数不左值，因为它们没有地址。 不左值的模板参数列表中的非类型值也没有地址。 这是导致编译器错误 C2891 的代码示例，因为作为模板参数传递的值是模板参数的编译器生成的副本。

```
template <int i> int* f() { return &i; }
```

左值的模板参数（如引用类型）可以采用其地址。

```
template <int& r> int* f() { return &r; }
```

若要更正此错误，请不要采用模板参数的地址，除非它是左值。

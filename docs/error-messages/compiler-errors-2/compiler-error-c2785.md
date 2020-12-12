---
description: 了解更多：编译器错误 C2785
title: 编译器错误 C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: f40b652e30b30f0ef17426b547337352181383e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297897"
---
# <a name="compiler-error-c2785"></a>编译器错误 C2785

"declaration1" 和 "declaration2" 具有不同的返回类型

函数模板专用化的返回类型与主函数模板的返回类型不同。

### <a name="to-correct-this-error"></a>更正此错误

1. 检查函数模板的所有专用化是否一致。

## <a name="example"></a>示例

下面的示例生成 C2785：

```cpp
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```

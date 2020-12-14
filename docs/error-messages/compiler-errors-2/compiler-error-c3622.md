---
description: 了解更多：编译器错误 C3622
title: 编译器错误 C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 19c599fced524001f360a4ad462a9dbebbfb2fa3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223030"
---
# <a name="compiler-error-c3622"></a>编译器错误 C3622

"class"：声明为 "关键字" 的类不能实例化

尝试实例化标记为 [抽象](../../extensions/abstract-cpp-component-extensions.md)的类。 标记为的类 **`abstract`** 可以是基类，但无法对其进行实例化。

## <a name="example"></a>示例

下面的示例生成 C3622。

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```

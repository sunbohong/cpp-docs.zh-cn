---
description: 了解更多：编译器错误 C3072
title: 编译器错误 C3072
ms.date: 11/04/2016
f1_keywords:
- C3072
helpviewer_keywords:
- C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
ms.openlocfilehash: 02876a6983a47ce76f6e089bafde68af41034131
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320274"
---
# <a name="compiler-error-c3072"></a>编译器错误 C3072

> 运算符 "*operator-name*" 不能应用于 ref 类的实例

使用一元 *运算符名称* 运算符将 ref 类的实例转换为句柄类型

CLR 类型需要 CLR 运算符，而不是本机 (或标准) 运算符。  有关详细信息，请参阅 [跟踪引用运算符](../../extensions/tracking-reference-operator-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3072。

```cpp
// C3072.cpp
// compile with: /clr
ref class R {};

int main() {
   R r1;
   R^ r2 = &r1;   // C3072
   R^ r3 = %r1;   // OK
}
```

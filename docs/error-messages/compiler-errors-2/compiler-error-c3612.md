---
description: 了解更多：编译器错误 C3612
title: 编译器错误 C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 332d4bae940a0c98b148fd6ba951a4f51d1bee27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223095"
---
# <a name="compiler-error-c3612"></a>编译器错误 C3612

"type"：密封类不能是抽象的

默认情况下，使用定义的类型是 `value` 密封的，除非它实现其基的所有方法，否则类是抽象的。 密封的抽象类既不能是基类，也不能被实例化。

有关更多信息，请参阅[类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3612：

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```

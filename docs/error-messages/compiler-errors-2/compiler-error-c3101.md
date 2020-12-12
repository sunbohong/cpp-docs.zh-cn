---
description: 了解更多：编译器错误 C3101
title: 编译器错误 C3101
ms.date: 11/04/2016
f1_keywords:
- C3101
helpviewer_keywords:
- C3101
ms.assetid: 4f673766-d4f7-4632-94a5-d36a83f7f4b5
ms.openlocfilehash: e0c52eadd2af4b090b34f851d561535f360a7e59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116166"
---
# <a name="compiler-error-c3101"></a>编译器错误 C3101

命名特性参数 "field" 的表达式非法

初始化命名特性参数时，该值必须是编译时常量。

有关特性的详细信息，请参阅 [用户定义的属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3101。

```cpp
// C3101.cpp
// compile with: /clr /c
ref class AAttribute : System::Attribute {
public:
   int Field;
};

extern int i;

[assembly:A(Field = i)];   // C3101
[assembly:A(Field = 0)];   // OK
```

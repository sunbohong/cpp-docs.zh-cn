---
description: 详细了解：编译器警告 (等级 3) C4580
title: 编译器警告（等级 3）C4580
ms.date: 11/04/2016
f1_keywords:
- C4580
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
ms.openlocfilehash: 0bda682526081023c9208d548023f7c8b7316db9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294712"
---
# <a name="compiler-warning-level-3-c4580"></a>编译器警告（等级 3）C4580

[attribute] 已弃用；改为指定 System::Attribute 或 Platform::Metadata 作为基类

[[attribute](../../windows/attributes/attribute.md)] 不再是用于创建用户定义的属性的首选语法。 有关详细信息，请参阅 [User-Defined Attributes](../../extensions/user-defined-attributes-cpp-component-extensions.md)。 对于 CLR 代码，请从 `System::Attribute` 派生特性。 对于 Windows 运行时代码，请从 `Platform::Metadata` 派生特性。

## <a name="example"></a>示例

下面的示例将生成 C3454，并演示如何修复此错误。

```cpp
// C4580.cpp
// compile with: /W3 /c /clr
[attribute]   // C4580
public ref class Attr {
public:
   int m_t;
};

public ref class Attr2 : System::Attribute {
public:
   int m_t;
};
```

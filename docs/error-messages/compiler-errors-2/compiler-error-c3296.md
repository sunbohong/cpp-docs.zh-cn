---
description: 了解更多：编译器错误 C3296
title: 编译器错误 C3296
ms.date: 11/04/2016
f1_keywords:
- C3296
helpviewer_keywords:
- C3296
ms.assetid: fc4c9dcd-16cf-4eee-a1ac-c43e7c29e443
ms.openlocfilehash: 18c4cd35cda096cbb9e335e30da8d0631d247f60
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144607"
---
# <a name="compiler-error-c3296"></a>编译器错误 C3296

“property”：已存在同名属性

编译器遇到具有相同名称的多个属性。 类型中的每个属性均必须具有唯一名称。

有关详细信息，请参阅 [property](../../extensions/property-cpp-component-extensions.md)。

## <a name="example"></a>示例

以下示例生成 C3296。

```cpp
// C3296.cpp
// compile with: /clr /c
using namespace System;

ref class R {
public:
   property int MyProp[int] { int get(int); }

   property String^ MyProp[int] { void set(int, String^); }   // C3296
};
```

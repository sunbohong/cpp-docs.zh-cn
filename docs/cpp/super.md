---
description: 了解详细信息： `__super`
title: __super
ms.date: 11/04/2016
f1_keywords:
- __super_cpp
helpviewer_keywords:
- __super keyword [C++]
ms.assetid: f0957c31-9256-405b-b402-cad182404b5f
ms.openlocfilehash: 30f2733abbd4599deabfa989d72b099c929cb050
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178129"
---
# `__super`

**Microsoft 专用**

允许您显式说明要为正在重写的函数调用基类实现。

## <a name="syntax"></a>语法

```
__super::member_function();
```

## <a name="remarks"></a>备注

在重载决策阶段将考虑所有可访问的基类方法，可提供最佳匹配项的函数就是调用的函数。

**`__super`** 只能出现在成员函数体中。

**`__super`** 不能与 using 声明一起使用。 有关详细信息，请参阅 [Using 声明](../cpp/using-declaration.md) 。

引入用于注入代码的 [特性](../windows/attributes/attributes-alphabetical-reference.md) 后，你的代码可能包含一个或多个基类，这些基类的名称可能不知道，但包含你希望调用的方法。

## <a name="example"></a>示例

```cpp
// deriv_super.cpp
// compile with: /c
struct B1 {
   void mf(int) {}
};

struct B2 {
   void mf(short) {}

   void mf(char) {}
};

struct D : B1, B2 {
   void mf(short) {
      __super::mf(1);   // Calls B1::mf(int)
      __super::mf('s');   // Calls B2::mf(char)
   }
};
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)

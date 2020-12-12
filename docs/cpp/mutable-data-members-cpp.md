---
description: '了解有关以下内容的详细信息：可变数据成员 (c + +) '
title: 可变数据成员 (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: a288b382b456fa313c49832bd2d13aaceb269be9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313809"
---
# <a name="mutable-data-members-c"></a>可变数据成员 (C++)

此关键字只能应用于类的非静态和非常量数据成员。 如果声明了某个数据成员 **`mutable`** ，则可以通过成员函数向此数据成员赋值，这是合法的 **`const`** 。

## <a name="syntax"></a>语法

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>备注

例如，以下代码将在编译时不会出错 `m_accessCount` ，因为已将声明为 **`mutable`** ，因此 `GetFlag` 即使 `GetFlag` 是常量成员函数，也可以修改它们。

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>请参阅

[关键字](../cpp/keywords-cpp.md)

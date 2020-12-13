---
description: 了解更多：编译器错误 C3908
title: 编译器错误 C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 67258f9f5946d180af9a270b931f88f263238856
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144165"
---
# <a name="compiler-error-c3908"></a>编译器错误 C3908

访问级别的限制低于 "构造"

 (获取或设置) 的属性访问器方法不能具有比在属性本身上指定的访问权限更少的访问限制。  同样，对于事件访问器方法。

有关详细信息，请参阅 [属性](../../extensions/property-cpp-component-extensions.md) 和 [事件](../../extensions/event-cpp-component-extensions.md)。

下面的示例生成 C3908：

```cpp
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```

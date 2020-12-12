---
description: 了解更多：编译器错误 C3803
title: " C3803"
ms.date: 11/04/2016
f1_keywords:
- C3803
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
ms.openlocfilehash: 23b3c9f38470bca471910bb31f7a0acbdf14693e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291553"
---
# <a name="compiler-error-c3803"></a> C3803

"property"：属性的类型与它的某个访问器 "访问器" 的类型不兼容

使用 [属性](../../cpp/property-cpp.md) 定义的属性的类型与它的某个访问器函数的返回类型不匹配。

下面的示例生成 C3803：

```cpp
// C3803.cpp
struct A
{
   __declspec(property(get=GetIt)) int i;
   char GetIt()
   {
      return 0;
   }

   /*
   // try the following definition instead
   int GetIt()
   {
      return 0;
   }
   */
}; // C3803

int main()
{
}
```

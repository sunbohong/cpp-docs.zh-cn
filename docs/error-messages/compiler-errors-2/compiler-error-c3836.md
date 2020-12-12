---
description: 了解更多：编译器错误 C3836
title: 编译器错误 C3836
ms.date: 11/04/2016
f1_keywords:
- C3836
helpviewer_keywords:
- C3836
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
ms.openlocfilehash: c7e05bbf95facf5b8552b4442138cc38b86703c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180872"
---
# <a name="compiler-error-c3836"></a>编译器错误 C3836

静态构造函数不允许有成员初始值设定项列表

托管类不能具有同样具有成员初始化列表的静态构造函数。 静态类构造函数由公共语言运行时调用，用于执行类初始化，初始化静态数据成员。

## <a name="example"></a>示例

下面的示例生成 C3836：

```cpp
// C3836a.cpp
// compile with: /clr
ref class M
{
   static int s_i;

public:
   static M() :  s_i(1234)   // C3836, delete initializer to resolve
   {
   }
};

int main()
{
}
```

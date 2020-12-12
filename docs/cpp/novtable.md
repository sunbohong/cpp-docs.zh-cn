---
description: 了解详细信息： novtable
title: novtable
ms.date: 11/04/2016
f1_keywords:
- novtable_cpp
helpviewer_keywords:
- novtable __declspec keyword
- __declspec keyword [C++], novtable
ms.assetid: cfef09c5-8c1e-4b14-8a72-7d726ded4484
ms.openlocfilehash: 2c818d07603e294f760b768861ce7e7a3e02894b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146193"
---
# <a name="novtable"></a>novtable

**Microsoft 专用**

这是一个 **`__declspec`** 扩展属性。

这种形式的 **`__declspec`** 可应用于任何类声明，但仅应用于纯接口类，即永远不会自行实例化的类。 **`__declspec`** 停止编译器生成代码以初始化 vfptr 构造函数中的) 和类的析构 (函数。 在许多情况下，这将移除对与类关联的 vtable 的唯一引用，因此链接器将移除它。 使用这种形式的 **`__declspec`** 可能导致代码大小大幅降低。

如果尝试实例化标记为的类 **`novtable`** ，然后访问类成员，则将收到 (AV) 的访问冲突。

## <a name="example"></a>示例

```cpp
// novtable.cpp
#include <stdio.h>

struct __declspec(novtable) X {
   virtual void mf();
};

struct Y : public X {
   void mf() {
      printf_s("In Y\n");
   }
};

int main() {
   // X *pX = new X();
   // pX->mf();   // Causes a runtime access violation.

   Y *pY = new Y();
   pY->mf();
}
```

```Output
In Y
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[`__declspec`](../cpp/declspec.md)<br/>
[关键字](../cpp/keywords-cpp.md)

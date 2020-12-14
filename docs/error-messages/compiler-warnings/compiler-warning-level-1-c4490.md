---
description: 了解详细信息：编译器警告 (等级 1) C4490
title: 编译器警告（等级 1）C4490
ms.date: 11/04/2016
f1_keywords:
- C4490
helpviewer_keywords:
- C4490
ms.assetid: f9b03ecf-41a1-4f4d-a74c-2c1e88234ccc
ms.openlocfilehash: 8216075e481e85f362e85cf158375a6d8b076772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310871"
---
# <a name="compiler-warning-level-1-c4490"></a>编译器警告（等级 1）C4490

"override"：重写说明符的用法不正确;"function" 与 ref 基类方法不匹配

重写说明符未正确使用。 例如，不能重写接口函数，而是实现它。

有关详细信息，请参阅 [重写说明符](../../extensions/override-specifiers-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C4490。

```cpp
// C4490.cpp
// compile with: /clr /c /W1

interface struct IFace {
   void Test();
};

ref struct Class1 : public IFace {
   virtual void Test() override {}   // C4490
   // try the following line instead
   // virtual void Test() {}
};
```

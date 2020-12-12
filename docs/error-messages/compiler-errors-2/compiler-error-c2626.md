---
description: 了解更多：编译器错误 C2626
title: 编译器错误 C2626
ms.date: 11/04/2016
f1_keywords:
- C2626
helpviewer_keywords:
- C2626
ms.assetid: 4c283ad0-251b-4571-bc18-468b9836746f
ms.openlocfilehash: 1a89d63d18fd029daa98ce1d248da24296ee2d4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123536"
---
# <a name="compiler-error-c2626"></a>编译器错误 C2626

“标识符”: 匿名结构或联合中不允许使用私有或受保护的数据成员

匿名结构或联合的成员必须具有公共访问。

以下示例生成 C2626：

```cpp
// C2626.cpp
int main() {
   union {
   protected:
      int j;     // C2626, j is protected
   private:
      int k;     // C2626, k is private
   };
}
```

若要解决此问题，请移除任何私有或受保护的标记：

```cpp
// C2626b.cpp
int main() {
   union {
   public:
      int i;   // OK, i is public
   };
}
```

---
description: 了解更多：编译器错误 C2825
title: 编译器错误 C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: fa72f915a77ec26e6da402ae8ff87ee380f1838c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194574"
---
# <a name="compiler-error-c2825"></a>编译器错误 C2825

var：在后跟 "：：" 时必须为类或命名空间

试图形成限定名称的尝试失败。

例如，确保你的代码不包含函数名称以：：开头的函数声明。

## <a name="example"></a>示例

下面的示例生成 C2825：

```cpp
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```

---
description: 了解更多：编译器错误 C2879
title: 编译器错误 C2879
ms.date: 11/04/2016
f1_keywords:
- C2879
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
ms.openlocfilehash: 6060678f71bf36d0af2e94e380a046ea7916ef05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194366"
---
# <a name="compiler-error-c2879"></a>编译器错误 C2879

"symbol"：只有现有命名空间才能由命名空间别名定义赋予备用名称

不能创建命名空间以外的符号的 [命名空间别名](../../cpp/namespaces-cpp.md#namespace_aliases) 。

下面的示例生成 C2879：

```cpp
// C2879.cpp
int main() {
   int i;
   namespace A = i;   // C2879 i is not a namespace
}
```

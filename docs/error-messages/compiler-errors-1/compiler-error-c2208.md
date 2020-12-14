---
description: 了解更多：编译器错误 C2208
title: 编译器错误 C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 76452c504e5f90857b15c5fc9250923705d3d20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245637"
---
# <a name="compiler-error-c2208"></a>编译器错误 C2208

"type"：没有使用此类型定义的成员

解析为类型名称的标识符位于聚合声明中，但编译器无法声明成员。

下面的示例生成 C2208：

```cpp
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```

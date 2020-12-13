---
description: 了解更多：编译器错误 C2870
title: 编译器错误 C2870
ms.date: 11/04/2016
f1_keywords:
- C2870
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
ms.openlocfilehash: 74e7f2de5cfbb5aca6bd653f5711b989de4ef326
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333772"
---
# <a name="compiler-error-c2870"></a>编译器错误 C2870

"name"：命名空间定义必须出现在文件范围内或紧跟在另一个命名空间定义中

你定义的命名空间 `name` 不正确。 命名空间必须在文件范围外 (所有块和类之外进行定义，) 或直接位于另一个命名空间中。

下面的示例生成 C2870：

```cpp
// C2870.cpp
// compile with: /c
int main() {
   namespace A { int i; };   // C2870
}
```

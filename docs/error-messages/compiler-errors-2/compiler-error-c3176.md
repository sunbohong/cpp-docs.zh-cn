---
description: 了解更多：编译器错误 C3176
title: 编译器错误 C3176
ms.date: 11/04/2016
f1_keywords:
- C3176
helpviewer_keywords:
- C3176
ms.assetid: 6cc8d602-8e15-47a7-b1b5-e93e5d50e271
ms.openlocfilehash: 8dda09ccbe6faa80d77f43c38b2c94427956cc3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242036"
---
# <a name="compiler-error-c3176"></a>编译器错误 C3176

"type"：不能声明局部值类型

类只能在全局范围内声明为值类型。

## <a name="example"></a>示例

下面的示例生成 C3176。

```cpp
// C3176.cpp
// compile with: /clr
int main () {
   enum class C {};   // C3176
}
```

---
title: 编译器错误 C2705
description: 描述 Microsoft C/c + + 编译器错误 C2705。
ms.date: 08/25/2020
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 40d0f70ee379f5d1347b7443817713a53e097f89
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898754"
---
# <a name="compiler-error-c2705"></a>编译器错误 C2705

> "*label*"：非法跳转到 "异常处理程序块" 范围

## <a name="remarks"></a>注解

执行将跳转到 **`try`** / **`catch`** 、 **`__try`** / **`__except`** 或 **`__try`** / **`__finally`** 块中的标签。 编译器不允许这种行为。 有关详细信息，请参阅 [异常处理](../../cpp/exception-handling-in-visual-cpp.md)。

## <a name="example"></a>示例

下面的示例生成 C2705：

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```

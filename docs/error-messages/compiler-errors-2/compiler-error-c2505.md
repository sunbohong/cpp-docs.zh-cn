---
description: 了解更多：编译器错误 C2505
title: 编译器错误 C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: 46054594731b8e39f4cb4b13e71559fcdbd2a55d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213008"
---
# <a name="compiler-error-c2505"></a>编译器错误 C2505

"symbol"： "__declspec (修饰符) " 只能应用于全局对象或静态数据成员的声明或定义

**`__declspec`** 在函数中使用了仅用于全局范围的修饰符。

有关详细信息，请参见 [应用程序域](../../cpp/appdomain.md) 和 [过程](../../cpp/process.md)。

下面的示例生成 C2505：

```cpp
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```

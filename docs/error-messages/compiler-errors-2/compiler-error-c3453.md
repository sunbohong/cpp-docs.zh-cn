---
description: 了解更多：编译器错误 C3453
title: 编译器错误 C3453
ms.date: 11/04/2016
f1_keywords:
- C3453
helpviewer_keywords:
- C3453
ms.assetid: dbefdbcf-f697-4239-b7a5-1d99b85e9e7f
ms.openlocfilehash: 2ff1c246dc66d60266f0fc44e134db3ab21605df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315967"
---
# <a name="compiler-error-c3453"></a>编译器错误 C3453

“attribute”：由于限定符“assembly”不匹配，因此没有应用特性

程序集或模块级特性只能指定为独立的说明。

## <a name="example"></a>示例

下面的示例生成 C3453。

```cpp
// C3453.cpp
// compile with: /clr /c
[assembly:System::CLSCompliant(true)]   // C3453
// try the following line instead
// [assembly:System::CLSCompliant(true)];
ref class X {};
```

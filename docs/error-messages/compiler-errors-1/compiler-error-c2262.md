---
description: 了解更多：编译器错误 C2262
title: 编译器错误 C2262
ms.date: 11/04/2016
f1_keywords:
- C2262
helpviewer_keywords:
- C2262
ms.assetid: 727d1c6e-53e8-40e5-b7b8-6a7ac2011727
ms.openlocfilehash: ef4cbeeeef9a7df42510dbf4cd021dde2081d294
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134571"
---
# <a name="compiler-error-c2262"></a>编译器错误 C2262

“attribute_specifiers”：不能为 InternalsVisibleTo 声明指定版本、区域性或处理器体系结构

未正确指定 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 特性。

## <a name="example"></a>示例

下面的示例生成 C2262。

```cpp
// C2262.cpp
// compile with: /clr /c
using namespace System::Runtime::CompilerServices;
[assembly: InternalsVisibleTo("assembly_name, version=1.2.3.7")];   // C2262
[assembly: InternalsVisibleTo("assembly_name ")];   // OK
```

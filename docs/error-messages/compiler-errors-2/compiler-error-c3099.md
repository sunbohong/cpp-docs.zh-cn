---
description: 了解更多：编译器错误 C3099
title: 编译器错误 C3099
ms.date: 11/04/2016
f1_keywords:
- C3099
helpviewer_keywords:
- C3099
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
ms.openlocfilehash: d065edd58df1e9196dc6aa31cfd4fb263f062f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116218"
---
# <a name="compiler-error-c3099"></a>编译器错误 C3099

“关键字”：将 [System::AttributeUsageAttribute] 用于托管特性；将 [Windows::Foundation::Metadata::AttributeUsageAttribute] 用于 WinRT 特性

使用 <xref:System.AttributeUsageAttribute> 声明 **/clr** 特性。 使用 `Windows::Foundation::Metadata::AttributeUsageAttribute` 声明 Windows 运行时特性。

有关/CLR 特性的详细信息，请参阅 [用户定义的属性](../../extensions/user-defined-attributes-cpp-component-extensions.md)。 有关 Windows 运行时中支持的属性，请参阅 [Windows Foundation 命名空间](/uwp/api/windows.foundation.metadata)

## <a name="example"></a>示例

下面的示例生成 C3099，并演示如何修复此错误。

```cpp
// C3099.cpp
// compile with: /clr /c
using namespace System;
[usage(10)]   // C3099
// try the following line instead
// [AttributeUsageAttribute(AttributeTargets::All)]
ref class A : Attribute {};
```

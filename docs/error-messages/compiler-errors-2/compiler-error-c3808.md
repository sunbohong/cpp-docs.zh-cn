---
description: 了解更多：编译器错误 C3808
title: 编译器错误 C3808
ms.date: 11/04/2016
f1_keywords:
- C3808
helpviewer_keywords:
- C3808
ms.assetid: 2ee8ac97-3ea4-417a-8710-be73a7f98cf4
ms.openlocfilehash: e5d31e884de0b04caba7c52e8d6abc01b3d21a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315148"
---
# <a name="compiler-error-c3808"></a>编译器错误 C3808

> "*type*"：具有 ComImport 特性的类不能定义成员 "*member*"，只允许使用 abstract 或 dllimport 函数

## <a name="remarks"></a>备注

派生自的类型 <xref:System.Runtime.InteropServices.ComImportAttribute> 无法定义 *成员*。

**/Clr： pure** 和 **/clr： safe** 编译器选项在 visual studio 2015 中已弃用，在 visual studio 2017 中不受支持。

## <a name="example"></a>示例

下面的示例生成 C3808。

```cpp
// C3808.cpp
// compile with: /c /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 {
   int f() {}   // C3808
   virtual int g() abstract;   // OK

   [DllImport("msvcrt.dll")]
   int printf(System::String ^, int i);   // OK
};
```

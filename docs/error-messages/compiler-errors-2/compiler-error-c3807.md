---
description: 了解更多：编译器错误 C3807
title: 编译器错误 C3807
ms.date: 11/04/2016
f1_keywords:
- C3807
helpviewer_keywords:
- C3807
ms.assetid: 7e2b0aab-8c61-4e71-b9c1-fcaeb6a1b5ea
ms.openlocfilehash: ffa8b52b13ae7245b62cd5aa8d7fec9285754b73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260093"
---
# <a name="compiler-error-c3807"></a>编译器错误 C3807

"type"：具有 ComImport 特性的类不能从 "type2" 派生，只允许使用接口实现

派生自的类型 <xref:System.Runtime.InteropServices.ComImportAttribute> 只能实现接口。

## <a name="example"></a>示例

下面的示例生成 C3807。

```cpp
// C3807.cpp
// compile with: /clr /c
ref struct S {};
interface struct I {};

[System::Runtime::InteropServices::ComImportAttribute()]
ref struct S1 : S {};   // C3807
ref struct S2 : I {};
```

---
description: 了解更多：编译器错误 C2842
title: 编译器错误 C2842
ms.date: 11/04/2016
f1_keywords:
- C2842
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
ms.openlocfilehash: f086c6c5fcfa451f320d96470615e4f5f4d5674a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119978"
---
# <a name="compiler-error-c2842"></a>编译器错误 C2842

> "*class*"：托管或 WinRT 类型不能定义自己的 "operator new" 或 "operator delete"

## <a name="remarks"></a>备注

你可以定义自己的 **运算符 new** 或 **operator delete** 来管理本机堆上的内存分配。 但是，引用类不能定义这些运算符，因为它们仅分配在托管堆上。

有关详细信息，请参阅 [用户定义的运算符 (c + +/cli) ](../../dotnet/user-defined-operators-cpp-cli.md)。

## <a name="example"></a>示例

以下示例生成 C2842。

```cpp
// C2842.cpp
// compile with: /clr /c
ref class G {
   void* operator new( size_t nSize );   // C2842
};
```

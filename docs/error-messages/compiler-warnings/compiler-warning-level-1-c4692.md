---
description: 了解详细信息：编译器警告 (等级 1) C4692
title: 编译器警告（等级 1）C4692
ms.date: 11/04/2016
f1_keywords:
- C4692
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
ms.openlocfilehash: 7c38a2bd4bfd4de943f64483cd8a9e96ece0b580
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249121"
---
# <a name="compiler-warning-level-1-c4692"></a>编译器警告（等级 1）C4692

“function”: 非私有成员的签名包含程序集私有本机类型“native_type”

在程序集外可见的类型包含成员函数，其签名包含在程序集外部不可见的本机类型。 因此，如果成员函数的包含类型在程序集外实例化，则不应调用该成员函数。

有关详细信息，请参阅 [类型可见性](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)。

默认情况下，此警告处于关闭状态。 有关详细信息，请参阅 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

## <a name="example"></a>示例

下面的示例生成 C4692。

```cpp
// C4692.cpp
// compile with: /W1 /c /clr
#pragma warning(default:4692)
class Private_Native_Class {};
public class Public_Native_Class {};
public ref class Public_Ref_Class {
public:
   void Test(Private_Native_Class *) {}   // C4692
   void Test2(Public_Native_Class *) {}   // OK
};
```

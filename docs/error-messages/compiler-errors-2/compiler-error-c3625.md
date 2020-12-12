---
description: 了解更多：编译器错误 C3625
title: 编译器错误 C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: ee28175eac35e05ca2a4620dffa84cf995e053a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144490"
---
# <a name="compiler-error-c3625"></a>编译器错误 C3625

“native_type”：本机类型不能从托管或 WinRT 类型“type”派生

本机类不能从托管或 WinRT 类继承。 有关更多信息，请参阅[类和结构](../../extensions/classes-and-structs-cpp-component-extensions.md)。

## <a name="example"></a>示例

以下示例生成 C3625：

```cpp
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```

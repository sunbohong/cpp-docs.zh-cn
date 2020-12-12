---
description: 了解更多：编译器错误 C3839
title: 编译器错误 C3839
ms.date: 11/04/2016
f1_keywords:
- C3839
helpviewer_keywords:
- C3839
ms.assetid: 0957faff-1e9f-439b-876b-85bd8d2c578d
ms.openlocfilehash: 8b34cdd7f09bea924d3e184f7ea639c3f8210ed5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180794"
---
# <a name="compiler-error-c3839"></a>编译器错误 C3839

无法更改托管或 WinRT 类型中的对齐方式

托管或 Windows 运行时类型中的变量对齐由 CLR 或 Windows 运行时控制，不能使用 [align](../../cpp/align-cpp.md)进行修改。

下面的示例生成 C3839：

```cpp
// C3839a.cpp
// compile with: /clr
ref class C
{
public:
   __declspec(align(32)) int m_j; // C3839
};

int main()
{
}
```

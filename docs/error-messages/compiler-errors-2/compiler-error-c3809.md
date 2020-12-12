---
description: 了解更多：编译器错误 C3809
title: 编译器错误 C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 62e7ff06e6ed5bf34861fdbae3f823e19ad5aad4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328204"
---
# <a name="compiler-error-c3809"></a>编译器错误 C3809

“class”: 托管或 WinRT 类型不能有任何友元函数/类/接口

托管类型和 Windows 运行时类型不允许使用友元。 若要修复此错误，请不要声明在托管或 Windows 运行时类型内声明友元。

下面的示例生成 C3809：

```cpp
// C3809a.cpp
// compile with: /clr
ref class A {};

ref class B
{
public:
   friend ref class A;   // C3809
};

int main()
{
}
```

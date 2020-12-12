---
description: 了解详细信息：编译器警告 (等级 1) C4917
title: 编译器警告（等级 1）C4917
ms.date: 11/04/2016
f1_keywords:
- C4917
helpviewer_keywords:
- C4917
ms.assetid: c05e2610-4a5d-4f4b-a99b-c15fd7f1d5f1
ms.openlocfilehash: b85d9dced285eade22cf6b8ff61657cd53703b88
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291423"
---
# <a name="compiler-warning-level-1-c4917"></a>编译器警告（等级 1）C4917

"声明符"： GUID 只能与类、接口或命名空间关联

除 [类](../../cpp/class-cpp.md)、 [接口](../../cpp/interface.md)或 [命名空间](../../cpp/namespaces-cpp.md) 之外的用户定义结构不能具有 GUID。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

## <a name="example"></a>示例

下面的代码示例生成 C4917：

```cpp
// C4917.cpp
// compile with: /W1
#pragma warning(default : 4917)
__declspec(uuid("00000000-0000-0000-0000-000000000001")) struct S
{
} s;   // C4917, don't put uuid on a struct

int main()
{
}
```

---
description: 详细了解：编译器警告 (级别 4) C4820
title: 编译器警告（等级 4）C4820
ms.date: 11/04/2016
f1_keywords:
- C4820
helpviewer_keywords:
- C4820
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
ms.openlocfilehash: 778bf605d6ee1441e9efd68380c64d231df03b69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330478"
---
# <a name="compiler-warning-level-4-c4820"></a>编译器警告（等级 4）C4820

“bytes”字节填充添加在构造“member_name”之后

元素的类型和顺序导致编译器向结构的末尾添加填充。 有关在结构中填充的详细信息，请参阅 [align](../../cpp/align-cpp.md) 。

默认情况下，此警告处于关闭状态。 请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 了解详细信息。

下面的示例生成 C4820：

```cpp
// C4820.cpp
// compile with: /W4 /c
#pragma warning(default : 4820)

// Delete the following 4 lines to resolve.
__declspec(align(2)) struct MyStruct {
   char a;
   int i;   // C4820
};

// OK
#pragma pack(1)
__declspec(align(1)) struct MyStruct2 {
   char a;
   int i;
};
```

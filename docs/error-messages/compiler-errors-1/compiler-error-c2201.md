---
title: 编译器错误 C2201
ms.date: 11/04/2016
f1_keywords:
- C2201
helpviewer_keywords:
- C2201
ms.assetid: ed927659-6e9c-447d-9963-19969ae1e957
ms.openlocfilehash: d6697de48c4868170e8c7afa287b0eb43e9523f5
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501641"
---
# <a name="compiler-error-c2201"></a>编译器错误 C2201

"identifier"：必须具有外部链接才能导出/导入

导出的标识符为 **`static`** 。

下面的示例生成 C2286：

```cpp
// C2201.cpp
// compile with: /c
__declspec(dllexport) static void func() {}   // C2201 func() is static
__declspec(dllexport) void func2() {}   // OK
```

## <a name="see-also"></a>请参阅

[链接的类型](../../cpp/program-and-linkage-cpp.md)

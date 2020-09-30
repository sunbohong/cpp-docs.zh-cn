---
title: 编译器错误 C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: a0f74179e187baea80993c5dda3f35f602f876c1
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508530"
---
# <a name="compiler-error-c2348"></a>编译器错误 C2348

"type name"：不是 C 样式聚合，无法在嵌入的 IDL 中导出

若要将 **`struct`** [导出](../../windows/attributes/export.md) 特性置于 .idl 文件中， **`struct`** 必须只包含数据。

下面的示例生成 C2348：

```cpp
// C2348.cpp
// C2348 error expected
[ module(name="SimpleMidlTest") ];

[export]
struct Point {
   // Delete the following two lines to resolve.
   Point() : m_i(0), m_j(0) {}
   Point(int i, int j) : m_i(i), m_j(j) {}

   int m_i;
   int m_j;
};
```

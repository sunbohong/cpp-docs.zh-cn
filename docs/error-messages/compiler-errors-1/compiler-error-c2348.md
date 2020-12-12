---
description: 了解更多：编译器错误 C2348
title: 编译器错误 C2348
ms.date: 11/04/2016
f1_keywords:
- C2348
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
ms.openlocfilehash: 829bd94c8fe78280b8b49b74f218e2143dda4335
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298352"
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

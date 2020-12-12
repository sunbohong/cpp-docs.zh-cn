---
description: 了解更多：编译器错误 C3075
title: 编译器错误 C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 68169ade5e9de13b618fe6d90936cbe887690775
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320218"
---
# <a name="compiler-error-c3075"></a>编译器错误 C3075

“instance”：无法将引用类型“type”的实例嵌入到值类型中

值类型不能包含引用类型的实例。

有关详细信息，请参阅 [引用类型的 c + + 堆栈语义](../../dotnet/cpp-stack-semantics-for-reference-types.md)。

## <a name="example"></a>示例

以下示例生成 C3075。

```cpp
// C3075.cpp
// compile with: /clr /c
ref struct U {};
value struct X {
   U y;   // C3075
};

ref struct Y {
   U y;   // OK
};
```

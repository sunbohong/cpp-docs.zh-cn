---
description: 了解更多：编译器错误 C2978
title: 编译器错误 C2978
ms.date: 11/04/2016
f1_keywords:
- C2978
helpviewer_keywords:
- C2978
ms.assetid: 5e7bee82-e266-4ccd-ad2e-ee89606ec5bf
ms.openlocfilehash: 7f39b6d7b01790bd8865c4e176ff8ed865756edb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281816"
---
# <a name="compiler-error-c2978"></a>编译器错误 C2978

语法错误：应为“keyword1”或“keyword2”；却发现类型“keyword3”；泛型中不支持非类型参数

未正确声明泛型类。 有关详细信息，请参阅 [泛型](../../extensions/generics-cpp-component-extensions.md)。

## <a name="example"></a>示例

以下示例生成 C2978：

```cpp
// C2978.cpp
// compile with: /clr /c
generic <ref class T>   // C2978
// try the following line instead
// generic <typename T>   // OK
ref class Utils {
   static void sort(T elems, size_t size);
};

generic <int>
// try the following line instead
// generic <class T>
ref class Utils2 {
   static void sort(T elems, size_t size);
};
```

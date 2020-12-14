---
description: 了解更多：编译器错误 C2779
title: 编译器错误 C2779
ms.date: 11/04/2016
f1_keywords:
- C2779
helpviewer_keywords:
- C2779
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
ms.openlocfilehash: 88acf83feb7a5aece8f05431eec7c70869cba6a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298040"
---
# <a name="compiler-error-c2779"></a>编译器错误 C2779

"声明"：属性方法只能与非静态数据成员关联

**`property`** 扩展属性未正确地应用于静态数据成员。

下面的示例生成 C2779：

```cpp
// C2779.cpp
struct A {
   static __declspec(property(put=PutProp))
   // try the following line instead
   __declspec(property(put=PutProp))
      int prop;   // C2779
   int PutProp(void);
};
```

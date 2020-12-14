---
description: 了解更多：编译器错误 C3551
title: 编译器错误 C3551
ms.date: 11/04/2016
f1_keywords:
- C3551
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
ms.openlocfilehash: 813d483b696d0829f05108a35e5731f93f6004ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223264"
---
# <a name="compiler-error-c3551"></a>编译器错误 C3551

“应为后期指定的返回类型”

如果使用 **`auto`** 关键字作为函数返回类型的占位符，则必须提供一个后期指定的返回类型。 在下面的示例中，函数的后期指定返回类型 `myFunction` 是一个指针，指向类型的四个元素的数组 **`int`** 。

```
auto myFunction()->int(*)[4];
```

## <a name="see-also"></a>请参阅

[auto](../../cpp/auto-cpp.md)

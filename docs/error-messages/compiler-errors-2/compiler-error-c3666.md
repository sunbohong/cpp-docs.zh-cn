---
description: 了解更多：编译器错误 C3666
title: 编译器错误 C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: 245fd061a7a1ce7b9b3e25ae76e6b15ec9428145
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134259"
---
# <a name="compiler-error-c3666"></a>编译器错误 C3666

"构造函数"：不允许在构造函数上使用重写说明符 "关键字"

在构造函数上使用了 override 说明符，这是不允许的。 有关详细信息，请参阅 [重写说明符](../../extensions/override-specifiers-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3666。

```cpp
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```

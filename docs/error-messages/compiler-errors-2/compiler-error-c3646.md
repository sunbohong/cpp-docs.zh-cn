---
description: 了解更多：编译器错误 C3646
title: 编译器错误 C3646
ms.date: 06/14/2018
f1_keywords:
- C3646
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
ms.openlocfilehash: 0c6f731a09612e6c128756de8d0690c922047e49
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203778"
---
# <a name="compiler-error-c3646"></a>编译器错误 C3646

> "说明符"：未知重写说明符

## <a name="remarks"></a>备注

编译器在预期找到重写说明符的位置找到了一个标记，但编译器无法识别该标记。

例如，如果 **_NOEXCEPT** 无法识别的 *说明符*，请将其替换为关键字 **`noexcept`** 。

有关详细信息，请参阅 [重写说明符](../../extensions/override-specifiers-cpp-component-extensions.md)。

## <a name="example"></a>示例

下面的示例生成 C3646，并演示如何修复此问题：

```cpp
// C3646.cpp
// compile with: /clr /c
ref class C {
   void f() unknown;   // C3646
   // try the following line instead
   // virtual void f() abstract;
};
```

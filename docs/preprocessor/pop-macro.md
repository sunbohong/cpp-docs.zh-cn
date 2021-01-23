---
description: 详细了解 pragma Microsoft c/c + + 中的 pop_macro 指令
title: pop_macro pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.pop_macro
- pop_macro_CPP
helpviewer_keywords:
- pop_macro pragma
- pragma, pop_macro
no-loc:
- pragma
ms.openlocfilehash: 99b0567838bac2a683f2a31fe13dd423e2efe651
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713358"
---
# <a name="pop_macro-no-locpragma"></a>`pop_macro` pragma

将 *宏名称* 宏的值设置为此宏的堆栈顶部的值。

## <a name="syntax"></a>语法

> **`#pragma pop_macro(`** "*宏名*" **`)`**

## <a name="remarks"></a>注解

[`push_macro`](../preprocessor/push-macro.md)必须先发出用于 *宏名* 的，然后才能执行 **`pop_macro`** 。

## <a name="example"></a>示例

```cpp
// pragma_directives_pop_macro.cpp
// compile with: /W1
#include <stdio.h>
#define X 1
#define Y 2

int main() {
   printf("%d",X);
   printf("\n%d",Y);
   #define Y 3   // C4005
   #pragma push_macro("Y")
   #pragma push_macro("X")
   printf("\n%d",X);
   #define X 2   // C4005
   printf("\n%d",X);
   #pragma pop_macro("X")
   printf("\n%d",X);
   #pragma pop_macro("Y")
   printf("\n%d",Y);
}
```

```Output
1
2
1
2
1
3
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)

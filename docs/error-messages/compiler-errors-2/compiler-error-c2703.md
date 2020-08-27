---
title: 编译器错误 C2703
description: 描述 Microsoft C/c + + 编译器错误 C2703。
ms.date: 08/24/2020
f1_keywords:
- C2703
helpviewer_keywords:
- C2703
ms.assetid: 384295c3-643d-47ae-a9a6-865b3036aa84
ms.openlocfilehash: 4d5b5ccad1cd15c1a107c81423e2372e14165776
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898603"
---
# <a name="compiler-error-c2703"></a>编译器错误 C2703

> 非法 `__leave` 语句

## <a name="remarks"></a>注解

**`__leave`** 语句必须位于 **`__try`** 块内。

## <a name="example"></a>示例

下面的示例生成 C2703：

```cpp
// C2703.cpp
int main() {
   __leave;   // C2703
   __try {
      // try the following line instead
      __leave;
   }
   __finally {}
}
```

## <a name="see-also"></a>请参阅

[`__leave`关键字](../../cpp/try-except-statement.md#__leave)\
[`try-except` 损益](../../cpp/try-except-statement.md)\
[`try-finally` 语句](../../cpp/try-finally-statement.md)

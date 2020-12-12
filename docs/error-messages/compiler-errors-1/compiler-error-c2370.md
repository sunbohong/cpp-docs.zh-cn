---
description: 了解更多：编译器错误 C2370
title: 编译器错误 C2370
ms.date: 11/04/2016
f1_keywords:
- C2370
helpviewer_keywords:
- C2370
ms.assetid: 03403e8f-f393-47c4-bd25-5c1c7ea7d5cd
ms.openlocfilehash: 75fcb952dadcb14d0edeb3e18b9cad1c6af535f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326066"
---
# <a name="compiler-error-c2370"></a>编译器错误 C2370

“identifier”: 重定义；不同的存储类

已使用不同的存储类声明标识符。

## <a name="examples"></a>示例

下面的示例生成 C2370:

```cpp
// C2370.cpp
// compile with: /Za /c
extern int i;
static int i;   // C2370
int i;   // OK
```

下面的示例生成 C2370:

```cpp
// C2370b.cpp
#define Thread __declspec( thread )
extern int tls_i;
int Thread tls_i;   // C2370 declaration and the definition differ
int tls_i;   // OK
```

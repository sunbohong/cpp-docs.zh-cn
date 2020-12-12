---
description: 了解更多：编译器错误 C2053
title: 编译器错误 C2053
ms.date: 11/04/2016
f1_keywords:
- C2053
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
ms.openlocfilehash: 6ead23c4a32e2f781bbc070284d6c83118e0c569
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283714"
---
# <a name="compiler-error-c2053"></a>编译器错误 C2053

"identifier"：宽字符串不匹配

宽字符串分配给不兼容的类型。

下面的示例生成 C2053：

```c
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```

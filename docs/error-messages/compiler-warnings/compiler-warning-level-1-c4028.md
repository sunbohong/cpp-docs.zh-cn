---
description: 了解详细信息：编译器警告 (等级 1) C4028
title: 编译器警告 (等级 1) C4028
ms.date: 11/04/2016
f1_keywords:
- C4028
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
ms.openlocfilehash: ac6f4ba05d7acfa0772429372128d32c27fc909c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241412"
---
# <a name="compiler-warning-level-1-c4028"></a>编译器警告 (等级 1) C4028

形参 "number" 与声明不同

形参的类型与声明中的相应参数不一致。 使用原始声明中的类型。

此警告仅对 C 源代码有效。

## <a name="example"></a>示例

下面的示例生成 C4028。

```c
// C4028.c
// compile with: /W1 /Za
void f(int , ...);
void f(int i, int j) {}   // C4028

void g(int , int);
void g(int i, int j) {}   // OK

int main() {}
```

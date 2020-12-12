---
description: 了解更多：编译器错误 C2714
title: 编译器错误 C2714
ms.date: 07/22/2020
f1_keywords:
- C2714
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
ms.openlocfilehash: 7bea0fc27de49f5767b8b250254f255964423cdc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320826"
---
# <a name="compiler-error-c2714"></a>编译器错误 C2714

> `alignof(void)` 不允许

传递给运算符的值无效。

## <a name="remarks"></a>备注

有关详细信息，请参阅[ `alignof` 运算符](../../cpp/alignof-operator.md)。

## <a name="example"></a>示例

下面的示例生成 C2714。

```cpp
// C2714.cpp
int main() {
   return alignof(void);   // C2714
   return alignof(char);   // OK
}
```

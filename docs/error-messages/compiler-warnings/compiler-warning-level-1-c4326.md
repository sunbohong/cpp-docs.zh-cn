---
description: 了解详细信息：编译器警告 (等级 1) C4326
title: 编译器警告（等级 1）C4326
ms.date: 08/27/2018
f1_keywords:
- C4326
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
ms.openlocfilehash: d7c82d7a0157b53e60281bbe7c45a38cc765a73d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340037"
---
# <a name="compiler-warning-level-1-c4326"></a>编译器警告（等级 1）C4326

> "*function*" 的返回类型应为 "*type1*"，而不是 "*type2*"

## <a name="remarks"></a>备注

函数返回了 *type1* 以外的类型。 例如，使用 [/za](../../build/reference/za-ze-disable-language-extensions.md)， **main** 未返回 **`int`** 。

## <a name="example"></a>示例

下面的示例生成 C4326，并演示如何修复此问题：

```cpp
// C4326.cpp
// compile with: /Za /W1
char main()
{
    // C4326, instead use int main()
}
```

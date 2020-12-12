---
description: 详细了解：编译器警告 (等级 3) C4159
title: 编译器警告 (等级 3) C4159
ms.date: 11/04/2016
f1_keywords:
- C4159
helpviewer_keywords:
- C4159
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
ms.openlocfilehash: 153bd7ee7bc634ab10e0e6eb872a8f055e6470e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326458"
---
# <a name="compiler-warning-level-3-c4159"></a>编译器警告 (等级 3) C4159

> #<a name="pragma-pragmapop--has-popped-previously-pushed-identifier-identifier"></a>pragma pragma (pop,... ) ：已弹出先前推送的标识符 "*identifier*"

## <a name="remarks"></a>备注

你的源代码包含带有杂注标识符的 **推送** 指令，后跟不带标识符的 **pop** 指令。 因此，会弹出 *标识符* ，以后使用 *标识符* 可能会导致意外的行为。

## <a name="example"></a>示例

为避免出现此警告，请在 **pop** 指令中指定一个标识符。 例如：

```cpp
// C4159.cpp
// compile with: /W3
#pragma pack(push, f)
#pragma pack(pop)   // C4159

// using the identifier resolves the warning
// #pragma pack(pop, f)

int main()
{
}
```

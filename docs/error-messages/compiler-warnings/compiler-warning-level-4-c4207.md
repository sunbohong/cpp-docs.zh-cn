---
description: 详细了解：编译器警告 (级别 4) C4207
title: 编译器警告（等级 4）C4207
ms.date: 11/04/2016
f1_keywords:
- C4207
helpviewer_keywords:
- C4207
ms.assetid: f4e09e3e-ac87-4489-8e3f-c8f76b82e721
ms.openlocfilehash: fe442f71789533227a68a2f9059291de207e277b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173215"
---
# <a name="compiler-warning-level-4-c4207"></a>编译器警告（等级 4）C4207

使用了非标准扩展：扩展初始值设定项窗体

使用 Microsoft extensions (/Ze) ，可以 **`char`** 使用大括号内的字符串初始化成员列表数组数组。

## <a name="example"></a>示例

```c
// C4207.c
// compile with: /W4
char c[] = { 'a', 'b', "cdefg" }; // C4207

int main()
{
}
```

此类初始化在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中无效。

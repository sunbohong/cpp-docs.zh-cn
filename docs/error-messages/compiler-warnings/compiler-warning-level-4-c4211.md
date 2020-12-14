---
description: 详细了解：编译器警告 (级别 4) C4211
title: 编译器警告（等级 4）C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: bbd6469dc98d95342538bf3a9065b4647619d69a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314732"
---
# <a name="compiler-warning-level-4-c4211"></a>编译器警告（等级 4）C4211

使用了非标准扩展：将 extern 重定义为 static

使用默认的 Microsoft 扩展 (/Ze) ，你可以将标识符重定义 **`extern`** 为 **`static`** 。

## <a name="example"></a>示例

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

此类重新定义在 ANSI 兼容性 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) 中无效。
